---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856006"
---
# <a name="defaulttrainingoptions-function"></a>DefaultTrainingOptions, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Zwraca domyślny zestaw opcji dla klasyfikatora szkoleniowego.

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>Wynik: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Rozsądny zestaw domyślnych opcji szkolenia do użycia w przypadku klasyfikatorów szkoleniowych.

## <a name="example"></a>Przykład

Aby użyć opcji domyślnych, ale z dodatkowymi pomiarami, użyj `w/` operatora:

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```