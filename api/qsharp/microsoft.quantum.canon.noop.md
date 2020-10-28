---
uid: Microsoft.Quantum.Canon.NoOp
title: Aktualizujący nie działa, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715759"
---
# <a name="noop-operation"></a>Aktualizujący nie działa, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Wykonuje operację Identity (No-op) w argumencie.

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a>Opis

Ta operacja przyjmuje wartość dowolnego typu i nic nie robi.
Może to być przydatne, gdy oczekiwano danych wejściowych typu operacji, ale nie powinno być podejmowane żadne działanie.
Na przykład jeśli określony Syndrome korekcji błędów wskazuje, że nie wystąpił błąd, `NoOp<Qubit[]>` może to być poprawna procedura odzyskiwania.
Podobnie, jeśli operacja oczekuje procedury przygotowania stanu jako dane wejściowe, może służyć `NoOp<Qubit[]>` do przygotowania stanu $ \ket{0 \cdots 0} $.

## <a name="input"></a>Dane wejściowe

### <a name="input--t"></a>dane wejściowe: t

Wartość do zignorowania.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

We wszystkich przypadkach należy jawnie określić parametr typu dla `NoOp` . Na przykład `NoOp<Qubit>` jest taka sama jak <xref:microsoft.quantum.intrinsic.i> .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. wewnętrzna. I](xref:Microsoft.Quantum.Intrinsic.I)