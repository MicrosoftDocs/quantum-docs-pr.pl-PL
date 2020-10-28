---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720516"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="976dc-102">CombinedStructure, funkcja</span><span class="sxs-lookup"><span data-stu-id="976dc-102">CombinedStructure function</span></span>

<span data-ttu-id="976dc-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="976dc-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="976dc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="976dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="976dc-105">W przypadku co najmniej jednej warstwy sterowanych obrotów funkcja zwraca jedną warstwę z indeksem parametru modelu przesuniętą w taki sposób, że odrębne warstwy są sparametryzowane według odrębnych parametrów modelu.</span><span class="sxs-lookup"><span data-stu-id="976dc-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="976dc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="976dc-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="976dc-107">warstwy: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="976dc-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="976dc-108">Warstwy, które mają być połączone.</span><span class="sxs-lookup"><span data-stu-id="976dc-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="976dc-109">Wynik: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="976dc-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="976dc-110">Pojedyncza warstwa kontrolowanych rotacji, reprezentująca połączenie wszystkich innych warstw.</span><span class="sxs-lookup"><span data-stu-id="976dc-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>