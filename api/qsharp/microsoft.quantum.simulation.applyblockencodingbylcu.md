---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722124"
---
# <a name="applyblockencodingbylcu-operation"></a>ApplyBlockEncodingByLCU, operacja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Implementacja programu `BlockEncodingByLCU` .

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="selector--ts--unit-adj--ctl"></a>Selektor: (t,) => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="auxiliary--t"></a>pomocniczy: 'T




### <a name="system--s"></a>System:





## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


### <a name="s"></a>Przeglądarki
