---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingStep
title: Operacja _RunSingleTrainingStep
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingStep
qsharp.summary: attempts a single parameter update in the direction of mini batch gradient
ms.openlocfilehash: c40bf6f1ceecef2cb196846b4f5a1c49023f1f74
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720624"
---
# <a name="_runsingletrainingstep-operation"></a>Operacja _RunSingleTrainingStep

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


próbuje wykonać aktualizację pojedynczego parametru w kierunku gradientu mini Batch

```qsharp
operation _RunSingleTrainingStep (miniBatch : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel) : (Double, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>Dane wejściowe

### <a name="minibatch--labeledsamplestategenerator"></a>miniBatch: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []

kontener próbek oznaczonych etykietami w ramach minimalnej partii


### <a name="options--trainingoptions"></a>Opcje: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)




### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)





## <a name="output--doublesequentialmodel"></a>Dane wyjściowe: ([Double](xref:microsoft.quantum.lang-ref.double),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))

para (narzędzia, nowe) parametry