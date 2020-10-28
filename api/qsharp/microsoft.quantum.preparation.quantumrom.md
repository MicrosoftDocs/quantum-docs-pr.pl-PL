---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722959"
---
# <a name="quantumrom-function"></a><span data-ttu-id="75eff-102">QuantumROM, funkcja</span><span class="sxs-lookup"><span data-stu-id="75eff-102">QuantumROM function</span></span>

<span data-ttu-id="75eff-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="75eff-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="75eff-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75eff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75eff-105">Używa techniki Quantum ROM do reprezentowania danej macierzy gęstości.</span><span class="sxs-lookup"><span data-stu-id="75eff-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="75eff-106">Po otrzymaniu listy $N $ współwydajnych $ \ alpha_j $, spowoduje to zwrócenie $U jednostkowej $, która używa metody Quantum-ROM do przygotowania przybliżenia $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ oczyszczania macierzy gęstości $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="75eff-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="75eff-107">W tym przybliżeniu błąd $ \epsilon $ jest taki, że $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ i $ \| \tilde\rho-\rho \| \le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="75eff-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="75eff-108">Innymi słowy, $ $ \begin{align} U\ket {0} ^ {\lceil\ Log_2 N\rceil} \ KET {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{garbage} _j}.</span><span class="sxs-lookup"><span data-stu-id="75eff-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="75eff-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="75eff-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="75eff-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="75eff-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="75eff-111">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="75eff-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="75eff-112">Błąd elementu docelowego $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="75eff-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="75eff-113">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="75eff-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="75eff-114">Tablica współczynników $N $, określająca prawdopodobieństwo Stanów bazowych.</span><span class="sxs-lookup"><span data-stu-id="75eff-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="75eff-115">Liczby ujemne $-\ alpha_j $ będą traktowane jako dodatnie $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="75eff-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="75eff-116">Output: (([int](xref:microsoft.quantum.lang-ref.int)[, int,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL)</span><span class="sxs-lookup"><span data-stu-id="75eff-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="75eff-117">Pierwszy parametr</span><span class="sxs-lookup"><span data-stu-id="75eff-117">First parameter</span></span>

<span data-ttu-id="75eff-118">Krotka `(x,(y,z))` `x = y + z` , gdzie jest łączna liczba przydzieloną qubits, `y` jest liczbą qubits dla `LittleEndian` rejestru i `z` jest liczbą qubits elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="75eff-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="75eff-119">Drugi parametr</span><span class="sxs-lookup"><span data-stu-id="75eff-119">Second parameter</span></span>

<span data-ttu-id="75eff-120">Jednostandardowa $ \ sum_j | \ alpha_j | $ tabeli współczynnika.</span><span class="sxs-lookup"><span data-stu-id="75eff-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="75eff-121">Trzeci parametr</span><span class="sxs-lookup"><span data-stu-id="75eff-121">Third parameter</span></span>

<span data-ttu-id="75eff-122">$U jednostki $.</span><span class="sxs-lookup"><span data-stu-id="75eff-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="75eff-123">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="75eff-123">References</span></span>

- <span data-ttu-id="75eff-124">Kodowanie elektronicznego spektrum w obwodach Quantum przy użyciu liniowej o złożoności T Babbush, Craig Gidney, Dominic W. Jagods, Nathana Wiebe, Jarrod McClean, Alexandru, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="75eff-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>