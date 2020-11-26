---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196178"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="a0ccb-102">SequentialModel typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="a0ccb-102">SequentialModel user defined type</span></span>

<span data-ttu-id="a0ccb-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a0ccb-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a0ccb-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a0ccb-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a0ccb-105">Opisuje model klasyfikatora Quantum składający się z sekwencji sparametryzowanej i kontrolowanej rotacji, przypisywania kątów obrotu oraz różnicy między dwiema klasami rozpoznawanymi przez model.</span><span class="sxs-lookup"><span data-stu-id="a0ccb-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="a0ccb-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="a0ccb-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="a0ccb-107">Struktura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="a0ccb-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="a0ccb-108">Sekwencja kontrolowanych rotacji używanych do klasyfikowania danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="a0ccb-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="a0ccb-109">Parametry: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a0ccb-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a0ccb-110">Przypisanie kątów obrotu do danej struktury klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="a0ccb-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="a0ccb-111">Różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a0ccb-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a0ccb-112">Różnica między dwiema klasami rozpoznawanymi przez ten klasyfikator.</span><span class="sxs-lookup"><span data-stu-id="a0ccb-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="a0ccb-113">Odwołania</span><span class="sxs-lookup"><span data-stu-id="a0ccb-113">References</span></span>

- [<span data-ttu-id="a0ccb-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="a0ccb-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)