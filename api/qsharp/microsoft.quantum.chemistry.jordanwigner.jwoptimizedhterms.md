---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms
title: JWOptimizedHTerms typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JWOptimizedHTerms
qsharp.summary: Format of data passed from C# to Q# to represent terms of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: d75737f23db84f2a21daff7a0ebcb8ae51feb642
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713967"
---
# <a name="jwoptimizedhterms-user-defined-type"></a><span data-ttu-id="da45a-102">JWOptimizedHTerms typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="da45a-102">JWOptimizedHTerms user defined type</span></span>

<span data-ttu-id="da45a-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="da45a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="da45a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da45a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da45a-105">Format danych przesłanych od języka C# do Q #, aby reprezentować warunki hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="da45a-105">Format of data passed from C# to Q# to represent terms of the Hamiltonian.</span></span>
<span data-ttu-id="da45a-106">Znaczenie reprezentowanego danych jest określane przez algorytm, który go otrzymuje.</span><span class="sxs-lookup"><span data-stu-id="da45a-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JWOptimizedHTerms = (Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[]);
```

