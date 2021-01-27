---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846977"
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