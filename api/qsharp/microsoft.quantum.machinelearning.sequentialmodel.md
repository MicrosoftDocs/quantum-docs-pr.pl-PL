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
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Opisuje model klasyfikatora Quantum składający się z sekwencji sparametryzowanej i kontrolowanej rotacji, przypisywania kątów obrotu oraz różnicy między dwiema klasami rozpoznawanymi przez model.

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="structure--controlledrotation"></a>Struktura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Sekwencja kontrolowanych rotacji używanych do klasyfikowania danych wejściowych.
### <a name="parameters--double"></a>Parametry: [Double](xref:microsoft.quantum.lang-ref.double)[]

Przypisanie kątów obrotu do danej struktury klasyfikacji.
### <a name="bias--double"></a>Różnica: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Różnica między dwiema klasami rozpoznawanymi przez ten klasyfikator.

## <a name="references"></a>Odwołania

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)