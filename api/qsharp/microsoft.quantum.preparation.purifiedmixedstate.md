---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230025"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="d555b-102">PurifiedMixedState, funkcja</span><span class="sxs-lookup"><span data-stu-id="d555b-102">PurifiedMixedState function</span></span>

<span data-ttu-id="d555b-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d555b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d555b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d555b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d555b-105">Zwraca operację, która przygotowuje oczyszczanie danego stanu mieszanego.</span><span class="sxs-lookup"><span data-stu-id="d555b-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="d555b-106">"Oczyszczony stan mieszany" odnosi się do Stanów formularza | ψ ⟩ = Σi √ pi | i ⟩ | garbagei ⟩ określony przez wektor współczynników {pi}.</span><span class="sxs-lookup"><span data-stu-id="d555b-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="d555b-107">Stany tego formularza można zmniejszyć do Stanów mieszanych ρ ≔ pi | i ⟩ ⟨ i | przez śledzenie w rejestrze "garbage" (oznacza to, że stan mieszany, który jest przekątną w oparciu o obliczenia).</span><span class="sxs-lookup"><span data-stu-id="d555b-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="d555b-108">Zobacz, https://arxiv.org/pdf/1805.03662.pdf?page=15 Aby uzyskać więcej dyskusji.</span><span class="sxs-lookup"><span data-stu-id="d555b-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="d555b-109">Opis</span><span class="sxs-lookup"><span data-stu-id="d555b-109">Description</span></span>

<span data-ttu-id="d555b-110">Używa techniki Quantum ROM do reprezentowania danej macierzy gęstości, zwracając tę reprezentację jako operację przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="d555b-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="d555b-111">W szczególności, podanej na liście $N $ współczynniki $ \ alpha_j $, ta funkcja zwraca operację, która używa techniki pamięci podręcznej Quantum w celu przygotowania przybliżenia $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ \begin{align}: \ sum_ {{j = 0} ^ {N-1} \ \rho {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $, gdzie każda $p _j $ jest przybliżeniem danego współczynnika $ \ alpha_j $, tak że $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ for each $j $.</span><span class="sxs-lookup"><span data-stu-id="d555b-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="d555b-112">Gdy przeszedł rejestr indeksów i rejestr qubits elementów bezużytecznych, we wstępnym stanie $ \ket {0} \ket{00\cdots 0} zwrócona operacja przygotowuje oba rejestry do oczyszczenia $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{align} $ $, takie jak resetowanie i cofanie przydziału rejestru elementów bezużytecznych, umożliwia przeprowadzenie żądanego przygotowania do poziomu błędu docelowego $ \epsilon</span><span class="sxs-lookup"><span data-stu-id="d555b-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="d555b-113">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d555b-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="d555b-114">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d555b-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d555b-115">Błąd elementu docelowego $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="d555b-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="d555b-116">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d555b-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d555b-117">Tablica współczynników $N $, określająca prawdopodobieństwo Stanów bazowych.</span><span class="sxs-lookup"><span data-stu-id="d555b-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="d555b-118">Liczby ujemne $-\ alpha_j $ będą traktowane jako dodatnie $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="d555b-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="d555b-119">Wynik: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="d555b-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="d555b-120">Operacja, która przygotowuje $ \tilde \rho $ jako oczyszczanie do wspólnych indeksów i rejestrów elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="d555b-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="d555b-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d555b-121">Remarks</span></span>

<span data-ttu-id="d555b-122">Współczynniki przekazane do tej operacji są znormalizowane zgodnie z 1 normą, w taki sposób, że współczynniki są zawsze traktowane do opisywania prawidłowego rozkładu prawdopodobieństwa kategorii.</span><span class="sxs-lookup"><span data-stu-id="d555b-122">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="d555b-123">Odwołania</span><span class="sxs-lookup"><span data-stu-id="d555b-123">References</span></span>

- <span data-ttu-id="d555b-124">Kodowanie elektronicznego spektrum w obwodach Quantum przy użyciu liniowej o złożoności T Babbush, Craig Gidney, Dominic W. Jagods, Nathana Wiebe, Jarrod McClean, Alexandru, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="d555b-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="d555b-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d555b-125">See Also</span></span>

- [<span data-ttu-id="d555b-126">Microsoft. Quantum. przygotowaniu. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="d555b-126">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)