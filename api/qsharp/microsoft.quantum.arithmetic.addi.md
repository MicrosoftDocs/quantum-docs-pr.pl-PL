---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721689"
---
# <a name="addi-operation"></a>AddI, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Program automatycznie wybiera między dodawaniem i bez, w zależności od rozmiaru rejestru `ys` .

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bitowy składnik dodawania.


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Składnik dodawania z co najmniej $n $ qubits. Będzie przechowywać wynik.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

