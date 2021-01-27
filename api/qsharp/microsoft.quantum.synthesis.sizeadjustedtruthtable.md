---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855322"
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