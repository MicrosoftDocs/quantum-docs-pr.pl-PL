---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204134"
---
# <a name="hterm-user-defined-type"></a>HTerm typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format danych przesłanych od języka C# do Q # w celu reprezentowania okresu hamiltonian.
Znaczenie reprezentowanego danych jest określane przez algorytm, który go otrzymuje.

```qsharp

newtype HTerm = (Int[], Double[]);
```

