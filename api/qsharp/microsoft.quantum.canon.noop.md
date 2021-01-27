---
uid: Microsoft.Quantum.Canon.NoOp
title: Aktualizujący nie działa, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852392"
---
# <a name="noop-operation"></a>Aktualizujący nie działa, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Wykonuje operację Identity (No-op) w argumencie.

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
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