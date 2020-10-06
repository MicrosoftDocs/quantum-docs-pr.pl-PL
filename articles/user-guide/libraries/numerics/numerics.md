---
title: Korzystanie z Q# biblioteki liczbowych firmy Microsoft
description: Dowiedz się więcej o typach i operacjach dostępnych w bibliotece liczb Quantum firmy Microsoft.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: dfcb8e9e5a15d0881750d67cf58d7ad47cbecd3a
ms.sourcegitcommit: 897ace8b506adb2331e911ee5633dceced566174
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91764138"
---
# <a name="using-the-numerics-library"></a>Korzystanie z biblioteki liczb

## <a name="overview"></a>Omówienie

Biblioteka liczbowa składa się z trzech składników

1. **Podstawowa liczba całkowita arytmetyczna** z dodającymi liczby całkowite i komparatorów
1. **Funkcja całkowita wysokiego poziomu** , która jest oparta na podstawowej funkcji; obejmuje mnożenie, dzielenie, inwersję itp.  w przypadku liczb całkowitych ze znakiem i bez znaku.
1. **Funkcja arytmetyczna stałego punktu** z inicjalizacją, dodawaniem, mnożeniem, wzajemnym, wieloznacznym, oceną wielomianu i pomiarem.

Dostęp do wszystkich tych składników można uzyskać przy użyciu jednej `open` instrukcji:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Typy

Biblioteka liczb obsługuje następujące typy:

1. **`LittleEndian`**: Tablica qubit `qArr : Qubit[]` , która reprezentuje liczbę całkowitą, gdzie `qArr[0]` wskazuje najmniejszy znaczący bit.
1. **`SignedLittleEndian`**: Taka sama jak `LittleEndian` z tą różnicą, że reprezentuje ze znakiem liczbę całkowitą przechowywaną w uzupełnieniu dwóch.
1. **`FixedPoint`**: Reprezentuje liczbę rzeczywistą składającą się z tablicy qubit `qArr2 : Qubit[]` i pozycji punktu binarnego `pos` , która zlicza liczbę cyfr binarnych po lewej stronie punktu binarnego. `qArr2` jest przechowywany w taki sam sposób jak w przypadku programu `SignedLittleEndian` .

## <a name="operations"></a>Operacje

Dla każdego z trzech powyższych typów dostępne są różne operacje:

1. **`LittleEndian`**
    - Znak dodawania
    - Porównanie
    - Znak mnożenia
    - Podniesienie
    - Dzielenie (z resztą)

1. **`SignedLittleEndian`**
    - Znak dodawania
    - Porównanie
    - Uzupełnienie od 1 do wersji 2
    - Znak mnożenia
    - Podniesienie

1. **`FixedPoint`**
    - Przygotowanie/inicjowanie do klasycznych wartości
    - Dodawanie (klasyczna stała lub inna stała Quantum)
    - Porównanie
    - Znak mnożenia
    - Podniesienie
    - Ocena wielomianowa z specjalizacją dla funkcji parzystych i nieparzystych
    - Wzajemne (1/x)
    - Pomiar (klasyczny Double)

Aby uzyskać więcej informacji i szczegółowe informacje dotyczące każdej z tych operacji, zobacz dokumentację Q# bibliotek References w witrynie [docs.Microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>Przykład: dodanie liczby całkowitej

Przykładowo należy rozważyć wykonanie operacji $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $, czyli operacji przyjmującej n-qubit Integer $x $ i n-lub (n + 1)-qubit Register $y $ jako dane wejściowe, które są mapowane na sumę $ (x + y) $. Należy zauważyć, że suma jest obliczana modulo $2 ^ n $, jeśli $y $ jest przechowywany w $n $-bitowym rejestrze.

Korzystając z zestawu Quantum Development Kit, tę operację można zastosować w następujący sposób:
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

## <a name="sample-evaluating-smooth-functions"></a>Przykład: ocenianie funkcji gładkich

Aby oszacować niezakłócone funkcje, takie jak $ \sin (x) $ na komputerze z systemem Quantum, gdzie $x $ jest `FixedPoint` numerem Quantum, biblioteka liczbowa zestawu SDK rozszerzenia Quantum udostępnia operacje `EvaluatePolynomialFxP` i `Evaluate[Even/Odd]PolynomialFxP` .

Pierwszy, `EvaluatePolynomialFxP` ,, umożliwia ocenę wielomianu formularza $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, gdzie $d $ oznacza *stopień*. W tym celu wystarczy, że są to współczynniki wielomianu `[a_0,..., a_d]` (typu `Double[]` ), dane wejściowe `x : FixedPoint` i wyjściowe `y : FixedPoint` (początkowo zero):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
Wyniki, $P (x) = 1 + 2x $, będą przechowywane w `yFxP` .

Drugi, `EvaluateEvenPolynomialFxP` , i trzeci, `EvaluateOddPolynomialFxP` , są specjalizacjami dla przypadków funkcji parzystych i nieparzystych. Oznacza to, że dla funkcji parzystej/nieparzystej $f (x) $ i $ $ P_ {nawet} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, symbol $ $ $f (x) $ jest dobrze zbliżony do $P _ {nawet} (x) $ lub $P _ {nieparzysta} (x): = x\cdot P_ {nawet} (x) $, odpowiednio.
W programie Q# te dwa przypadki mogą być obsługiwane w następujący sposób:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
który szacuje $P _ {parzysty} (x) = 1 + 2 $, i
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
który szacuje $P _ {unparzysty} (x) = x + 2x ^ 3 $.

## <a name="more-samples"></a>Więcej przykładów

Więcej przykładów można znaleźć w [repozytorium głównych przykładów](https://github.com/Microsoft/Quantum).

Aby rozpocząć, Sklonuj repozytorium i Otwórz `Numerics` podfolder:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics
```

Następnie `cd` do jednego z przykładowych folderów i uruchomienia przykładu za pośrednictwem

```bash
dotnet run
```
