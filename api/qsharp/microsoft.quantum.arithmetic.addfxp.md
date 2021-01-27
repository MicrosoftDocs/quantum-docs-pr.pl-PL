---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843870"
---
# <a name="addfxp-operation"></a>AddFxP, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Dodaje dwie stałe numery przechowywane w rejestrach Quantum.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

W przypadku dwóch rejestrów ustalonych odpowiednio w Stanach $ \ket{f_1} $ i $ \ket{f_2} $ program wykona operację $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 f_2} $.

## <a name="input"></a>Dane wejściowe

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Numer pierwszej stałej punktu


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Druga liczba stałych punktów, zostanie zaktualizowana tak, aby zawierała sumę dwóch danych wejściowych.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Bieżąca implementacja wymaga, aby dwie stałe punkty miały tę samą pozycję punktu zliczania z najmniej znaczącego bitu, tj., $n _i $ i $p _i $ muszą być równe.