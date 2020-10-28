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
# <a name="combinedstructure-function"></a>CombinedStructure, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


W przypadku co najmniej jednej warstwy sterowanych obrotów funkcja zwraca jedną warstwę z indeksem parametru modelu przesuniętą w taki sposób, że odrębne warstwy są sparametryzowane według odrębnych parametrów modelu.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Dane wejściowe

### <a name="layers--controlledrotation"></a>warstwy: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

Warstwy, które mają być połączone.



## <a name="output--controlledrotation"></a>Wynik: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Pojedyncza warstwa kontrolowanych rotacji, reprezentująca połączenie wszystkich innych warstw.