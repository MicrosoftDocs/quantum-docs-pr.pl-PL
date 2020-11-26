---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211971"
---
# <a name="combinedstructure-function"></a>CombinedStructure, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


W przypadku co najmniej jednej warstwy sterowanych obrotów funkcja zwraca jedną warstwę z indeksem parametru modelu przesuniętą w taki sposób, że odrębne warstwy są sparametryzowane według odrębnych parametrów modelu.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Dane wejściowe

### <a name="layers--controlledrotation"></a>warstwy: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

Warstwy, które mają być połączone.



## <a name="output--controlledrotation"></a>Wynik: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Pojedyncza warstwa kontrolowanych rotacji, reprezentująca połączenie wszystkich innych warstw.