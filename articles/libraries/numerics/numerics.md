---
title: Korzystanie z biblioteki liczbowej | Microsoft Docs
description: Korzystanie z biblioteki liczb
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 332781a4356015461426ee7640fd931a41450367
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184614"
---
# <a name="using-the-numerics-library"></a>Korzystanie z biblioteki liczb

## <a name="overview"></a>Przegląd

Biblioteka liczbowa składa się z trzech składników

1. **Podstawowa liczba całkowita arytmetyczna** z dodającymi liczby całkowite i komparatorów
1. **Funkcja całkowita wysokiego poziomu** , która jest oparta na podstawowej funkcji; obejmuje mnożenie, dzielenie, inwersję itp.  w przypadku liczb całkowitych ze znakiem i bez znaku.
1. **Funkcja arytmetyczna stałego punktu** z inicjalizacją, dodawaniem, mnożeniem, wzajemnym, wieloznacznym, oceną wielomianu i pomiarem.

Dostęp do wszystkich tych składników można uzyskać przy użyciu jednej instrukcji `open`:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Typ

Biblioteka liczb obsługuje następujące typy:

1. **`LittleEndian`** : tablica qubit `qArr : Qubit[]`, która reprezentuje liczbę całkowitą, w której `qArr[0]` oznacza najmniej znaczący bit.
1. **`SignedLittleEndian`** : taka sama jak `LittleEndian`, z tą różnicą, że reprezentuje cyfrową liczbę całkowitą przechowywaną w uzupełnieniu dwóch.
1. **`FixedPoint`** : reprezentuje liczbę rzeczywistą składającą się z `qArr2 : Qubit[]` tablicy qubit i położenia punktu binarnego `pos`, która zlicza liczbę cyfr binarnych po lewej stronie punktu binarnego. `qArr2` są przechowywane w taki sam sposób co `SignedLittleEndian`.

## <a name="operations"></a>Operations

Dla każdego z trzech powyższych typów dostępne są różne operacje:

1. **`LittleEndian`**
    - Dodatkowo
    - Porównanie
    - Mnożenia
    - Podniesienie
    - Dzielenie (z resztą)

1. **`SignedLittleEndian`**
    - Dodatkowo
    - Porównanie
    - Uzupełnienie od 1 do wersji 2
    - Mnożenia
    - Podniesienie

1. **`FixedPoint`**
    - Przygotowanie/inicjowanie do klasycznych wartości
    - Dodawanie (klasyczna stała lub inna stała Quantum)
    - Porównanie
    - Mnożenia
    - Podniesienie
    - Ocena wielomianowa z specjalizacją dla funkcji parzystych i nieparzystych
    - Wzajemne (1/x)
    - Pomiar (klasyczny Double)

Aby uzyskać więcej informacji i szczegółowe informacje dotyczące każdej z tych operacji, zobacz dokumentację dotyczącą bibliotek Q # w witrynie [docs.Microsoft.com](https://docs.microsoft.com/en-us/quantum)

## <a name="sample-integer-addition"></a>Przykład: dodanie liczby całkowitej

Przykładowo należy rozważyć wykonanie operacji $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $, czyli operacji przyjmującej n-qubit Integer $x $ i n-lub (n + 1)-qubit Register $y $ jako dane wejściowe, które są mapowane na sumę $ (x + y) $. Należy zauważyć, że suma jest obliczana modulo $2 ^ n $, jeśli $y $ jest przechowywany w $n $-bitowym rejestrze.

Korzystając z zestawu Quantum Development Kit, tę operację można zastosować w następujący sposób:
```qsharp
operation MyAdditionTest (xInt : Int, yInt : Int, n : Int) : Unit
{
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xInt, x); // initialize values
        ApplyXorInPlace(yInt, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Przykład: ocenianie funkcji gładkich

Aby oszacować funkcje gładkie, takie jak $ \sin (x) $ na komputerze z systemem Quantum, gdzie $x $ jest typem Quantum `FixedPoint`, Biblioteka elementów Quantum Development Kit zawiera operacje `EvaluatePolynomialFxP` i `Evaluate[Even/Odd]PolynomialFxP`.

Pierwszy, `EvaluatePolynomialFxP`, umożliwia ocenę wielomianu formularza $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, gdzie $d $ oznacza *stopień*. W tym celu wystarczy, że są to współczynniki wielomianowe `[a_0,..., a_d]` (typu `Double[]`), `x : FixedPoint` wejściowe i `y : FixedPoint` wyjściowych (początkowo zero):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
Wynik, $P (x) = 1 + 2x $, będzie przechowywany w `yFxP`.

Drugi, `EvaluateEvenPolynomialFxP`i trzeci, `EvaluateOddPolynomialFxP`, są specjalizacjami dla przypadków funkcji parzystych i nieparzystych. Oznacza to, że dla funkcji parzystej/nieparzystej $f (x) $ i $ $ p_ {nawet} (x) = a_0 + A_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ jest dobrze po$P _ {nawet} (x) $ lub $P _ {nieparzysta} (x): = x\cdot p_ {Parzyst} (x) $ piwo.
W Q # te dwa przypadki mogą być obsługiwane w następujący sposób:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
który szacuje $P _ {parzysty} (x) = 1 + 2 $, i
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
który szacuje $P _ {unparzysty} (x) = x + 2x ^ 3 $.

## <a name="more-samples"></a>Więcej przykładów

Więcej przykładów można znaleźć w [repozytorium głównych przykładów](https://github.com/Microsoft/Quantum).

Aby rozpocząć, Sklonuj repozytorium i Otwórz podfolder `Numerics`:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

Następnie `cd` do jednego z przykładowych folderów i uruchomić przykład za pomocą

```bash
dotnet run
```
