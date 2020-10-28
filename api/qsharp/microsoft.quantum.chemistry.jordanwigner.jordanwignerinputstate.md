---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 171a2999ab8c73925d4624c565bfd41a4e73c99d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713981"
---
# <a name="jordanwignerinputstate-user-defined-type"></a><span data-ttu-id="2db77-102">JordanWignerInputState typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="2db77-102">JordanWignerInputState user defined type</span></span>

<span data-ttu-id="2db77-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2db77-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2db77-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2db77-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2db77-105">Format danych przesłanych od języka C# do Q # w celu reprezentowania przygotowania stanu początkowego znaczenie danych reprezentowane przez algorytm, który go otrzymuje.</span><span class="sxs-lookup"><span data-stu-id="2db77-105">Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

