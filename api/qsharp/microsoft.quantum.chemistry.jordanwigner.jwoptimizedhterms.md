---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms
title: JWOptimizedHTerms typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JWOptimizedHTerms
qsharp.summary: Format of data passed from C# to Q# to represent terms of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 1588adc0edb95e347616dd6260200c09fee0f190
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837632"
---
# <a name="jwoptimizedhterms-user-defined-type"></a>JWOptimizedHTerms typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format danych przesłanych od języka C# do Q #, aby reprezentować warunki hamiltonian.
Znaczenie reprezentowanego danych jest określane przez algorytm, który go otrzymuje.

```qsharp

newtype JWOptimizedHTerms = (Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[]);
```

