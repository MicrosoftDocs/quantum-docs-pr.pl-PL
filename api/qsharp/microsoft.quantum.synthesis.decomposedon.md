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
# <a name="decomposedon-function"></a>DecomposedOn, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dekomponowauje permutację na zmiennej

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Opis

Nadana Permutacja $ \pi $ ( `perm` ) i indeks $i $ ( `index` ), ta metoda zwraca trzy Permutacje $ ((\ pi_l, \ pi_r), \pi ') $ w taki sposób, że obrazy $ \ pi_l $ i $ \ pi_r $ nie zmieniają bitów w ich elementach w indeksach innych niż $i $ i obrazy $ \pi ' $ nie zmieniają bitu $i $ w ich elementach.

## <a name="input"></a>Dane wejściowe

### <a name="perm--int"></a>uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>indeks: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Wynik: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])



## <a name="example"></a>Przykład

Załóżmy, że dane wejściowe to uprawnienie = [0, 2, 3, 5, 7, 1, 4, 6] i index = 0, a następnie ta funkcja oblicza trzy permutacje w oparciu o poniższą tabelę, która wyświetla permutację `perm` w notacji binarnej z elementami w grupie a i obrazów w grupie D.  W kolumnach są wystawione indeksy bitowe.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

Wszystkie wartości indeksów, które nie są równe 0 (= index), są kopiowane z A do B i z D do C.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

Następny a 0 jest umieszczany dla pierwszego elementu z pustym indeksem w kolumnie 0 w bloku B, a następnie wartość 1 jest umieszczana w B, gdzie prefiks jest zgodny (w pierwszym przypadku drugi wiersz z indeksami 0 0).
Następnie w tym samym wierszu w bloku C zostanie dodana wartość 1, a następnie wartość 0 dla odpowiedniego prefiksu w bloku C.  Ten proces jest powtarzany, dopóki wszystkie indeksy nie zostaną umieszczone w kolumnie 0 w blokach B i C.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

W tabeli można przeczytać trzy nowe permutacje:

- $ \ pi_l $ z elementami w, obrazy w B (z lewej)
- $ \ pi_r $ z elementami w D, zdjęciami w języku C (po prawej)
- $ \pi ' $ z elementami w B, obrazy w C (reszta)

Należy zauważyć, że przez wartości bitowe projektu nie zmieniają się w $ \ pi_l $ i $ \ pi_r $ dla indeksów 1 i 2, a wartości bitowe nie są zmieniane dla w $ \ pi_ ' $ dla indeksu 0.  Należy również zauważyć, że $ \ pi_l $ i $ \ pi_r $ musi być samoobsługowy.

Liczby pochodne i zwrócone są następujące: Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] reszta = [0, 3, 2, 5, 6, 1, 4, 7]