---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229957"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="6857e-102">PurifiedMixedStateWithData, funkcja</span><span class="sxs-lookup"><span data-stu-id="6857e-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="6857e-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="6857e-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="6857e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6857e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6857e-105">Zwraca operację, która przygotowuje oczyszczanie danego stanu mieszanego, Entangled z rejestrem reprezentującym daną kolekcję danych.</span><span class="sxs-lookup"><span data-stu-id="6857e-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="6857e-106">"Oczyszczony stan mieszany z danymi" odnosi się do stanu formularza Σi √ pi | i ⟩ | XI ⟩ | garbagei ⟩, gdzie każda XI to bitstring kodowanie dodatkowych danych skojarzonych z rejestrem | i ⟩.</span><span class="sxs-lookup"><span data-stu-id="6857e-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="6857e-107">Zobacz, https://arxiv.org/pdf/1805.03662.pdf?page=15 Aby uzyskać więcej dyskusji.</span><span class="sxs-lookup"><span data-stu-id="6857e-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="6857e-108">Opis</span><span class="sxs-lookup"><span data-stu-id="6857e-108">Description</span></span>

<span data-ttu-id="6857e-109">Używa techniki Quantum ROM do reprezentowania danej macierzy gęstości, zwracając tę reprezentację jako operację przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="6857e-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="6857e-110">W szczególności, uwzględniając listę $N $ współwydajne $ \ alpha_j $ oraz bitstring $ \vec{x}_j $ skojarzone z każdym czynnikiem, ta funkcja zwraca operację wykorzystującą technikę pamięci podręcznej Quantum do przygotowania przybliżenia $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ stanu mieszanego $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ Frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $, gdzie każda $p _j $ to przybliżenie do danego współczynnika $ \ alpha_j $ tak, że $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ for each $j $.</span><span class="sxs-lookup"><span data-stu-id="6857e-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="6857e-111">Gdy przeszedł rejestr indeksów i rejestr elementów bezużytecznych qubits, początkowo w stanie $ \ket {0} \ket{00\cdots 0}, zwrócona operacja przygotowuje oba rejestry do oczyszczenia $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}, \end{align} $ $, takich jak resetowanie i cofanie przydziału rejestru elementów bezużytecznych powoduje, że w przypadku błędu docelowego $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="6857e-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="6857e-112">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6857e-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="6857e-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6857e-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6857e-114">Błąd elementu docelowego $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="6857e-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="6857e-115">współczynniki: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []</span><span class="sxs-lookup"><span data-stu-id="6857e-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="6857e-116">Tablica $N współczynników, określająca prawdopodobieństwo Stanów bazowych, wraz z bitstring $ \vec{x} _j $ skojarzonymi z każdym czynnikiem.</span><span class="sxs-lookup"><span data-stu-id="6857e-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="6857e-117">Liczby ujemne $-\ alpha_j $ będą traktowane jako dodatnie $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="6857e-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="6857e-118">Wynik: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="6857e-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="6857e-119">Operacja, która przygotowuje $ \tilde \rho $ jako oczyszczanie do wspólnych indeksów i rejestrów elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="6857e-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="6857e-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6857e-120">Remarks</span></span>

<span data-ttu-id="6857e-121">Współczynniki przekazane do tej operacji są znormalizowane zgodnie z 1 normą, w taki sposób, że współczynniki są zawsze traktowane do opisywania prawidłowego rozkładu prawdopodobieństwa kategorii.</span><span class="sxs-lookup"><span data-stu-id="6857e-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="6857e-122">Odwołania</span><span class="sxs-lookup"><span data-stu-id="6857e-122">References</span></span>

- <span data-ttu-id="6857e-123">Kodowanie elektronicznego spektrum w obwodach Quantum przy użyciu liniowej o złożoności T Babbush, Craig Gidney, Dominic W. Jagods, Nathana Wiebe, Jarrod McClean, Alexandru, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="6857e-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="6857e-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6857e-124">See Also</span></span>

- [<span data-ttu-id="6857e-125">Microsoft. Quantum. przygotowaniu. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="6857e-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)