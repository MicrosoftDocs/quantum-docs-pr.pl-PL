---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e09c9da500889dfcb514d0a02dec957bfaa70e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851387"
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