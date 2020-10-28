---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711335"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Przykład z etykietą z klasą, do której należy ten przykład.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="features--double"></a>Funkcje: [Double](xref:microsoft.quantum.lang-ref.double)[]

Wektor funkcji dla danego przykładu.
### <a name="label--int"></a>Etykieta: [int](xref:microsoft.quantum.lang-ref.int)

Etykieta liczb całkowitych dla klasy, do której należy ten przykład.