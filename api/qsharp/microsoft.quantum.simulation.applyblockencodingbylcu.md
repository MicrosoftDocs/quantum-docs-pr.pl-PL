---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 8ce6eb16b1dc5a83dd3a9559592c20d6b7b999b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225486"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="f8b62-102">ApplyBlockEncodingByLCU, operacja</span><span class="sxs-lookup"><span data-stu-id="f8b62-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="f8b62-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f8b62-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f8b62-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8b62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8b62-105">Implementacja programu `BlockEncodingByLCU` .</span><span class="sxs-lookup"><span data-stu-id="f8b62-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f8b62-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f8b62-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="f8b62-107">statePreparation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="f8b62-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="f8b62-108">Selektor: ('T,) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="f8b62-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="f8b62-109">pomocniczy: 'T</span><span class="sxs-lookup"><span data-stu-id="f8b62-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="f8b62-110">System:</span><span class="sxs-lookup"><span data-stu-id="f8b62-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="f8b62-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8b62-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f8b62-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f8b62-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8b62-113">'C</span><span class="sxs-lookup"><span data-stu-id="f8b62-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="f8b62-114">Przeglądarki</span><span class="sxs-lookup"><span data-stu-id="f8b62-114">'S</span></span>

