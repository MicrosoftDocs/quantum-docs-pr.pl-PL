---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721305"
---
# <a name="carryoutcorecdkm-operation"></a>CarryOutCoreCDKM, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Operacja podstawowa w RippleCarryAdderCDKM, używana z powyższą operacją ApplyOuterCDKMAdder, czyli sprzężona z tą operacją w celu uzyskania wewnętrznej operacji RippleCarryAdderCDKM. Ta operacja oblicza qubit przeprowadzenia i stosuje sekwencję nieobecności bram w ramach danych wejściowych `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Pierwszy rejestr qubit.


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Drugi rejestr qubit.


### <a name="ancilla--qubit"></a>Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ancilla qubit używany w RippleCarryAdderCDKM przeszedł do tej operacji.


### <a name="carry--qubit"></a>Przenieś: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Przeprowadzenie qubit w operacji RippleCarryAdderCDKM.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Dokumentacja

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum Ripple-przenieść obwód dodawania", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1