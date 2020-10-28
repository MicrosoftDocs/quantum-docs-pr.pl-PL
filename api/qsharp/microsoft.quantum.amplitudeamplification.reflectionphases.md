---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721816"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="554b2-102">ReflectionPhases typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="554b2-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="554b2-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="554b2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="554b2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="554b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="554b2-105">Fazy dla sekwencji częściowego odbicia w wzmocnienia amplitudy.</span><span class="sxs-lookup"><span data-stu-id="554b2-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="554b2-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="554b2-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="554b2-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="554b2-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="554b2-108">Tablica faz odbicia informacji o stanie początkowym.</span><span class="sxs-lookup"><span data-stu-id="554b2-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="554b2-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="554b2-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="554b2-110">Tablica faz dla odbicia stanu docelowego.</span><span class="sxs-lookup"><span data-stu-id="554b2-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="554b2-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="554b2-111">Remarks</span></span>

<span data-ttu-id="554b2-112">Obie tablice muszą mieć równej długości.</span><span class="sxs-lookup"><span data-stu-id="554b2-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="554b2-113">Należy zauważyć, że w wielu przypadkach Pierwsza faza dotycząca stanu początkowego i ostatniej fazy dotyczącej stanu docelowego wprowadza globalną fazę zmiany i może być ustawiona na $0 $.</span><span class="sxs-lookup"><span data-stu-id="554b2-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>