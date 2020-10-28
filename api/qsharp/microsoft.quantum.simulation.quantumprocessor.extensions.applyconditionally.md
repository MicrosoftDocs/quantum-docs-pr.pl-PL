---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: ApplyConditionally, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: fe623b240e35ee88f673b6e90db6307ef701d049
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710537"
---
# <a name="applyconditionally-operation"></a>ApplyConditionally, operacja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Package [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __nieprawidłowy <Result>__ []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __nieprawidłowy <Result>__ []




### <a name="onequalop--t--unit"></a>onEqualOp: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="equalarg--t"></a>equalArg: 'T




### <a name="onnonequalop--u--unit"></a>onNonEqualOp: ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


### <a name="u"></a>' U

