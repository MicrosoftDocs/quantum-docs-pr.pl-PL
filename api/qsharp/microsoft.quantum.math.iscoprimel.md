---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228138"
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