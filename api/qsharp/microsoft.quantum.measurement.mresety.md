---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227033"
---
# <a name="mresety-operation"></a><span data-ttu-id="c6d96-102">MResetY, operacja</span><span class="sxs-lookup"><span data-stu-id="c6d96-102">MResetY operation</span></span>

<span data-ttu-id="c6d96-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="c6d96-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="c6d96-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c6d96-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c6d96-105">Mierzy pojedynczy qubit w bazie Y i resetuje go do ustalonego stanu początkowego po pomiar.</span><span class="sxs-lookup"><span data-stu-id="c6d96-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="c6d96-106">Opis</span><span class="sxs-lookup"><span data-stu-id="c6d96-106">Description</span></span>

<span data-ttu-id="c6d96-107">Wykonuje pomiar pojedynczej qubit na podstawie $Y $ i zapewnia, że qubit jest zwracany do $ \ket {0} $ po pomiarze.</span><span class="sxs-lookup"><span data-stu-id="c6d96-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="c6d96-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c6d96-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="c6d96-109">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c6d96-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c6d96-110">Pojedyncze qubit, które mają być mierzone.</span><span class="sxs-lookup"><span data-stu-id="c6d96-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c6d96-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="c6d96-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="c6d96-112">Wynik pomiaru `target` w Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="c6d96-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>