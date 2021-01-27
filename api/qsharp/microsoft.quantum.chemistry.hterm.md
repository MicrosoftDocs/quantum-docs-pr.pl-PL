---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 744668a4fe96ee00fe2f7991f4e1f05eea19d417
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851789"
---
# <a name="hterm-user-defined-type"></a>HTerm typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format danych przesłanych od języka C# do Q # w celu reprezentowania okresu hamiltonian.
Znaczenie reprezentowanego danych jest określane przez algorytm, który go otrzymuje.

```qsharp

newtype HTerm = (Int[], Double[]);
```

