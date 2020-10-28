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
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


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

## <a name="references"></a>Dokumentacja

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)