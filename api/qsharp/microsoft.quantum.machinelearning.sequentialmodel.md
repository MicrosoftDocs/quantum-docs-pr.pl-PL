---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722390"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="68e84-102">SequentialModel typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="68e84-102">SequentialModel user defined type</span></span>

<span data-ttu-id="68e84-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="68e84-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="68e84-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68e84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68e84-105">Opisuje model klasyfikatora Quantum składający się z sekwencji sparametryzowanej i kontrolowanej rotacji, przypisywania kątów obrotu oraz różnicy między dwiema klasami rozpoznawanymi przez model.</span><span class="sxs-lookup"><span data-stu-id="68e84-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="68e84-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="68e84-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="68e84-107">Struktura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="68e84-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="68e84-108">Sekwencja kontrolowanych rotacji używanych do klasyfikowania danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="68e84-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="68e84-109">Parametry: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="68e84-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="68e84-110">Przypisanie kątów obrotu do danej struktury klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="68e84-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="68e84-111">Różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="68e84-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="68e84-112">Różnica między dwiema klasami rozpoznawanymi przez ten klasyfikator.</span><span class="sxs-lookup"><span data-stu-id="68e84-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="68e84-113">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="68e84-113">References</span></span>

- [<span data-ttu-id="68e84-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="68e84-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)