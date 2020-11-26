---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202927"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dostosowuje tabelę prawdy z tablicy wartości logicznych zgodnie z liczbą zmiennych

Zwracana jest nowa tablica o długości `2^numVars` , która może wymagać poszerzenia `table` rozmiaru z `false` wpisami lub obcinanie go do `2^numVars` elementów.

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Dane wejściowe

### <a name="table--bool"></a>Tabela: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabela prawdy jako tablica wartości prawdy


### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)

Liczba zmiennych



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Dostosowana wielkość korekty w tabeli prawdy