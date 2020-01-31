---
title: 'Umieszczenie ich razem — techniki Q # | Microsoft Docs'
description: 'Umieszczenie ich razem — techniki Q #'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820168"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="60729-103">Wszystkie razem: teleportowanie</span><span class="sxs-lookup"><span data-stu-id="60729-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="60729-104">Wróćmy do przykładowego obwodu teleportowego zdefiniowanego w [obwodach Quantum](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="60729-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="60729-105">Zamierzamy użyć tego przykładu do zilustrowania koncepcji, które już poznasz.</span><span class="sxs-lookup"><span data-stu-id="60729-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="60729-106">W przypadku osób, które nie znają tego teorii, należy zapoznać się z opisem teleportów Quantum, a następnie wskazówki dotyczące implementacji kodu w Q #.</span><span class="sxs-lookup"><span data-stu-id="60729-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="60729-107">Teleportowanie Quantum: teoretyczne</span><span class="sxs-lookup"><span data-stu-id="60729-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="60729-108">Teleportowanie Quantum jest techniką wysyłania nieznanego stanu Quantum (jako "__wiadomość__") z qubit w jednej lokalizacji do qubit w innej lokalizacji (odwołujemy się do tych qubits jako "__tutaj__" i "__tam__").</span><span class="sxs-lookup"><span data-stu-id="60729-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="60729-109">Możemy reprezentować nasz __komunikat__ jako wektor przy użyciu notacji Dirac:</span><span class="sxs-lookup"><span data-stu-id="60729-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="60729-110">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="60729-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="60729-111">Stan qubit __komunikatu__ jest nieznany dla nas, ponieważ nie znam wartości $ \Alpha $ i $ \beta $.</span><span class="sxs-lookup"><span data-stu-id="60729-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="60729-112">Krok 1. Tworzenie stanu Entangled</span><span class="sxs-lookup"><span data-stu-id="60729-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="60729-113">Aby wysłać __wiadomość__ , której potrzebujemy, qubit w __tym miejscu__ , aby Entangled __z qubit.__</span><span class="sxs-lookup"><span data-stu-id="60729-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="60729-114">Można to osiągnąć, stosując bramę Hadamard, a następnie bramę CNOT.</span><span class="sxs-lookup"><span data-stu-id="60729-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="60729-115">Przyjrzyjmy się zapisowi matematycznemu za te operacje na bramie.</span><span class="sxs-lookup"><span data-stu-id="60729-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="60729-116">Zaczniemy od qubits __tutaj__ __i w__ stanie $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="60729-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="60729-117">Po Entangling tych qubits są w stanie:</span><span class="sxs-lookup"><span data-stu-id="60729-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="60729-118">$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="60729-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="60729-119">Krok 2. wysłanie wiadomości</span><span class="sxs-lookup"><span data-stu-id="60729-119">Step 2: Send the message</span></span>
<span data-ttu-id="60729-120">Aby wysłać __wiadomość__ , należy najpierw zastosować bramę CNOT z __komunikatem__ qubit i __w tym miejscu__ qubit jako dane wejściowe ( __komunikat__ qubit o kontrolce, a w tym __miejscu__ qubit to element docelowy qubit, w tym wystąpieniu).</span><span class="sxs-lookup"><span data-stu-id="60729-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="60729-121">Ten stan danych wejściowych można napisać:</span><span class="sxs-lookup"><span data-stu-id="60729-121">This input state can be written:</span></span>

<span data-ttu-id="60729-122">$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="60729-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="60729-123">Rozszerza to:</span><span class="sxs-lookup"><span data-stu-id="60729-123">This expands to:</span></span>

<span data-ttu-id="60729-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="60729-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="60729-125">W wyniku tego Brama CNOT przerzuca element docelowy qubit, gdy kontrolka qubit ma wartość 1.</span><span class="sxs-lookup"><span data-stu-id="60729-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="60729-126">Na przykład, dane wejściowe klasy $ \ket{000}$ nie spowodują zmian, ponieważ pierwszy qubit (formant) to 0.</span><span class="sxs-lookup"><span data-stu-id="60729-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="60729-127">Należy jednak wziąć pod przypadek, gdzie pierwszy qubit to 1 — na przykład dane wejściowe $ \ket{100}$.</span><span class="sxs-lookup"><span data-stu-id="60729-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="60729-128">W tym przypadku dane wyjściowe to $ \ket{110}$, ponieważ drugi qubit (obiekt docelowy) jest przerzucany przez bramę CNOT.</span><span class="sxs-lookup"><span data-stu-id="60729-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="60729-129">Teraz Rozważmy nasze dane wyjściowe po przejściu bramy CNOT na nasze dane wejściowe powyżej.</span><span class="sxs-lookup"><span data-stu-id="60729-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="60729-130">Wynik:</span><span class="sxs-lookup"><span data-stu-id="60729-130">The result is:</span></span>

<span data-ttu-id="60729-131">$ $ \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="60729-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="60729-132">Następnym krokiem do wysłania __wiadomości__ jest zastosowanie bramy Hadamard do __wiadomości__ qubit (to pierwsze qubit każdego z tych terminów).</span><span class="sxs-lookup"><span data-stu-id="60729-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="60729-133">W wyniku tego Brama Hadamard wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="60729-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="60729-134">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="60729-134">Input</span></span> | <span data-ttu-id="60729-135">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="60729-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="60729-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="60729-136">$\ket{0}$</span></span>  | <span data-ttu-id="60729-137">$ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="60729-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="60729-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="60729-138">$\ket{1}$</span></span>  | <span data-ttu-id="60729-139">$ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="60729-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="60729-140">Jeśli stosujemy bramę Hadamard do pierwszego qubit każdego z powyższych danych wyjściowych powyżej, otrzymamy następujący wynik:</span><span class="sxs-lookup"><span data-stu-id="60729-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="60729-141">$ $ \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="60729-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="60729-142">Należy zauważyć, że każdy termin ma $2 \frac{1}{\sqrt{2}} $.</span><span class="sxs-lookup"><span data-stu-id="60729-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="60729-143">Możemy pomnożyć te wartości, dając następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="60729-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="60729-144">$ $ \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="60729-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="60729-145">Wartość $ \frac{1}{2}$ jest wspólna dla każdego warunku, dzięki czemu możemy teraz wykonać ją poza nawiasami:</span><span class="sxs-lookup"><span data-stu-id="60729-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="60729-146">$ $ \frac{1}{2}\big [\Alpha (\ket{0} + \ket{1}) \ket{00} + \Alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="60729-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="60729-147">Następnie można rozmnożyć nawiasy dla każdego terminu, podając:</span><span class="sxs-lookup"><span data-stu-id="60729-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="60729-148">$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001} \beta\ket{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="60729-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="60729-149">Krok 3. mierzenie wyniku</span><span class="sxs-lookup"><span data-stu-id="60729-149">Step 3: Measure the result</span></span>

<span data-ttu-id="60729-150">Ze względu __na to,__ __że__ Entangled, wszelkie pomiary w __tym miejscu__ będą miały wpływ na stan tej __lokalizacji__.</span><span class="sxs-lookup"><span data-stu-id="60729-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="60729-151">Jeśli mierzę pierwszy i drugi qubit (__komunikat__ i __tutaj__), możemy dowiedzieć się, jaki stan __istnieje__ , ze względu na tę właściwość Entanglement.</span><span class="sxs-lookup"><span data-stu-id="60729-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="60729-152">Jeśli mierzę i uzyskasz wynik 00, nadpozycja zwija, pozostawiając tylko warunki zgodne z tym wynikiem.</span><span class="sxs-lookup"><span data-stu-id="60729-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="60729-153">To $ \alpha\ket{000} + \beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="60729-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="60729-154">Można ją refaktoryzację do $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="60729-155">W związku z tym, jeśli mierzę pierwszy i drugi qubit jako 00, wiemy, że trzecia __qubit, w__stanie $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="60729-156">Jeśli mierzę i otrzymasz wynik 01, nadpozycja zwija, pozostawiając tylko warunki zgodne z tym wynikiem.</span><span class="sxs-lookup"><span data-stu-id="60729-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="60729-157">To $ \alpha\ket{011} + \beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="60729-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="60729-158">Można ją refaktoryzację do $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="60729-159">W związku z tym, jeśli mierzę pierwszy i drugi qubit jako 01, wiemy, że trzecia __qubit, w__stanie $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="60729-160">Jeśli mierzę i otrzymasz wynik 10, nadpozycja zwija, pozostawiając tylko warunki zgodne z tym wynikiem.</span><span class="sxs-lookup"><span data-stu-id="60729-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="60729-161">To jest $ \alpha\ket{100}-\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="60729-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="60729-162">Można ją refaktoryzację do $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="60729-163">W związku z tym, jeśli mierzę pierwszy i drugi qubit na 10, wiemy, że trzecia __qubit, w__stanie $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="60729-164">Jeśli mierzę i uzyskasz wynik 11, nadpozycja zwija, pozostawiając tylko warunki zgodne z tym wynikiem.</span><span class="sxs-lookup"><span data-stu-id="60729-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="60729-165">To jest $ \alpha\ket{111}-\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="60729-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="60729-166">Można ją refaktoryzację do $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="60729-167">W związku z tym, jeśli mierzę pierwszy i drugi qubit jako 11, wiemy, że trzecia __qubit, w__stanie $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="60729-168">Krok 4. interpretowanie wyniku</span><span class="sxs-lookup"><span data-stu-id="60729-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="60729-169">Jako przypomnienie oryginalna __wiadomość__ , którą chcemy wysłać, to:</span><span class="sxs-lookup"><span data-stu-id="60729-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="60729-170">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="60729-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="60729-171">Musimy __uzyskać qubit w__ tym stanie, tak aby otrzymany stan był zamierzony.</span><span class="sxs-lookup"><span data-stu-id="60729-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="60729-172">Jeśli wartość jest mierzona i otrzyma wynik __00, trzecia qubit, w__stanie $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="60729-173">Ponieważ jest to zamierzony __komunikat__, nie jest wymagana żadna zmiana.</span><span class="sxs-lookup"><span data-stu-id="60729-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="60729-174">W przypadku pomiaru i otrzymaniu wyniku 01 qubit __trzecia, w__stanie $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="60729-175">Różni się to od zamierzonego __komunikatu__, jednak zastosowanie niebramy daje nam żądany stan $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="60729-176">W przypadku pomiaru i uzyskaniu wyniku 10 trzecia __qubit, w__stanie $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="60729-177">Różni się to od zamierzonego __komunikatu__, ale zastosowanie bramy z daje nam żądany stan $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="60729-178">W przypadku pomiaru i uzyskaniu wyniku 11 qubit __trzecia, w__stanie $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="60729-179">Różni się to od zamierzonego __komunikatu__, ale zastosowanie bramy nie powoduje, że jest ona pożądanym stanem $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="60729-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="60729-180">Aby podsumować, jeśli mierzę i pierwszy qubit to 1, stosowana jest brama Z.</span><span class="sxs-lookup"><span data-stu-id="60729-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="60729-181">Jeśli mierzę, a drugi qubit wynosi 1, zostanie zastosowana Brama nie.</span><span class="sxs-lookup"><span data-stu-id="60729-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="60729-182">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="60729-182">Summary</span></span>
<span data-ttu-id="60729-183">Poniższa poniżej znajduje się książka tekstowa Quantum obwodu, który implementuje teleport.</span><span class="sxs-lookup"><span data-stu-id="60729-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="60729-184">Od lewej do prawej można zobaczyć:</span><span class="sxs-lookup"><span data-stu-id="60729-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="60729-185">Krok 1. Entangling tutaj i __w__ __tym miejscu__ , stosując bramę HADAMARD i bramę CNOT.</span><span class="sxs-lookup"><span data-stu-id="60729-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="60729-186">Krok 2. Wysyłanie __komunikatu__ przy użyciu bramy CNOT i bramy Hadamard.</span><span class="sxs-lookup"><span data-stu-id="60729-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="60729-187">Krok 3. przejęcie pomiaru pierwszego i drugiego qubits, __komunikatu__ i __tutaj__.</span><span class="sxs-lookup"><span data-stu-id="60729-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="60729-188">Krok 4. stosowanie bramy NOT bramowej lub Z, w zależności od wyniku pomiaru w kroku 3.</span><span class="sxs-lookup"><span data-stu-id="60729-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!["Teleport (MSG: qubit, tam: qubit): Unit"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="60729-190">Teleportowanie Quantum: kod</span><span class="sxs-lookup"><span data-stu-id="60729-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="60729-191">Mamy nasz Obwód na teleportowanie Quantum:</span><span class="sxs-lookup"><span data-stu-id="60729-191">We have our circuit for quantum teleportation:</span></span>

!["Teleport (MSG: qubit, tam: qubit): Unit"](~/media/teleportation.svg)

<span data-ttu-id="60729-193">Teraz możemy przetłumaczyć każdy z kroków tego obwodu Quantum na Q #.</span><span class="sxs-lookup"><span data-stu-id="60729-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="60729-194">Krok 0: definicja</span><span class="sxs-lookup"><span data-stu-id="60729-194">Step 0: Definition</span></span>
<span data-ttu-id="60729-195">Gdy wykonujesz teleportowanie, musimy znać __komunikat__ , który chcemy wysłać, i gdzie chcemy go wysłać.</span><span class="sxs-lookup"><span data-stu-id="60729-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="60729-196">Z tego powodu rozpoczynamy od zdefiniowania nowej operacji teleport, która ma dwa qubits jako argumenty `msg` i `there`:</span><span class="sxs-lookup"><span data-stu-id="60729-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="60729-197">Musimy również przydzielić `here` qubit, które są dostępne w bloku `using`:</span><span class="sxs-lookup"><span data-stu-id="60729-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="60729-198">Krok 1. Tworzenie stanu Entangled</span><span class="sxs-lookup"><span data-stu-id="60729-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="60729-199">Następnie możemy utworzyć parę Entangled między `here` i `there` przy użyciu operacji @"microsoft.quantum.intrinsic.h" i @"microsoft.quantum.intrinsic.cnot":</span><span class="sxs-lookup"><span data-stu-id="60729-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="60729-200">Krok 2. wysłanie wiadomości</span><span class="sxs-lookup"><span data-stu-id="60729-200">Step 2: Send the message</span></span>
<span data-ttu-id="60729-201">Następnie użyjemy kolejnych bram $ \operatorname{CNOT} $ i $H $, aby przenieść qubit wiadomości:</span><span class="sxs-lookup"><span data-stu-id="60729-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="60729-202">Krok 3 & 4: mierzenie i interpretacja wyniku</span><span class="sxs-lookup"><span data-stu-id="60729-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="60729-203">Na koniec używamy @"microsoft.quantum.intrinsic.m" do wykonywania pomiarów i wykonywania niezbędnych operacji bram w celu uzyskania żądanego stanu, zgodnie z instrukcją `if`:</span><span class="sxs-lookup"><span data-stu-id="60729-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="60729-204">Spowoduje to zakończenie definicji naszego operatora teleportowego, aby można było cofnąć alokację `here`, zakończyć treść i zakończyć operację.</span><span class="sxs-lookup"><span data-stu-id="60729-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
