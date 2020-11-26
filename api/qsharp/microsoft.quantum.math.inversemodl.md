---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 0d768114c84025a067e0b60762e6834fbd36deb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228189"
---
# <a name="inversemodl-function"></a>InverseModL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca $b $, które $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Dane wejściowe

### <a name="a--bigint"></a>Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Odwrócona liczba


### <a name="modulus--bigint"></a>Moduł: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Moduł, zgodnie z którym liczby są odwrócone



## <a name="output--bigint"></a>Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Liczba całkowita $b $, taka jak $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.