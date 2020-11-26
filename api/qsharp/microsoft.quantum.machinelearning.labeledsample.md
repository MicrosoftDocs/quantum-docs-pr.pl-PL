---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196331"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Przykład z etykietą z klasą, do której należy ten przykład.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="features--double"></a>Funkcje: [Double](xref:microsoft.quantum.lang-ref.double)[]

Wektor funkcji dla danego przykładu.
### <a name="label--int"></a>Etykieta: [int](xref:microsoft.quantum.lang-ref.int)

Etykieta liczb całkowitych dla klasy, do której należy ten przykład.