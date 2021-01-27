---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855526"
---
# <a name="decomposedon-function"></a><span data-ttu-id="57cd6-102">DecomposedOn, funkcja</span><span class="sxs-lookup"><span data-stu-id="57cd6-102">DecomposedOn function</span></span>

<span data-ttu-id="57cd6-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="57cd6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="57cd6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57cd6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57cd6-105">Dekomponowauje permutację na zmiennej</span><span class="sxs-lookup"><span data-stu-id="57cd6-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="57cd6-106">Opis</span><span class="sxs-lookup"><span data-stu-id="57cd6-106">Description</span></span>

<span data-ttu-id="57cd6-107">Nadana Permutacja $ \pi $ ( `perm` ) i indeks $i $ ( `index` ), ta metoda zwraca trzy Permutacje $ ((\ pi_l, \ pi_r), \pi ') $ w taki sposób, że obrazy $ \ pi_l $ i $ \ pi_r $ nie zmieniają bitów w ich elementach w indeksach innych niż $i $ i obrazy $ \pi ' $ nie zmieniają bitu $i $ w ich elementach.</span><span class="sxs-lookup"><span data-stu-id="57cd6-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="57cd6-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="57cd6-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="57cd6-109">uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="57cd6-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="57cd6-110">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57cd6-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="57cd6-111">Wynik: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="57cd6-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="57cd6-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="57cd6-112">Example</span></span>

<span data-ttu-id="57cd6-113">Załóżmy, że dane wejściowe to uprawnienie = [0, 2, 3, 5, 7, 1, 4, 6] i index = 0, a następnie ta funkcja oblicza trzy permutacje w oparciu o poniższą tabelę, która wyświetla permutację `perm` w notacji binarnej z elementami w grupie a i obrazów w grupie D.  W kolumnach są wystawione indeksy bitowe.</span><span class="sxs-lookup"><span data-stu-id="57cd6-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="57cd6-114">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="57cd6-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="57cd6-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-115">2 1 0</span></span> | <span data-ttu-id="57cd6-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-116">2 1 0</span></span> | <span data-ttu-id="57cd6-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-117">2 1 0</span></span> | <span data-ttu-id="57cd6-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="57cd6-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-119">0 0 0</span></span> |       |       | <span data-ttu-id="57cd6-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-120">0 0 0</span></span> | <span data-ttu-id="57cd6-121">0</span><span class="sxs-lookup"><span data-stu-id="57cd6-121">0</span></span>
| <span data-ttu-id="57cd6-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-122">0 0 1</span></span> |       |       | <span data-ttu-id="57cd6-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-123">0 1 0</span></span> | <span data-ttu-id="57cd6-124">2</span><span class="sxs-lookup"><span data-stu-id="57cd6-124">2</span></span>
| <span data-ttu-id="57cd6-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-125">0 1 0</span></span> |       |       | <span data-ttu-id="57cd6-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-126">0 1 1</span></span> | <span data-ttu-id="57cd6-127">3</span><span class="sxs-lookup"><span data-stu-id="57cd6-127">3</span></span>
| <span data-ttu-id="57cd6-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-128">0 1 1</span></span> |       |       | <span data-ttu-id="57cd6-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-129">1 0 1</span></span> | <span data-ttu-id="57cd6-130">5</span><span class="sxs-lookup"><span data-stu-id="57cd6-130">5</span></span>
| <span data-ttu-id="57cd6-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-131">1 0 0</span></span> |       |       | <span data-ttu-id="57cd6-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-132">1 1 1</span></span> | <span data-ttu-id="57cd6-133">7</span><span class="sxs-lookup"><span data-stu-id="57cd6-133">7</span></span>
| <span data-ttu-id="57cd6-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-134">1 0 1</span></span> |       |       | <span data-ttu-id="57cd6-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-135">0 0 1</span></span> | <span data-ttu-id="57cd6-136">1</span><span class="sxs-lookup"><span data-stu-id="57cd6-136">1</span></span>
| <span data-ttu-id="57cd6-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-137">1 1 0</span></span> |       |       | <span data-ttu-id="57cd6-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-138">1 0 0</span></span> | <span data-ttu-id="57cd6-139">4</span><span class="sxs-lookup"><span data-stu-id="57cd6-139">4</span></span>
| <span data-ttu-id="57cd6-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-140">1 1 1</span></span> |       |       | <span data-ttu-id="57cd6-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-141">1 1 0</span></span> | <span data-ttu-id="57cd6-142">6</span><span class="sxs-lookup"><span data-stu-id="57cd6-142">6</span></span>

<span data-ttu-id="57cd6-143">Wszystkie wartości indeksów, które nie są równe 0 (= index), są kopiowane z A do B i z D do C.</span><span class="sxs-lookup"><span data-stu-id="57cd6-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="57cd6-144">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="57cd6-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="57cd6-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-145">2 1 0</span></span> | <span data-ttu-id="57cd6-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-146">2 1 0</span></span> | <span data-ttu-id="57cd6-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-147">2 1 0</span></span> | <span data-ttu-id="57cd6-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="57cd6-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-149">0 0 0</span></span> | <span data-ttu-id="57cd6-150">0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-150">0 0</span></span>   | <span data-ttu-id="57cd6-151">0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-151">0 0</span></span>   | <span data-ttu-id="57cd6-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-152">0 0 0</span></span> |
| <span data-ttu-id="57cd6-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-153">0 0 1</span></span> | <span data-ttu-id="57cd6-154">0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-154">0 0</span></span>   | <span data-ttu-id="57cd6-155">0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-155">0 1</span></span>   | <span data-ttu-id="57cd6-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-156">0 1 0</span></span> |
| <span data-ttu-id="57cd6-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-157">0 1 0</span></span> | <span data-ttu-id="57cd6-158">0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-158">0 1</span></span>   | <span data-ttu-id="57cd6-159">0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-159">0 1</span></span>   | <span data-ttu-id="57cd6-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-160">0 1 1</span></span> |
| <span data-ttu-id="57cd6-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-161">0 1 1</span></span> | <span data-ttu-id="57cd6-162">0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-162">0 1</span></span>   | <span data-ttu-id="57cd6-163">1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-163">1 0</span></span>   | <span data-ttu-id="57cd6-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-164">1 0 1</span></span> |
| <span data-ttu-id="57cd6-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-165">1 0 0</span></span> | <span data-ttu-id="57cd6-166">1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-166">1 0</span></span>   | <span data-ttu-id="57cd6-167">1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-167">1 1</span></span>   | <span data-ttu-id="57cd6-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-168">1 1 1</span></span> |
| <span data-ttu-id="57cd6-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-169">1 0 1</span></span> | <span data-ttu-id="57cd6-170">1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-170">1 0</span></span>   | <span data-ttu-id="57cd6-171">0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-171">0 0</span></span>   | <span data-ttu-id="57cd6-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-172">0 0 1</span></span> |
| <span data-ttu-id="57cd6-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-173">1 1 0</span></span> | <span data-ttu-id="57cd6-174">1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-174">1 1</span></span>   | <span data-ttu-id="57cd6-175">1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-175">1 0</span></span>   | <span data-ttu-id="57cd6-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-176">1 0 0</span></span> |
| <span data-ttu-id="57cd6-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-177">1 1 1</span></span> | <span data-ttu-id="57cd6-178">1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-178">1 1</span></span>   | <span data-ttu-id="57cd6-179">1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-179">1 1</span></span>   | <span data-ttu-id="57cd6-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-180">1 1 0</span></span> |

<span data-ttu-id="57cd6-181">Następny a 0 jest umieszczany dla pierwszego elementu z pustym indeksem w kolumnie 0 w bloku B, a następnie wartość 1 jest umieszczana w B, gdzie prefiks jest zgodny (w pierwszym przypadku drugi wiersz z indeksami 0 0).</span><span class="sxs-lookup"><span data-stu-id="57cd6-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="57cd6-182">Następnie w tym samym wierszu w bloku C zostanie dodana wartość 1, a następnie wartość 0 dla odpowiedniego prefiksu w bloku C.  Ten proces jest powtarzany, dopóki wszystkie indeksy nie zostaną umieszczone w kolumnie 0 w blokach B i C.</span><span class="sxs-lookup"><span data-stu-id="57cd6-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="57cd6-183">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="57cd6-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="57cd6-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-184">2 1 0</span></span> | <span data-ttu-id="57cd6-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-185">2 1 0</span></span> | <span data-ttu-id="57cd6-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-186">2 1 0</span></span> | <span data-ttu-id="57cd6-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="57cd6-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-188">0 0 0</span></span> | <span data-ttu-id="57cd6-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-189">0 0 0</span></span> | <span data-ttu-id="57cd6-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-190">0 0 0</span></span> | <span data-ttu-id="57cd6-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-191">0 0 0</span></span> |
| <span data-ttu-id="57cd6-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-192">0 0 1</span></span> | <span data-ttu-id="57cd6-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-193">0 0 1</span></span> | <span data-ttu-id="57cd6-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-194">0 1 1</span></span> | <span data-ttu-id="57cd6-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-195">0 1 0</span></span> |
| <span data-ttu-id="57cd6-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-196">0 1 0</span></span> | <span data-ttu-id="57cd6-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-197">0 1 0</span></span> | <span data-ttu-id="57cd6-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-198">0 1 0</span></span> | <span data-ttu-id="57cd6-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-199">0 1 1</span></span> |
| <span data-ttu-id="57cd6-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-200">0 1 1</span></span> | <span data-ttu-id="57cd6-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-201">0 1 1</span></span> | <span data-ttu-id="57cd6-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-202">1 0 1</span></span> | <span data-ttu-id="57cd6-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-203">1 0 1</span></span> |
| <span data-ttu-id="57cd6-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-204">1 0 0</span></span> | <span data-ttu-id="57cd6-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-205">1 0 0</span></span> | <span data-ttu-id="57cd6-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-206">1 1 0</span></span> | <span data-ttu-id="57cd6-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-207">1 1 1</span></span> |
| <span data-ttu-id="57cd6-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-208">1 0 1</span></span> | <span data-ttu-id="57cd6-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-209">1 0 1</span></span> | <span data-ttu-id="57cd6-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-210">0 0 1</span></span> | <span data-ttu-id="57cd6-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-211">0 0 1</span></span> |
| <span data-ttu-id="57cd6-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-212">1 1 0</span></span> | <span data-ttu-id="57cd6-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-213">1 1 0</span></span> | <span data-ttu-id="57cd6-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-214">1 0 0</span></span> | <span data-ttu-id="57cd6-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-215">1 0 0</span></span> |
| <span data-ttu-id="57cd6-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-216">1 1 1</span></span> | <span data-ttu-id="57cd6-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-217">1 1 1</span></span> | <span data-ttu-id="57cd6-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="57cd6-218">1 1 1</span></span> | <span data-ttu-id="57cd6-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="57cd6-219">1 1 0</span></span> |

<span data-ttu-id="57cd6-220">W tabeli można przeczytać trzy nowe permutacje:</span><span class="sxs-lookup"><span data-stu-id="57cd6-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="57cd6-221">$ \ pi_l $ z elementami w, obrazy w B (z lewej)</span><span class="sxs-lookup"><span data-stu-id="57cd6-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="57cd6-222">$ \ pi_r $ z elementami w D, zdjęciami w języku C (po prawej)</span><span class="sxs-lookup"><span data-stu-id="57cd6-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="57cd6-223">$ \pi ' $ z elementami w B, obrazy w C (reszta)</span><span class="sxs-lookup"><span data-stu-id="57cd6-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="57cd6-224">Należy zauważyć, że przez wartości bitowe projektu nie zmieniają się w $ \ pi_l $ i $ \ pi_r $ dla indeksów 1 i 2, a wartości bitowe nie są zmieniane dla w $ \ pi_ ' $ dla indeksu 0.</span><span class="sxs-lookup"><span data-stu-id="57cd6-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="57cd6-225">Należy również zauważyć, że $ \ pi_l $ i $ \ pi_r $ musi być samoobsługowy.</span><span class="sxs-lookup"><span data-stu-id="57cd6-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="57cd6-226">Liczby pochodne i zwrócone są następujące: Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] reszta = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="57cd6-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>