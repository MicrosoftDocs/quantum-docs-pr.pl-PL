---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721212"
---
# <a name="copymostsignificantbit-operation"></a>CopyMostSignificantBit, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Kopiuje najbardziej znaczący bit rejestru qubit `from` reprezentujący liczbę całkowitą bez znaku w qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="from--littleendian"></a>z: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Liczba całkowita bez znaku, z której jest kopiowany najwyższy bit.
Liczba całkowita jest zakodowana w formacie little-endian.


### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, w którym jest kopiowany najwyższy bit. Kodowanie bitowe jest w obliczeniach.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)