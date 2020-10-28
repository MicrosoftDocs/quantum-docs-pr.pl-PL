---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714868"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="1a3fe-102">HTerm typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="1a3fe-102">HTerm user defined type</span></span>

<span data-ttu-id="1a3fe-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1a3fe-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="1a3fe-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1a3fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1a3fe-105">Format danych przesłanych od języka C# do Q # w celu reprezentowania okresu hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="1a3fe-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="1a3fe-106">Znaczenie reprezentowanego danych jest określane przez algorytm, który go otrzymuje.</span><span class="sxs-lookup"><span data-stu-id="1a3fe-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

