---
title: 'Korzystanie z biblioteki liczbowej Microsoft Q #'
description: Dowiedz się więcej o typach i operacjach dostępnych w bibliotece liczb Quantum firmy Microsoft.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82677105"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="c1229-103">Korzystanie z biblioteki liczb</span><span class="sxs-lookup"><span data-stu-id="c1229-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="c1229-104">Omówienie</span><span class="sxs-lookup"><span data-stu-id="c1229-104">Overview</span></span>

<span data-ttu-id="c1229-105">Biblioteka liczbowa składa się z trzech składników</span><span class="sxs-lookup"><span data-stu-id="c1229-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="c1229-106">**Podstawowa liczba całkowita arytmetyczna** z dodającymi liczby całkowite i komparatorów</span><span class="sxs-lookup"><span data-stu-id="c1229-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="c1229-107">**Funkcja całkowita wysokiego poziomu** , która jest oparta na podstawowej funkcji; obejmuje mnożenie, dzielenie, inwersję itp.  w przypadku liczb całkowitych ze znakiem i bez znaku.</span><span class="sxs-lookup"><span data-stu-id="c1229-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="c1229-108">**Funkcja arytmetyczna stałego punktu** z inicjalizacją, dodawaniem, mnożeniem, wzajemnym, wieloznacznym, oceną wielomianu i pomiarem.</span><span class="sxs-lookup"><span data-stu-id="c1229-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="c1229-109">Dostęp do wszystkich tych składników można uzyskać przy użyciu jednej `open` instrukcji:</span><span class="sxs-lookup"><span data-stu-id="c1229-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="c1229-110">Typy</span><span class="sxs-lookup"><span data-stu-id="c1229-110">Types</span></span>

<span data-ttu-id="c1229-111">Biblioteka liczb obsługuje następujące typy:</span><span class="sxs-lookup"><span data-stu-id="c1229-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="c1229-112">**`LittleEndian`**: Tablica `qArr : Qubit[]` qubit, która reprezentuje liczbę całkowitą, `qArr[0]` gdzie wskazuje najmniejszy znaczący bit.</span><span class="sxs-lookup"><span data-stu-id="c1229-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="c1229-113">**`SignedLittleEndian`**: Taka sama `LittleEndian` jak z tą różnicą, że reprezentuje ze znakiem liczbę całkowitą przechowywaną w uzupełnieniu dwóch.</span><span class="sxs-lookup"><span data-stu-id="c1229-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="c1229-114">**`FixedPoint`**: Reprezentuje liczbę rzeczywistą składającą się z tablicy `qArr2 : Qubit[]` qubit i pozycji `pos`punktu binarnego, która zlicza liczbę cyfr binarnych po lewej stronie punktu binarnego.</span><span class="sxs-lookup"><span data-stu-id="c1229-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="c1229-115">`qArr2`jest przechowywany w taki sam sposób jak `SignedLittleEndian`w przypadku programu.</span><span class="sxs-lookup"><span data-stu-id="c1229-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="c1229-116">Operacje</span><span class="sxs-lookup"><span data-stu-id="c1229-116">Operations</span></span>

<span data-ttu-id="c1229-117">Dla każdego z trzech powyższych typów dostępne są różne operacje:</span><span class="sxs-lookup"><span data-stu-id="c1229-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="c1229-118">Dodawanie</span><span class="sxs-lookup"><span data-stu-id="c1229-118">Addition</span></span>
    - <span data-ttu-id="c1229-119">Porównanie</span><span class="sxs-lookup"><span data-stu-id="c1229-119">Comparison</span></span>
    - <span data-ttu-id="c1229-120">Mnożenie</span><span class="sxs-lookup"><span data-stu-id="c1229-120">Multiplication</span></span>
    - <span data-ttu-id="c1229-121">Podniesienie</span><span class="sxs-lookup"><span data-stu-id="c1229-121">Squaring</span></span>
    - <span data-ttu-id="c1229-122">Dzielenie (z resztą)</span><span class="sxs-lookup"><span data-stu-id="c1229-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="c1229-123">Dodawanie</span><span class="sxs-lookup"><span data-stu-id="c1229-123">Addition</span></span>
    - <span data-ttu-id="c1229-124">Porównanie</span><span class="sxs-lookup"><span data-stu-id="c1229-124">Comparison</span></span>
    - <span data-ttu-id="c1229-125">Uzupełnienie od 1 do wersji 2</span><span class="sxs-lookup"><span data-stu-id="c1229-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="c1229-126">Mnożenie</span><span class="sxs-lookup"><span data-stu-id="c1229-126">Multiplication</span></span>
    - <span data-ttu-id="c1229-127">Podniesienie</span><span class="sxs-lookup"><span data-stu-id="c1229-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="c1229-128">Przygotowanie/inicjowanie do klasycznych wartości</span><span class="sxs-lookup"><span data-stu-id="c1229-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="c1229-129">Dodawanie (klasyczna stała lub inna stała Quantum)</span><span class="sxs-lookup"><span data-stu-id="c1229-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="c1229-130">Porównanie</span><span class="sxs-lookup"><span data-stu-id="c1229-130">Comparison</span></span>
    - <span data-ttu-id="c1229-131">Mnożenie</span><span class="sxs-lookup"><span data-stu-id="c1229-131">Multiplication</span></span>
    - <span data-ttu-id="c1229-132">Podniesienie</span><span class="sxs-lookup"><span data-stu-id="c1229-132">Squaring</span></span>
    - <span data-ttu-id="c1229-133">Ocena wielomianowa z specjalizacją dla funkcji parzystych i nieparzystych</span><span class="sxs-lookup"><span data-stu-id="c1229-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="c1229-134">Wzajemne (1/x)</span><span class="sxs-lookup"><span data-stu-id="c1229-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="c1229-135">Pomiar (klasyczny Double)</span><span class="sxs-lookup"><span data-stu-id="c1229-135">Measurement (classical Double)</span></span>

<span data-ttu-id="c1229-136">Aby uzyskać więcej informacji i szczegółowe informacje dotyczące każdej z tych operacji, zobacz dokumentację dotyczącą bibliotek Q # w witrynie [docs.Microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="c1229-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="c1229-137">Przykład: dodanie liczby całkowitej</span><span class="sxs-lookup"><span data-stu-id="c1229-137">Sample: Integer addition</span></span>

<span data-ttu-id="c1229-138">Przykładowo należy rozważyć wykonanie operacji $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $, czyli operacji przyjmującej n-qubit Integer $x $ i n-lub (n + 1)-qubit Register $y $ jako dane wejściowe, które są mapowane na sumę $ (x + y) $.</span><span class="sxs-lookup"><span data-stu-id="c1229-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="c1229-139">Należy zauważyć, że suma jest obliczana modulo $2 ^ n $, jeśli $y $ jest przechowywany w $n $-bitowym rejestrze.</span><span class="sxs-lookup"><span data-stu-id="c1229-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="c1229-140">Korzystając z zestawu Quantum Development Kit, tę operację można zastosować w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c1229-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="c1229-141">Przykład: ocenianie funkcji gładkich</span><span class="sxs-lookup"><span data-stu-id="c1229-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="c1229-142">Aby oszacować niezakłócone funkcje, takie jak $ \sin (x) $ na komputerze z systemem Quantum, gdzie $x `FixedPoint` $ jest numerem Quantum, biblioteka liczbowa zestawu SDK rozszerzenia Quantum `EvaluatePolynomialFxP` udostępnia `Evaluate[Even/Odd]PolynomialFxP`operacje i.</span><span class="sxs-lookup"><span data-stu-id="c1229-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="c1229-143">Pierwszy, `EvaluatePolynomialFxP`,, umożliwia ocenę wielomianu formularza $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, gdzie $d $ oznacza *stopień*.</span><span class="sxs-lookup"><span data-stu-id="c1229-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="c1229-144">W tym `[a_0,..., a_d]` celu wystarczy, że są to współczynniki wielomianu (typu `Double[]`), dane wejściowe `x : FixedPoint` i wyjściowe `y : FixedPoint` (początkowo zero):</span><span class="sxs-lookup"><span data-stu-id="c1229-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="c1229-145">Wyniki, $P (x) = 1 + 2x $, będą przechowywane w `yFxP`.</span><span class="sxs-lookup"><span data-stu-id="c1229-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="c1229-146">Drugi, `EvaluateEvenPolynomialFxP`, i trzeci, `EvaluateOddPolynomialFxP`, są specjalizacjami dla przypadków funkcji parzystych i nieparzystych.</span><span class="sxs-lookup"><span data-stu-id="c1229-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="c1229-147">Oznacza to, że dla funkcji parzystej/nieparzystej $f (x) $ i $ $ P_ {nawet} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, symbol $ $ $f (x) $ jest dobrze zbliżony do $P _ {nawet} (x) $ lub $P _ {nieparzysta} (x): = x\cdot P_ {nawet} (x) $, odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="c1229-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="c1229-148">W Q # te dwa przypadki mogą być obsługiwane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="c1229-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="c1229-149">który szacuje $P _ {parzysty} (x) = 1 + 2 $, i</span><span class="sxs-lookup"><span data-stu-id="c1229-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="c1229-150">który szacuje $P _ {unparzysty} (x) = x + 2x ^ 3 $.</span><span class="sxs-lookup"><span data-stu-id="c1229-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="c1229-151">Więcej przykładów</span><span class="sxs-lookup"><span data-stu-id="c1229-151">More samples</span></span>

<span data-ttu-id="c1229-152">Więcej przykładów można znaleźć w [repozytorium głównych przykładów](https://github.com/Microsoft/Quantum).</span><span class="sxs-lookup"><span data-stu-id="c1229-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="c1229-153">Aby rozpocząć, Sklonuj repozytorium i Otwórz `Numerics` podfolder:</span><span class="sxs-lookup"><span data-stu-id="c1229-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="c1229-154">Następnie `cd` do jednego z przykładowych folderów i uruchomienia przykładu za pośrednictwem</span><span class="sxs-lookup"><span data-stu-id="c1229-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
