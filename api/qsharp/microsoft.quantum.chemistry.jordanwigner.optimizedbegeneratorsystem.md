---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
title: OptimizedBEGeneratorSystem typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEGeneratorSystem
qsharp.summary: Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.
ms.openlocfilehash: eb274420a2fb813b1e34cea42bf1336e592feaae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837403"
---
# <a name="optimizedbegeneratorsystem-user-defined-type"></a>OptimizedBEGeneratorSystem typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Funkcja zwracająca `OptimizedBETermIndex` dane dla terminu `n` podanego przez liczbę całkowitą `n` wraz z liczbą warunków w pierwszej `Int` i łączną wartość bezwzględną wszystkich współczynników warunku w `Double` .

```qsharp

newtype OptimizedBEGeneratorSystem = (Int, Double, (Int -> Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex));
```

