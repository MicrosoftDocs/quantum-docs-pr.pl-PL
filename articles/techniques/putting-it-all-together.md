---
title: Techniki Q# - Łącząc to wszystko razem
description: Przejdź przez podstawowy program Q#, który demonstruje teleportację kwantową.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030569"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="9ff23-103">Wszystko razem: Teleportacja</span><span class="sxs-lookup"><span data-stu-id="9ff23-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="9ff23-104">Wróćmy do przykładu obwodu teleportacji zdefiniowanego w [obwodach kwantowych.](xref:microsoft.quantum.concepts.circuits)</span><span class="sxs-lookup"><span data-stu-id="9ff23-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="9ff23-105">Wykorzystamy to do zilustrowania pojęć, których do tej pory się nauczyliśmy.</span><span class="sxs-lookup"><span data-stu-id="9ff23-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="9ff23-106">Wyjaśnienie teleportacji kwantowej znajduje się poniżej dla tych, którzy nie są zaznajomieni z teorią, a następnie instruktaż implementacji kodu w Q#.</span><span class="sxs-lookup"><span data-stu-id="9ff23-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="9ff23-107">Teleportacja kwantowa: Teoria</span><span class="sxs-lookup"><span data-stu-id="9ff23-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="9ff23-108">Teleportacja kwantowa jest techniką wysyłania nieznanego stanu kwantowego (który będziemy odnosić się jako "__wiadomość__") z kubitu w jednym miejscu do kubitu w innym miejscu (będziemy odnosić się do tych kubitów jako "__tutaj__" i "__tam__', odpowiednio).</span><span class="sxs-lookup"><span data-stu-id="9ff23-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="9ff23-109">Możemy reprezentować nasze __przesłanie__ jako wektor za pomocą notacji Dirac:</span><span class="sxs-lookup"><span data-stu-id="9ff23-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="9ff23-110">$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="9ff23-111">Stan kubitu __wiadomości__ jest nam nieznany, ponieważ nie znamy wartości $\alpha$ i $\beta$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="9ff23-112">Krok 1: Tworzenie stanu splątanego</span><span class="sxs-lookup"><span data-stu-id="9ff23-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="9ff23-113">Aby wysłać __wiadomość__ musimy kubit __tutaj__ być uwikłany w kubit __tam__.</span><span class="sxs-lookup"><span data-stu-id="9ff23-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="9ff23-114">Osiąga się to poprzez zastosowanie bramy Hadamarda, a następnie bramy CNOT.</span><span class="sxs-lookup"><span data-stu-id="9ff23-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="9ff23-115">Spójrzmy na matematykę za tymi operacjami bramek.</span><span class="sxs-lookup"><span data-stu-id="9ff23-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="9ff23-116">Zaczniemy od kubitów __tu__ i __tam__ zarówno w{0}stanie $\ket $.</span><span class="sxs-lookup"><span data-stu-id="9ff23-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="9ff23-117">Po oplątanie tych kubitów, są one w stanie:</span><span class="sxs-lookup"><span data-stu-id="9ff23-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="9ff23-118">$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="9ff23-119">Krok 2: Wyślij wiadomość</span><span class="sxs-lookup"><span data-stu-id="9ff23-119">Step 2: Send the message</span></span>
<span data-ttu-id="9ff23-120">Aby wysłać __wiadomość,__ najpierw stosujemy bramę CNOT z kubitem __wiadomości__ i __tutaj__ kubit jako dane wejściowe (kubit __wiadomości__ jest formantem, a kubit __tutaj__ jest kubitem docelowym, w tym przypadku).</span><span class="sxs-lookup"><span data-stu-id="9ff23-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="9ff23-121">Ten stan wejściowy może być zapisany:</span><span class="sxs-lookup"><span data-stu-id="9ff23-121">This input state can be written:</span></span>

<span data-ttu-id="9ff23-122">$${0} \ket{\psi}\ket{\phi^+} = (\alpha\ket +{1}\beta\ket{1})(\frac {\sqrt{2}}(\ket{00} + \ket{11})) $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="9ff23-123">Spowoduje to rozszerzenie o:</span><span class="sxs-lookup"><span data-stu-id="9ff23-123">This expands to:</span></span>

<span data-ttu-id="9ff23-124">$$ \ket{\psi}\ket{\phi^+} ={2}\frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} +{2}\frac{/beta}{\sqrt }{\sqrt }{\pl/ket}{\ket}{\ket}{\ket}{\ket}{\ket}{\ket}\ket}\ket}\ket}\ket }\ket{111} $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="9ff23-125">Przypominamy, że brama CNOT odwraca kubit docelowy, gdy kubit kontrolny wynosi 1.</span><span class="sxs-lookup"><span data-stu-id="9ff23-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="9ff23-126">Na przykład wejście $\ket{000}$ spowoduje brak zmian, ponieważ pierwszy kubit (formant) wynosi 0.</span><span class="sxs-lookup"><span data-stu-id="9ff23-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="9ff23-127">Jednak weź przypadek, w którym pierwszy kubit jest 1 -{100}na przykład wejście $\ket $.</span><span class="sxs-lookup"><span data-stu-id="9ff23-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="9ff23-128">W tym przypadku dane wyjściowe{110}to $\ket $ jako drugi kubit (cel) jest odwrócony przez bramę CNOT.</span><span class="sxs-lookup"><span data-stu-id="9ff23-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="9ff23-129">Rozważmy teraz nasze dane wyjściowe, gdy brama CNOT działała na nasze dane wejściowe powyżej.</span><span class="sxs-lookup"><span data-stu-id="9ff23-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="9ff23-130">Rezultatem jest:</span><span class="sxs-lookup"><span data-stu-id="9ff23-130">The result is:</span></span>

<span data-ttu-id="9ff23-131">{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{011} {2}{110} {2}{101} {2}}\ket + \frac{\beta}{\sqrt }\ket + \frac{\beta}{\sqrt }\ket $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="9ff23-132">Następnym krokiem do wysłania __wiadomości__ jest zastosowanie bramy Hadamarda do kubitu __wiadomości__ (to pierwszy kubit każdego terminu).</span><span class="sxs-lookup"><span data-stu-id="9ff23-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="9ff23-133">Przypominamy, że brama Hadamarda wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="9ff23-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="9ff23-134">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9ff23-134">Input</span></span> | <span data-ttu-id="9ff23-135">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="9ff23-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="9ff23-136">$\ket{0}$</span><span class="sxs-lookup"><span data-stu-id="9ff23-136">$\ket{0}$</span></span>  | <span data-ttu-id="9ff23-137">$\frac{1}{\sqrt{2}}(\ket{0} +{1}\ket )$</span><span class="sxs-lookup"><span data-stu-id="9ff23-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="9ff23-138">$\ket{1}$</span><span class="sxs-lookup"><span data-stu-id="9ff23-138">$\ket{1}$</span></span>  | <span data-ttu-id="9ff23-139">$\frac{1}{\sqrt{2}}(\ket{0} -{1}\ket )$</span><span class="sxs-lookup"><span data-stu-id="9ff23-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="9ff23-140">Jeśli zastosujemy bramę Hadamarda do pierwszego kubitu każdego okresu naszej produkcji powyżej, uzyskamy następujący wynik:</span><span class="sxs-lookup"><span data-stu-id="9ff23-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="9ff23-141">$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}}(\ket{1}{00} {2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {1}{01} {0} + \ket ))\ket + \frac{\alpha}{\sqrt }(\frac {\sqrt }(\ket + \ket ))\ket + \frac{/beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="9ff23-142">Należy zauważyć, że każdy termin{1}ma dwa{2}$\frac {\sqrt }$ czynników.</span><span class="sxs-lookup"><span data-stu-id="9ff23-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="9ff23-143">Możemy je pomnożyć, podając następujący wynik:</span><span class="sxs-lookup"><span data-stu-id="9ff23-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="9ff23-144">$$ \frac{\alpha}{2}(\ket{0} +{1}\ket{00} )\ket +{2}\frac{\alpha} (\ket{0} + \ket{1}{11} )\ket + \frac{\beta}{2}(\ket{0} - \ket{0} {1}{01} {1})\ket{10} + \frac{\beta}{2}(\ket - \ket )\ket $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="9ff23-145">Współczynnik $\frac{1}{2}$ jest wspólny dla każdego terminu, więc możemy teraz zabrać go poza nawiasy:</span><span class="sxs-lookup"><span data-stu-id="9ff23-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="9ff23-146">$${1}{2}\frac \big[\alpha(\ket{0} +{1}\ket{00} )\ket +{0} \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket - \ket{0} {1})\ket{01}\big] $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="9ff23-147">Następnie możemy pomnożyć nawiasy dla każdego terminu dając:</span><span class="sxs-lookup"><span data-stu-id="9ff23-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="9ff23-148">{1}{2}$$ \frac \big[\alpha\ket{000} + \alpha\ket{100} +{011} \alpha\ket{111} + \alpha\ket{010} + \beta\ket -{001} \beta\ket{101}{110} + \beta\ket - \beta\ket \ket \big] $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="9ff23-149">Krok 3: Zmierz wynik</span><span class="sxs-lookup"><span data-stu-id="9ff23-149">Step 3: Measure the result</span></span>

<span data-ttu-id="9ff23-150">Ze względu na __tu__ i __nie__ jest splątane, każdy pomiar __tutaj__ wpłynie na stan __tam__.</span><span class="sxs-lookup"><span data-stu-id="9ff23-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="9ff23-151">Jeśli zmierzymy pierwszy i drugi kubit (__wiadomość__ i __tutaj__) możemy dowiedzieć się, w jakim stanie __jest,__ ze względu na tę właściwość splątania.</span><span class="sxs-lookup"><span data-stu-id="9ff23-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="9ff23-152">Jeśli zmierzymy i uzyskamy wynik 00, superpozycja upada, pozostawiając tylko warunki zgodne z tym wynikiem.</span><span class="sxs-lookup"><span data-stu-id="9ff23-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="9ff23-153">To $\alpha\ket{000} +\beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="9ff23-154">Można to z refaktoryzować{00}do $\ket (\alpha\ket{0} +/beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="9ff23-155">Dlatego jeśli zmierzymy pierwszy i drugi kubit na 00, wiemy, że trzeci kubit, __tam__,{0} jest w stanie{1}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="9ff23-156">Jeśli zmierzymy i uzyskamy wynik 01, superpozycja upada, pozostawiając tylko warunki zgodne z tym wynikiem.</span><span class="sxs-lookup"><span data-stu-id="9ff23-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="9ff23-157">To $\alpha\ket{011} +\beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="9ff23-158">Można to z refaktoryzować{01}do $\ket (\alpha\ket{1} +/beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="9ff23-159">Dlatego jeśli zmierzymy pierwszy i drugi kubit na 01, wiemy, że trzeci kubit, __tam__,{1} jest w stanie{0}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="9ff23-160">Jeśli zmierzymy i uzyskamy wynik 10, superpozycja upada, pozostawiając tylko warunki zgodne z tym wynikiem.</span><span class="sxs-lookup"><span data-stu-id="9ff23-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="9ff23-161">To jest $\alpha\ket{100} -\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="9ff23-162">Można to z refaktoryzować{10}do $\ket (\alpha\ket{0} -\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="9ff23-163">Dlatego jeśli zmierzymy pierwszy i drugi kubit na 10, wiemy, że trzeci kubit, __tam__,{0} jest w stanie{1}$(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="9ff23-164">Jeśli zmierzymy i uzyskamy wynik 11, superpozycja upada, pozostawiając tylko warunki zgodne z tym wynikiem.</span><span class="sxs-lookup"><span data-stu-id="9ff23-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="9ff23-165">To jest $\alpha\ket{111} -\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="9ff23-166">Można to z refaktoryzować{11}do $\ket (\alpha\ket{1} -\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="9ff23-167">Dlatego jeśli zmierzymy pierwszy i drugi kubit na 11, wiemy, że trzeci kubit, __tam__,{1} jest w stanie{0}$(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="9ff23-168">Krok 4: Interpretowanie wyniku</span><span class="sxs-lookup"><span data-stu-id="9ff23-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="9ff23-169">Przypominamy, że oryginalna __wiadomość,__ którą chcieliśmy wysłać, brzmiała:</span><span class="sxs-lookup"><span data-stu-id="9ff23-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="9ff23-170">$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="9ff23-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="9ff23-171">Musimy wprowadzić __tam__ kubit do tego stanu, aby otrzymane państwo było tym, które było zamierzone.</span><span class="sxs-lookup"><span data-stu-id="9ff23-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="9ff23-172">Jeśli zmierzyliśmy i uzyskaliśmy wynik 00, to trzeci kubit, __tam__, jest{0} w stanie $(\alpha\ket +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="9ff23-173">Ponieważ jest to zamierzony __komunikat,__ nie jest wymagana żadna zmiana.</span><span class="sxs-lookup"><span data-stu-id="9ff23-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="9ff23-174">Jeśli zmierzyliśmy i uzyskaliśmy wynik 01, to trzeci kubit, __tam__, jest{1} w stanie $(\alpha\ket +\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="9ff23-175">Różni się to od zamierzonego __komunikatu__, jednak zastosowanie nie bramy daje{0} nam żądany stan{1}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="9ff23-176">Jeśli zmierzyliśmy i uzyskaliśmy wynik 10, to trzeci kubit, __tam__, jest{0} w stanie $(\alpha\ket -\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="9ff23-177">Różni się to od zamierzonego __komunikatu__, jednak zastosowanie bramy Z daje{0} nam żądany stan{1}$(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="9ff23-178">Jeśli zmierzyliśmy i uzyskaliśmy wynik 11, to trzeci kubit, __tam__, jest{1} w stanie $(\alpha\ket -\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="9ff23-179">Różni się to od zamierzonego __komunikatu__, jednak zastosowanie nie bramy, po której następuje{0} brama Z,{1}daje nam żądany stan $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="9ff23-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="9ff23-180">Podsumowując, jeśli zmierzymy, a pierwszy kubit wynosi 1, stosowana jest brama Z.</span><span class="sxs-lookup"><span data-stu-id="9ff23-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="9ff23-181">Jeśli zmierzymy, a drugi kubit wynosi 1, zostanie zastosowana brama NOT.</span><span class="sxs-lookup"><span data-stu-id="9ff23-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="9ff23-182">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="9ff23-182">Summary</span></span>
<span data-ttu-id="9ff23-183">Poniżej pokazano tekst książki obwodu kwantowego, który implementuje teleportacji.</span><span class="sxs-lookup"><span data-stu-id="9ff23-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="9ff23-184">Przechodząc od lewej do prawej, możesz zobaczyć:</span><span class="sxs-lookup"><span data-stu-id="9ff23-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="9ff23-185">Krok 1: Oplątanie __tu__ i __ówdź,__ stosując bramę Hadamarda i bramę CNOT.</span><span class="sxs-lookup"><span data-stu-id="9ff23-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="9ff23-186">Krok 2: Wysłanie __wiadomości__ za pomocą bramy CNOT i bramy Hadamarda.</span><span class="sxs-lookup"><span data-stu-id="9ff23-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="9ff23-187">Krok 3: Pomiar pierwszego i drugiego kubitów, __wiadomość__ i __tutaj__.</span><span class="sxs-lookup"><span data-stu-id="9ff23-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="9ff23-188">Krok 4: Zastosowanie bramy NOT lub Z, w zależności od wyniku pomiaru w kroku 3.</span><span class="sxs-lookup"><span data-stu-id="9ff23-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!["Teleport(msg : Qubit, tam: Qubit) : Jednostka"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="9ff23-190">Teleportacja kwantowa: Kod</span><span class="sxs-lookup"><span data-stu-id="9ff23-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="9ff23-191">Mamy nasz obwód do teleportacji kwantowej:</span><span class="sxs-lookup"><span data-stu-id="9ff23-191">We have our circuit for quantum teleportation:</span></span>

!["Teleport(msg : Qubit, tam: Qubit) : Jednostka"](~/media/teleportation.svg)

<span data-ttu-id="9ff23-193">Możemy teraz przetłumaczyć każdy z kroków w tym obwodzie kwantowym na Q#.</span><span class="sxs-lookup"><span data-stu-id="9ff23-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="9ff23-194">Krok 0: Definicja</span><span class="sxs-lookup"><span data-stu-id="9ff23-194">Step 0: Definition</span></span>
<span data-ttu-id="9ff23-195">Kiedy przeprowadzamy teleportację, musimy znać __wiadomość,__ którą chcemy wysłać i gdzie chcemy ją wysłać __(tam).__</span><span class="sxs-lookup"><span data-stu-id="9ff23-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="9ff23-196">Z tego powodu rozpoczynamy od zdefiniowania nowej operacji Teleport, która `msg` jest `there`podana dwa kubity jako argumenty, i:</span><span class="sxs-lookup"><span data-stu-id="9ff23-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="9ff23-197">Musimy również przydzielić kubit, `here` który `using` osiągamy za pomocą bloku:</span><span class="sxs-lookup"><span data-stu-id="9ff23-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="9ff23-198">Krok 1: Tworzenie stanu splątanego</span><span class="sxs-lookup"><span data-stu-id="9ff23-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="9ff23-199">Następnie możemy utworzyć splątaną `here` `there` parę między @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" i za pomocą operacji i:</span><span class="sxs-lookup"><span data-stu-id="9ff23-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="9ff23-200">Krok 2: Wyślij wiadomość</span><span class="sxs-lookup"><span data-stu-id="9ff23-200">Step 2: Send the message</span></span>
<span data-ttu-id="9ff23-201">Następnie używamy następnego $\operatorname{CNOT}$ i $H$ bramy, aby przenieść nasz kubit wiadomości:</span><span class="sxs-lookup"><span data-stu-id="9ff23-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="9ff23-202">Krok 3 & 4: Pomiar i interpretacja wyniku</span><span class="sxs-lookup"><span data-stu-id="9ff23-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="9ff23-203">Na koniec używamy @"microsoft.quantum.intrinsic.m" do wykonywania pomiarów i wykonywania niezbędnych operacji bramy, aby uzyskać `if` pożądany stan, zgodnie z instrukcjami:</span><span class="sxs-lookup"><span data-stu-id="9ff23-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="9ff23-204">Krok 5: Ponowne uruchomienie rejestru kubitów</span><span class="sxs-lookup"><span data-stu-id="9ff23-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="9ff23-205">Na koniec każdej operacji Q# musimy pozwolić kubity w stanie{0}$\ket $.</span><span class="sxs-lookup"><span data-stu-id="9ff23-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="9ff23-206">Możemy użyć, @"microsoft.quantum.intrinsic.reset" aby ponownie uruchomić wszystkie kubity do stanu zerowego, a to zakończy naszą operację.</span><span class="sxs-lookup"><span data-stu-id="9ff23-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


