---
title: Pomiary Pauli
description: Dowiedz się, jak korzystać z operacji pomiaru pojedynczego i qubit Pauli.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269477"
---
# <a name="pauli-measurements"></a><span data-ttu-id="f9127-103">Pomiary Pauli</span><span class="sxs-lookup"><span data-stu-id="f9127-103">Pauli Measurements</span></span>

<span data-ttu-id="f9127-104">W poprzednich dyskusjach koncentrujemy się na obliczaniu pomiarów bazowych.</span><span class="sxs-lookup"><span data-stu-id="f9127-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="f9127-105">W rzeczywistości istnieją inne typowe pomiary związane z przetwarzaniem jednostek Quantum, które z perspektywy notacji są wygodne do wyrażania na podstawie obliczeniowych pomiarów.</span><span class="sxs-lookup"><span data-stu-id="f9127-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="f9127-106">Podczas pracy z pytaniami Q # najbardziej typowym rodzajem pomiarów, które będą używane, prawdopodobnie będą *pomiary Pauli*, które uogólnią obliczenia obliczające pomiary w celu uwzględnienia pomiarów w innych bazach i parzystości między różnymi qubits.</span><span class="sxs-lookup"><span data-stu-id="f9127-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="f9127-107">W takich przypadkach często omawia się pomiar pomiaru operatora Pauli, w ogólności operatora, takiego jak $X, Y, Z $ lub $Z \otimes Z, x \otimes x, x \otimes Y $ i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="f9127-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="f9127-108">W pytaniach Q # qubit operatory Pauli są ogólnie reprezentowane przez tablice typu `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="f9127-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="f9127-109">Na przykład, aby reprezentować $X \otimes Z \otimes Y $ , można użyć tablicy `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="f9127-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="f9127-110">Omawianie pomiaru w warunkach operatorów Pauli jest szczególnie powszechne w podpolu korekcji błędów Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9127-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="f9127-111">W pytaniach Q # przestrzegamy podobnej Konwencji; teraz wyjaśnimy ten alternatywny widok pomiarów.</span><span class="sxs-lookup"><span data-stu-id="f9127-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="f9127-112">Przed napisaniem szczegółowych informacji o tym, jak sądzisz o pomiarze Pauli, warto zastanowić się nad tym, co mierzy jeden qubit wewnątrz komputera Quantum w stanie Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9127-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="f9127-113">Załóżmy, że mamy $n $ qubit Quantum, a następnie zmierzenie jednego qubitu natychmiast reguły mające na celu odłożenia, $ że stanem może być wartość $2 ^ n.</span><span class="sxs-lookup"><span data-stu-id="f9127-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="f9127-114">Innymi słowy, pomiar projektuje stan Quantum na jedną z dwóch miejsc.</span><span class="sxs-lookup"><span data-stu-id="f9127-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="f9127-115">Możemy uogólnić sposób, w jaki myślimy o pomiarach, aby odzwierciedlić ten Intuition.</span><span class="sxs-lookup"><span data-stu-id="f9127-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="f9127-116">Aby zwięzłie zidentyfikować te podobszary, należy zapoznać się z językiem.</span><span class="sxs-lookup"><span data-stu-id="f9127-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="f9127-117">Jednym ze sposobów opisywania dwóch podobszarów jest określenie ich za pośrednictwem macierzy, która ma dwie unikalne eigenvalues, podejmowane przez Konwencję jako $ \Pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="f9127-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="f9127-118">Aby zapoznać się z prostym przykładem opisywania obszarów w ten sposób, należy rozważyć $Z $ :</span><span class="sxs-lookup"><span data-stu-id="f9127-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="f9127-119">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-119">$$ \begin{align}</span></span>
  <span data-ttu-id="f9127-120">Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="f9127-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="f9127-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-121">\end{align}</span></span>
$$

<span data-ttu-id="f9127-122">Odczytując elementy ukośne macierzy Pauli $Z $ , widzimy, że $Z $ ma dwa eigenvectors, $ \ket{0 } $ i $ \ket{1 } $, z odpowiednimi eigenvalues $ \Pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="f9127-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="f9127-123">W takim przypadku, jeśli mierzę qubit i uzyskamy `Zero` (odpowiadający stanowi $ \ket{0 } $), wiemy, że stan naszego qubit to $ + 1 $ eigenstate $ operatora $Z.</span><span class="sxs-lookup"><span data-stu-id="f9127-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="f9127-124">Podobnie, jeśli uzyskamy `One` , wiemy, że stan naszego qubit to $-1 $ eigenstate $Z $ .</span><span class="sxs-lookup"><span data-stu-id="f9127-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="f9127-125">Ten proces jest określany w języku Pauli pomiarów jako "pomiar Pauli $Z $ " i jest całkowicie równoważny do wykonywania obliczeniowej miary.</span><span class="sxs-lookup"><span data-stu-id="f9127-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="f9127-126">Każda \times macierz $2 2 $ , która jest przekształceniem jednostkowym $Z $ również spełnia te kryteria.</span><span class="sxs-lookup"><span data-stu-id="f9127-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="f9127-127">Oznacza to, że możemy również użyć macierzy $A = U ^ \dagger Z U $ , gdzie $U $ to każda inna macierz jednostkowa, aby udostępnić macierz, która definiuje dwa wyniki pomiaru w jego $ \Pm 1 $ eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="f9127-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="f9127-128">Notacja Pauli jest odwołująca się do tej równoważnej jednostki, identyfikując $X, Y, Z $ pomiarów jako równoważne pomiary, które mogą wykonać, aby uzyskać informacje z qubit.</span><span class="sxs-lookup"><span data-stu-id="f9127-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="f9127-129">Te pomiary są podane poniżej dla wygody.</span><span class="sxs-lookup"><span data-stu-id="f9127-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="f9127-130">Pomiar Pauli</span><span class="sxs-lookup"><span data-stu-id="f9127-130">Pauli Measurement</span></span>  |<span data-ttu-id="f9127-131">Transformacja jednostkowa</span><span class="sxs-lookup"><span data-stu-id="f9127-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="f9127-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="f9127-132">$Z$</span></span>               | <span data-ttu-id="f9127-133">$ \boldone$</span><span class="sxs-lookup"><span data-stu-id="f9127-133">$\boldone$</span></span>             |
| <span data-ttu-id="f9127-134">$X$</span><span class="sxs-lookup"><span data-stu-id="f9127-134">$X$</span></span>               | <span data-ttu-id="f9127-135">$H$</span><span class="sxs-lookup"><span data-stu-id="f9127-135">$H$</span></span>                    |
| <span data-ttu-id="f9127-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="f9127-136">$Y$</span></span>               | <span data-ttu-id="f9127-137">$HS ^ {\dagger}$</span><span class="sxs-lookup"><span data-stu-id="f9127-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="f9127-138">Oznacza to, że przy użyciu tego języka "miara $Y $ " jest równoznaczna z zastosowaniem $HS ^ \dagger, $ a następnie mierzenia w oparciu o obliczenia, gdzie [`S`](xref:microsoft.quantum.intrinsic.s) jest wewnętrzną operacją Quantum czasami nazywaną "bramą fazowy" i może być symulowane przez macierz jednostkową</span><span class="sxs-lookup"><span data-stu-id="f9127-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="f9127-139">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-139">$$ \begin{align}</span></span>
    <span data-ttu-id="f9127-140">S = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f9127-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="f9127-141">1 & 0 \\ \\ 0 & i \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="f9127-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="f9127-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-142">\end{align}</span></span>
$$

<span data-ttu-id="f9127-143">Jest to również równoznaczne z zastosowaniem $HS ^ \dagger $ do wektora stanu Quantum, a następnie zmierzenie $Z, w taki sposób, $ że Następująca operacja jest równoznaczna z `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="f9127-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="f9127-144">Prawidłowy stan można znaleźć w wyniku przekształcenia z powrotem do podstawy obliczeniowej, co oznacza zastosowanie $SH $ do wektora stanu Quantum; w powyższym fragmencie, przekształcenie z powrotem do podstawy obliczeniowej jest obsługiwane automatycznie przez użycie `within … apply` bloku.</span><span class="sxs-lookup"><span data-stu-id="f9127-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="f9127-145">W polu Q # wyrażamy wynik---to znaczy, że klasyczne informacje wyodrębnione ze względu na współdziałanie ze stanem---są `Result` określane przez wartość $j \In \\ {\Texttt{zero } , \texttt{one } \\ } $ wskazującą, czy wynik znajduje się w $ (-1) ^ j $ eigenspace operatora Pauli.</span><span class="sxs-lookup"><span data-stu-id="f9127-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="f9127-146">Pomiary z wieloma qubitami</span><span class="sxs-lookup"><span data-stu-id="f9127-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="f9127-147">Pomiary operatorów Pauli wieloqubitowych są zdefiniowane w podobny sposób, jak pokazano w:</span><span class="sxs-lookup"><span data-stu-id="f9127-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="f9127-148">$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1&0 0&0&\\\\ 0&1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="f9127-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="f9127-149">W ten sposób produkty dwuetapowe dwóch operatorów Pauli $Z $ tworzą macierz składającą się z dwóch spacji składających się z elementów $ + 1 $ i $-1 $ eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="f9127-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="f9127-150">Podobnie jak w przypadku pojedynczej qubit, oba stanowią pół obszaru, co połowa dostępnego miejsca wektorowego należy do $ + 1 $ eigenspace i pozostała połowa do $-1 $ eigenspace.</span><span class="sxs-lookup"><span data-stu-id="f9127-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="f9127-151">Ogólnie rzecz biorąc, można łatwo zapoznać się z definicją iloczynu dwuczęściowego, że każdy dwuczęściowy produkt operatorów Pauli-$Z $ i tożsamość również przestrzega tego.</span><span class="sxs-lookup"><span data-stu-id="f9127-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="f9127-152">Na przykład</span><span class="sxs-lookup"><span data-stu-id="f9127-152">For example,</span></span>

<span data-ttu-id="f9127-153">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-153">$$ \begin{align}</span></span>
    <span data-ttu-id="f9127-154">Z \otimes \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f9127-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="f9127-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="f9127-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="f9127-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-156">\end{align}</span></span>
$$

<span data-ttu-id="f9127-157">Tak jak wcześniej, każda jednostkowa transformacja takich macierzy również opisuje dwie spacje oznaczone przez $ \Pm 1 $ eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="f9127-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="f9127-158">Na przykład $X \otimes X = h \otimes h (z \otimes ) h h \otimes $ od tożsamości, która $Z = HXH $ .</span><span class="sxs-lookup"><span data-stu-id="f9127-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="f9127-159">Podobnie jak w przypadku qubit, wszystkie dwie qubit Pauli-pomiary mogą być zapisywane jako $U ^ \dagger (Z \otimes \id) U $ dla $4 \times 4 $ macierzy jednostkowych $U $ .</span><span class="sxs-lookup"><span data-stu-id="f9127-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="f9127-160">Wyliczmy przekształcenia w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="f9127-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="f9127-161">W poniższej tabeli użyto $ \operatorname{SWAP } $ do wskazania macierzy $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="f9127-162">\operatorname{SWAP } & = \left (\begin{Matrix}</span><span class="sxs-lookup"><span data-stu-id="f9127-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="f9127-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="f9127-164">$ $ używany do symulowania operacji wewnętrznej [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="f9127-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="f9127-165">Pomiar Pauli</span><span class="sxs-lookup"><span data-stu-id="f9127-165">Pauli Measurement</span></span>     |<span data-ttu-id="f9127-166">Transformacja jednostkowa</span><span class="sxs-lookup"><span data-stu-id="f9127-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="f9127-167">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="f9127-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="f9127-168">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="f9127-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="f9127-169">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="f9127-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="f9127-170">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="f9127-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="f9127-171">$X \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="f9127-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="f9127-172">$H \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="f9127-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="f9127-173">$Y \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="f9127-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="f9127-174">$HS ^ \dagger \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="f9127-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="f9127-175">$ \boldone \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="f9127-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="f9127-176">$ \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="f9127-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="f9127-177">$ \boldone \otimes X$</span><span class="sxs-lookup"><span data-stu-id="f9127-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="f9127-178">$ (H \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="f9127-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="f9127-179">$ \boldone \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="f9127-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="f9127-180">$ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="f9127-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="f9127-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="f9127-181">$Z\otimes Z$</span></span> | <span data-ttu-id="f9127-182">$ \operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="f9127-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="f9127-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="f9127-183">$X\otimes Z$</span></span> | <span data-ttu-id="f9127-184">$ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="f9127-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="f9127-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="f9127-185">$Y\otimes Z$</span></span> | <span data-ttu-id="f9127-186">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="f9127-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="f9127-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="f9127-187">$Z\otimes X$</span></span> | <span data-ttu-id="f9127-188">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="f9127-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="f9127-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="f9127-189">$X\otimes X$</span></span> | <span data-ttu-id="f9127-190">$ \operatorname{CNOT } \_ {10 } (h \otimes h) $</span><span class="sxs-lookup"><span data-stu-id="f9127-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="f9127-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="f9127-191">$Y\otimes X$</span></span> | <span data-ttu-id="f9127-192">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="f9127-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="f9127-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="f9127-193">$Z\otimes Y$</span></span> | <span data-ttu-id="f9127-194">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="f9127-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="f9127-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="f9127-195">$X\otimes Y$</span></span> | <span data-ttu-id="f9127-196">$ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="f9127-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="f9127-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="f9127-197">$Y\otimes Y$</span></span> | <span data-ttu-id="f9127-198">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="f9127-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="f9127-199">W tym miejscu [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operacja zostanie wyświetlona z następującej przyczyny.</span><span class="sxs-lookup"><span data-stu-id="f9127-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="f9127-200">Każda miara Pauli, która nie obejmuje macierzy $ \boldone, $ jest równoważna do jednostki do $Z \otimes z z $ powyższego powodu.</span><span class="sxs-lookup"><span data-stu-id="f9127-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="f9127-201">Eigenvalues z $Z \otimes z $ są zależne od parzystości qubits, która składa się z każdego wektora obliczeniowego, a operacje kontrolowane nie służą do obliczenia tej parzystości i zapisania jej w pierwszym bitach.</span><span class="sxs-lookup"><span data-stu-id="f9127-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="f9127-202">Następnie po przemierzeniu pierwszego bitu możemy odzyskać tożsamość wynikowego, który jest równoważny do mierzenia operatora Pauli.</span><span class="sxs-lookup"><span data-stu-id="f9127-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="f9127-203">Jedna dodatkowa Uwaga: Chociaż może być skłonny do założenia, że pomiary $Z \otimes z $ są takie same jak pomiary sekwencyjne $Z \otimes \mathbb{1 $, } a następnie $ \mathbb{1 } \otimes Z $ , to założenie miałoby wartość false.</span><span class="sxs-lookup"><span data-stu-id="f9127-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="f9127-204">Powodem jest to, że pomiar $Z \otimes z $ projektów w stanie Quantum do wartości $ + 1 $ lub $-1 $ eigenstate tych operatorów.</span><span class="sxs-lookup"><span data-stu-id="f9127-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="f9127-205">Pomiar $Z \otimes \mathbb{1 } $, a następnie $ \Mathbb{1 } \otimes z $ projektów, wektor stanu Quantum najpierw w połowie miejsca $Z \otimes \mathbb{1 } $, a następnie do połowy miejsca na $ \mathbb{1 } \otimes z $ . Ponieważ istnieją cztery wektory obliczeniowe, przeprowadzenie obydwu pomiarów zmniejsza stan do kwartału, a tym samym redukuje go do jednego wektora obliczanego na podstawie.</span><span class="sxs-lookup"><span data-stu-id="f9127-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="f9127-206">Korelacje między qubits</span><span class="sxs-lookup"><span data-stu-id="f9127-206">Correlations between qubits</span></span>
<span data-ttu-id="f9127-207">Innym sposobem na pomiar iloczynów ilościowych macierzy Pauli, takich jak $X \otimes X $ lub $Z \otimes Z $ , jest to, że pomiary umożliwiają przeszukanie informacji przechowywanych w korelacji między tymi dwoma qubits.</span><span class="sxs-lookup"><span data-stu-id="f9127-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="f9127-208">Pomiar $X \otimes \id $ umożliwia przeglądanie informacji przechowywanych lokalnie w pierwszej qubit.</span><span class="sxs-lookup"><span data-stu-id="f9127-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="f9127-209">Mimo że oba typy pomiarów są równie cenne w przypadku obliczeń opartych na usługach Quantum</span><span class="sxs-lookup"><span data-stu-id="f9127-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="f9127-210">Wykaże, że w ramach przetwarzania Quantum, często informacje, które chcesz poznać, nie są przechowywane w żadnym z pojedynczych qubit, ale raczej są przechowywane nielokalnie we wszystkich qubitsach i dlatego tylko przez ich przechodzenie przez wspólną miarę (np. $Z \otimes Z $ ) czy te informacje stają się manifestem.</span><span class="sxs-lookup"><span data-stu-id="f9127-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="f9127-211">Na przykład w przypadku korekcji błędów często chcemy dowiedzieć się, jaki błąd wystąpił podczas uczenia niczego o stanie, który próbujesz chronić.</span><span class="sxs-lookup"><span data-stu-id="f9127-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="f9127-212">[Przykładowy kod przerzucania bitów](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) przedstawia przykład sposobu, w jaki można to zrobić przy użyciu pomiarów, takich jak $Z \otimes Z \otimes \id $ i $ \id \Otimes z \otimes z $ .</span><span class="sxs-lookup"><span data-stu-id="f9127-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="f9127-213">Można również mierzyć dowolne operatory Pauli, takie jak $X \otimes Y \Otimes Z \otimes \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="f9127-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="f9127-214">Wszystkie te produkty dwuskładnikowe operatorów Pauli mają tylko dwa eigenvalues $ \Pm 1 $ , a oba eigenspaces stanowią pół miejsca całego obszaru wektora.</span><span class="sxs-lookup"><span data-stu-id="f9127-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="f9127-215">W ten sposób są one zgodne z wymaganiami określonymi powyżej.</span><span class="sxs-lookup"><span data-stu-id="f9127-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="f9127-216">W Q #, takie pomiary zwracają $j, $ Jeśli pomiar daje wynik w eigenspace znak $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="f9127-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="f9127-217">Pauli pomiary jako Wbudowana funkcja w Q # jest przydatne, ponieważ pomiary takich operatorów wymagają długich łańcuchów kontrolowanych i nieopartych na bramach i transformacji bazowych, aby opisać bramę diagonalizing $U, która jest $ niezbędna do wyrażenia działania jako iloczyn dwuskładnikowego $Z $ i $ \id $ . Aby określić, że chcesz wykonać jedną z tych wstępnie zdefiniowanych pomiarów, nie musisz martwić się o to, jak przekształcić swoją podstawę, tak aby pomiar bazowy obliczał informacje.</span><span class="sxs-lookup"><span data-stu-id="f9127-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="f9127-218">W programie Q # wszystkie wymagane przekształcenia podstawowe są obsługiwane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="f9127-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="f9127-219">Aby uzyskać więcej informacji, zobacz [`Measure`](xref:microsoft.quantum.intrinsic.measure) i [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operacje.</span><span class="sxs-lookup"><span data-stu-id="f9127-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="f9127-220">Theorem bez klonowania</span><span class="sxs-lookup"><span data-stu-id="f9127-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="f9127-221">Informacje o Quantum są zaawansowane.</span><span class="sxs-lookup"><span data-stu-id="f9127-221">Quantum information is powerful.</span></span>
<span data-ttu-id="f9127-222">Umożliwia nam wykonywanie niezwykłych rzeczy, takich jak liczba czynników, które są wykładniczo szybsze niż najlepsze znane klasyczne algorytmy, lub efektywnie symuluje skorelowane systemy elektronów, które w sposób klasyczny wymagają wykładniczego kosztu, aby symulować dokładne symulacje.</span><span class="sxs-lookup"><span data-stu-id="f9127-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="f9127-223">Istnieją jednak ograniczenia dotyczące mocy obliczeniowej Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9127-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="f9127-224">Takie ograniczenie jest określone przez *theorem bez klonowania*.</span><span class="sxs-lookup"><span data-stu-id="f9127-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="f9127-225">Theorem No-kloning ma nazwę aptly.</span><span class="sxs-lookup"><span data-stu-id="f9127-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="f9127-226">Nie zezwala na klonowanie ogólnych Stanów Quantum przez komputer Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9127-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="f9127-227">Potwierdzenie theorem jest niezwykle proste.</span><span class="sxs-lookup"><span data-stu-id="f9127-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="f9127-228">Gdy Pełna weryfikacja theorem nie jest w stanie nieco zbyt technicznym w naszej dyskusji, w przypadku braku dodatkowych qubits pomocniczych znajduje się w naszym zakresie (pomocnicze qubits to qubits używany do wyznaczania miejsca podczas obliczeń i są łatwe w użyciu i zarządzane w usłudze Q [#).](xref:microsoft.quantum.guide.qubits#borrowed-qubits)</span><span class="sxs-lookup"><span data-stu-id="f9127-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="f9127-229">W przypadku takiego komputera z systemem Quantum Operacja klonowania musi być opisana przez macierz jednostkową.</span><span class="sxs-lookup"><span data-stu-id="f9127-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="f9127-230">Nie można wymusić pomiaru, ponieważ spowodowałoby to uszkodzenie stanu Quantum, który próbujemy sklonować.</span><span class="sxs-lookup"><span data-stu-id="f9127-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="f9127-231">Aby symulować operację klonowania, chcemy, aby macierz jednostkowa używała właściwości $ $ U \ket { \psi } \ket{0 } = \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="f9127-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="f9127-232">$ $ dla dowolnego stanu $ \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="f9127-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="f9127-233">Właściwość liniowości mnożenia macierzy wskazuje, że dla każdego drugiego stanu Quantum $ \ket { \phi } $,</span><span class="sxs-lookup"><span data-stu-id="f9127-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="f9127-234">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-234">$$ \begin{align}</span></span>
    <span data-ttu-id="f9127-235">U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi \right } ) \right] \ket{0}</span><span class="sxs-lookup"><span data-stu-id="f9127-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="f9127-236">& = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="f9127-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="f9127-237">+ \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="f9127-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="f9127-238">\right) \\ \\ & \ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right).</span><span class="sxs-lookup"><span data-stu-id="f9127-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="f9127-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f9127-239">\end{align}</span></span>
$$

<span data-ttu-id="f9127-240">Zapewnia to podstawowe Intuition za theorem bez klonowania: każde urządzenie, które kopiuje nieznany stan Quantum, musi powodować błędy w co najmniej niektórych stanach, które kopiuje.</span><span class="sxs-lookup"><span data-stu-id="f9127-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="f9127-241">Podczas gdy klucz założono, że Cloner działa liniowo na stanie wprowadzania, może zostać naruszony poprzez dodanie i pomiar pomocniczej qubits, takie interakcje także przecieki informacji o systemie za pomocą statystyk pomiarów i zapobiegania dokładnemu klonowi w takich przypadkach.</span><span class="sxs-lookup"><span data-stu-id="f9127-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="f9127-242">Aby uzyskać bardziej szczegółowe informacje, zobacz theorem No-kloning, [Aby uzyskać więcej informacji](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="f9127-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="f9127-243">Theorema bez klonowania jest ważna w przypadku jakościowej interpretacji obliczeń opartych na usłudze Quantum, ponieważ w przypadku niedrogiego klonowania Stanów Quantum można udzielić prawie magicalej możliwości uczenia się od Stanów Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9127-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="f9127-244">Rzeczywiście można naruszyć zasadę niepewności vaunted Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="f9127-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="f9127-245">Alternatywnie można użyć optymalnej Cloner do pobrania pojedynczego przykładu ze złożonej dystrybucji Quantum i dowiedzieć się wszystkiego, co może być możliwe, aby poznać tę dystrybucję z zaledwie jednego przykładu.</span><span class="sxs-lookup"><span data-stu-id="f9127-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="f9127-246">Przypomina to Przerzucanie monet i obserwowanie głowic, a następnie na poinformowanie przyjaciela o wyniku odpowiedzi "Ah" dystrybucja tej monety musi być Bernoulliego z $p = 0.512643 \ ldots $ ! "</span><span class="sxs-lookup"><span data-stu-id="f9127-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="f9127-247">Taka instrukcja byłaby niesensicala, ponieważ jeden bit informacji (wynik Head) po prostu nie może udostępnić wielu bitów informacji potrzebnych do zakodowania dystrybucji bez poważnych informacji.</span><span class="sxs-lookup"><span data-stu-id="f9127-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="f9127-248">Podobnie, bez wcześniejszej informacji, nie możemy idealnie sklonować stanu Quantum, tak samo, jak nie można przygotować kompletu takich monet bez znajomości $p $ .</span><span class="sxs-lookup"><span data-stu-id="f9127-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="f9127-249">Informacje nie są bezpłatne w obliczeniach Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9127-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="f9127-250">Każda qubit mierzona w postaci pojedynczej informacji, a theorem bez klonowania nie wykazuje, że nie ma tylne wejście, które mogą być wykorzystywane w celu założenia zasadniczego kompromisu między informacjami uzyskanymi na temat systemu a zaistniałymi zakłóceniami.</span><span class="sxs-lookup"><span data-stu-id="f9127-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
