---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715227"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Oblicza rozmiar kroku Trotter w cyklicznej implementacji algorytmu symulacji Trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="order--int"></a>kolejność: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Uwagi

Ta operacja używa innej konwencji indeksowania niż wartość [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). W szczególności `DecomposedIntoTimeStepsCA(_, 4)` odpowiada skalarnemu $p _2 (\lambda) $ w Quant-pH/0508139.