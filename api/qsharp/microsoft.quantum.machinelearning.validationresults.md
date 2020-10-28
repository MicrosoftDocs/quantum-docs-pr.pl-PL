---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720429"
---
# <a name="validationresults-user-defined-type"></a>ValidationResults typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Wyniki weryfikacji klasyfikatora względem zestawu próbek.

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="nmisclassifications--int"></a>NMisclassifications: [int](xref:microsoft.quantum.lang-ref.int)

Liczba błędnych klasyfikacji zaobserwowanych podczas walidacji.
### <a name="nvalidationsamples--int"></a>NValidationSamples: [int](xref:microsoft.quantum.lang-ref.int)

