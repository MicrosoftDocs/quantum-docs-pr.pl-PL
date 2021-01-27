---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840071"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Oblicza rozmiar kroku Trotter w cyklicznej implementacji algorytmu symulacji Trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="order--int"></a>kolejność: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Uwagi

Ta operacja używa innej konwencji indeksowania niż wartość [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). W szczególności `DecomposedIntoTimeStepsCA(_, 4)` odpowiada skalarnemu $p _2 (\lambda) $ w Quant-pH/0508139.