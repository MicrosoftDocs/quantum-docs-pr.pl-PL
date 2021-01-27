---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854304"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="4d535-102">PurifiedMixedState, funkcja</span><span class="sxs-lookup"><span data-stu-id="4d535-102">PurifiedMixedState function</span></span>

<span data-ttu-id="4d535-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="4d535-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="4d535-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d535-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d535-105">Zwraca operację, która przygotowuje oczyszczanie danego stanu mieszanego.</span><span class="sxs-lookup"><span data-stu-id="4d535-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="4d535-106">"Oczyszczony stan mieszany" odnosi się do Stanów formularza | ψ ⟩ = Σi √ pi | i ⟩ | garbagei ⟩ określony przez wektor współczynników {pi}.</span><span class="sxs-lookup"><span data-stu-id="4d535-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="4d535-107">Stany tego formularza można zmniejszyć do Stanów mieszanych ρ ≔ pi | i ⟩ ⟨ i | przez śledzenie w rejestrze "garbage" (oznacza to, że stan mieszany, który jest przekątną w oparciu o obliczenia).</span><span class="sxs-lookup"><span data-stu-id="4d535-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="4d535-108">Zobacz, https://arxiv.org/pdf/1805.03662.pdf?page=15 Aby uzyskać więcej dyskusji.</span><span class="sxs-lookup"><span data-stu-id="4d535-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="4d535-109">Opis</span><span class="sxs-lookup"><span data-stu-id="4d535-109">Description</span></span>

<span data-ttu-id="4d535-110">Używa techniki Quantum ROM do reprezentowania danej macierzy gęstości, zwracając tę reprezentację jako operację przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="4d535-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="4d535-111">W szczególności, podanej na liście $N $ współczynniki $ \ alpha_j $, ta funkcja zwraca operację, która używa techniki pamięci podręcznej Quantum w celu przygotowania przybliżenia $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ \begin{align}: \ sum_ {{j = 0} ^ {N-1} \ \rho {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $, gdzie każda $p _j $ jest przybliżeniem danego współczynnika $ \ alpha_j $, tak że $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ for each $j $.</span><span class="sxs-lookup"><span data-stu-id="4d535-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="4d535-112">Gdy przeszedł rejestr indeksów i rejestr qubits elementów bezużytecznych, we wstępnym stanie $ \ket {0} \ket{00\cdots 0} zwrócona operacja przygotowuje oba rejestry do oczyszczenia $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{align} $ $, takie jak resetowanie i cofanie przydziału rejestru elementów bezużytecznych, umożliwia przeprowadzenie żądanego przygotowania do poziomu błędu docelowego $ \epsilon</span><span class="sxs-lookup"><span data-stu-id="4d535-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="4d535-113">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4d535-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="4d535-114">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4d535-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4d535-115">Błąd elementu docelowego $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="4d535-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="4d535-116">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4d535-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4d535-117">Tablica współczynników $N $, określająca prawdopodobieństwo Stanów bazowych.</span><span class="sxs-lookup"><span data-stu-id="4d535-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="4d535-118">Liczby ujemne $-\ alpha_j $ będą traktowane jako dodatnie $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="4d535-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="4d535-119">Wynik: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="4d535-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="4d535-120">Operacja, która przygotowuje $ \tilde \rho $ jako oczyszczanie do wspólnych indeksów i rejestrów elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="4d535-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="example"></a><span data-ttu-id="4d535-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="4d535-121">Example</span></span>

<span data-ttu-id="4d535-122">Poniższy fragment kodu przygotowuje oczyszczenie stanu $3 $-qubit $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, gdzie $ \vec\alpha = (1.0, 2,0, 3,0, 4,0, 5,0) $, a błąd docelowy to $10 ^ {-3} $:</span><span class="sxs-lookup"><span data-stu-id="4d535-122">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, and the target error is $10^{-3}$:</span></span>

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="4d535-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4d535-123">Remarks</span></span>

<span data-ttu-id="4d535-124">Współczynniki przekazane do tej operacji są znormalizowane zgodnie z 1 normą, w taki sposób, że współczynniki są zawsze traktowane do opisywania prawidłowego rozkładu prawdopodobieństwa kategorii.</span><span class="sxs-lookup"><span data-stu-id="4d535-124">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="4d535-125">Odwołania</span><span class="sxs-lookup"><span data-stu-id="4d535-125">References</span></span>

- <span data-ttu-id="4d535-126">Kodowanie elektronicznego spektrum w obwodach Quantum przy użyciu liniowej o złożoności T Babbush, Craig Gidney, Dominic W. Jagods, Nathana Wiebe, Jarrod McClean, Alexandru, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="4d535-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="4d535-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4d535-127">See Also</span></span>

- [<span data-ttu-id="4d535-128">Microsoft. Quantum. przygotowaniu. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="4d535-128">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)