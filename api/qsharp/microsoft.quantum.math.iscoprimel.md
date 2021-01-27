---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851344"
---
# <a name="iscoprimel-function"></a>IsCoprimeL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wartość true, jeśli $a $ i $b $ są współi w przeciwnym razie false.

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="a--bigint"></a>Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Pierwsza liczba, które są testowane co primality


### <a name="b--bigint"></a>b: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Druga liczba, z której jest testowana primality



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

Prawda, jeśli $a $ i $b $ są współdzielone (np. ich największy wspólny dzielnik to 1) i w przeciwnym razie ma wartość false