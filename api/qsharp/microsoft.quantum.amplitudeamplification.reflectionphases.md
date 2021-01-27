---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847184"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="66928-102">ReflectionPhases typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="66928-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="66928-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="66928-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="66928-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66928-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66928-105">Fazy dla sekwencji częściowego odbicia w wzmocnienia amplitudy.</span><span class="sxs-lookup"><span data-stu-id="66928-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="66928-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="66928-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="66928-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="66928-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="66928-108">Tablica faz odbicia informacji o stanie początkowym.</span><span class="sxs-lookup"><span data-stu-id="66928-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="66928-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="66928-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="66928-110">Tablica faz dla odbicia stanu docelowego.</span><span class="sxs-lookup"><span data-stu-id="66928-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="66928-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="66928-111">Remarks</span></span>

<span data-ttu-id="66928-112">Obie tablice muszą mieć równej długości.</span><span class="sxs-lookup"><span data-stu-id="66928-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="66928-113">Należy zauważyć, że w wielu przypadkach Pierwsza faza dotycząca stanu początkowego i ostatniej fazy dotyczącej stanu docelowego wprowadza globalną fazę zmiany i może być ustawiona na $0 $.</span><span class="sxs-lookup"><span data-stu-id="66928-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>