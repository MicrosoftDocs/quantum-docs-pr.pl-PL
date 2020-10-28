---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
title: OptimizedBEGeneratorSystem typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEGeneratorSystem
qsharp.summary: Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.
ms.openlocfilehash: 06d13a8a64a3c572821ec97f8776d6f1dbe4a4ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713939"
---
# <a name="optimizedbegeneratorsystem-user-defined-type"></a><span data-ttu-id="e0d28-102">OptimizedBEGeneratorSystem typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="e0d28-102">OptimizedBEGeneratorSystem user defined type</span></span>

<span data-ttu-id="e0d28-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e0d28-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e0d28-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0d28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0d28-105">Funkcja zwracająca `OptimizedBETermIndex` dane dla terminu `n` podanego przez liczbę całkowitą `n` wraz z liczbą warunków w pierwszej `Int` i łączną wartość bezwzględną wszystkich współczynników warunku w `Double` .</span><span class="sxs-lookup"><span data-stu-id="e0d28-105">Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.</span></span>

```qsharp

newtype OptimizedBEGeneratorSystem = (Int, Double, (Int -> Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex));
```

