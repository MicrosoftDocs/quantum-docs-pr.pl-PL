---
title: 'Techniki Q # — zmienne lokalne | Microsoft Docs'
description: 'Techniki Q # — zmienne lokalne'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4f5eff1ee8482fa5e5fee9dff421efab93fc0c5a
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183288"
---
# <a name="local-variables"></a>Zmienne lokalne #

Wartość dowolnego typu w Q # można przypisać do zmiennej do ponownego użycia w ramach operacji lub funkcji za pomocą słowa kluczowego `let`.
Na wystąpienie:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Przypisuje określoną tablicę operatorów Pauli do zmiennej o nazwie `measurementOperator`.

> [!TIP]
> Należy zauważyć, że nie trzeba jawnie określać typu naszej nowej zmiennej, ponieważ wyrażenie po prawej stronie instrukcji `let` jest niejednoznaczne i typ jest wnioskowany przez kompilator. 

Zmienne w Q # są *niezmienne*, co oznacza, że gdy zmienna została zdefiniowana w ten sposób, nie można jej zmienić w jakikolwiek sposób.
Pozwala to na kilka optymalizacji, w tym optymalizację klasycznej logiki działającej na zmienne, które mają być zmieniane w celu zastosowania wariantu `Adjoint` operacji.

Zmienne zdefiniowane za pomocą powyższego powiązania `let` są lokalne dla określonego zakresu, takie jak treść operacji lub zawartość pętli `for`.


## <a name="mutability"></a>Zmienność ##

Alternatywnie, aby utworzyć zmienną o `let`, słowo kluczowe `mutable` utworzy specjalną zmienną modyfikowalną, którą można ponownie powiązać po jej początkowym utworzeniu za pomocą słowa kluczowego `set`.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Wszystkie typy w Q #, łącznie z tablicami, są zgodne z semantyką wartości. W szczególności nie jest możliwe aktualizowanie elementów tablicy. Aby zmodyfikować istniejącą tablicę, należy korzystać z mechanizmu kopiowania i aktualizowania podobnie jak dla rekordów w programie F#. Za pomocą narzędzi biblioteki dla tablic dostępnych w [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)można na przykład łatwo zdefiniować funkcję, która zwraca tablicę Paul, gdzie Pauli przy indeksie `i` przyjmuje daną wartość, a wszystkie inne wpisy są tożsamość: 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

Dowiesz się więcej na temat pracy z tablicami podczas omawiania instrukcji i wyrażeń Q #. 

Zmienność w elemencie Q # to koncepcja, która ma zastosowanie do *symbolu* , a nie typu lub wartości. W przeciwnym razie nie ma reprezentacji w systemie typów, niejawnie lub niejawnie, i niezależnie od tego, czy powiązanie jest modyfikowalne (wskazywane przez słowo kluczowe `mutable`) czy niezmienne (zgodnie z definicją `let`) nie zmienia typu powiązanych zmiennych. Zapewnia to istotny sposób izolowania zmienność w wyspecjalizowanych funkcjach i operacjach.
W szczególności, chociaż w przypadku operacji, która używa zmiennej modyfikowalnej nie może być automatycznie generowana, funkcja autogeneracji działa prawidłowo w przypadku operacji wywołującej funkcję, która używa zmienność.
Z tego powodu dobrym sposobem jest zapewnienie funkcji i operacji, które wykorzystują zmienność jako krótkie i kompaktowe, tak aby pozostała część programu Quantum mogła być napisywana przy użyciu standardowych, niezmiennych zmiennych.


## <a name="deconstruction"></a>Dekonstrukcja ##

Oprócz przypisywania pojedynczej zmiennej, `let` i `mutable` słów kluczowych — lub w rzeczywistości innych konstrukcji powiązań — umożliwia także rozpakowywanie zawartości [typu krotki](xref:microsoft.quantum.language.type-model#tuple-types).
Przypisanie tego formularza jest określane w celu *odtworzenia* elementów tej krotki.
Na przykład w przypadku modelowania terminu w hamiltonian przez krotkę możemy użyć dekonstrukcji, aby uzyskać dostęp do różnych danych, które są potrzebne do symulowania w tym okresie:

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


