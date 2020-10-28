---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: Operacja _ExtractLogicalQubitFromSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 71390feb84660cc9bf7bb12b64eac6d3ca512387
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712558"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>Operacja _ExtractLogicalQubitFromSteaneCode

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package [](https://nuget.org/packages/)


Syndrome pomiar i odwrotność osadzania.

$X $-i $Z $-stabilizatory nie są traktowane równo, co jest spowodowane szczególnym wyborem obwodu kodowania.
Ten element asymetrii prowadzi do innej procedury wyodrębniania Syndrome.
Jeden z nich może mierzyć Syndrome przez zmierzenie operatora Pauli qubit bezpośrednio w stanie kodu, ale w celu przeprowadzenia operacji logiczne qubit jest zwracany do jednego qubit, w wyniku którego można wykonać pomiary Syndrome bez dalszych ancillas.

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>Dane wejściowe

### <a name="code--logicalregister"></a>kod: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Wynik: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Logiczne qubit i para liczb całkowitych dla $X $-Syndrome i $Z $-Syndrome.
Reprezentują one indeks kodu qubit, w którym jeden $X $-lub $Z $-Error spowodował przemierzoną Syndrome.

## <a name="remarks"></a>Uwagi

Należy zauważyć, że ta operacja nie jest oznaczona jako `internal` , ponieważ testy jednostkowe bezpośrednio zależą od tej operacji. W przyszłości podczas przyszłego ulepszania testy jednostkowe powinny być refaktoryzacjne, aby zależały tylko od publicznie wywoływanych operacji.

> [!WARNING]
> Ta procedura jest dostosowana do określonego obwodu kodowania dla kodu qubit Steane. w przypadku zmodyfikowania obwodu kodowania wynik Syndrome może być interpretowany inaczej.