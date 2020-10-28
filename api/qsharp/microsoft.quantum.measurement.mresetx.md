---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725003"
---
# <a name="mresetx-operation"></a><span data-ttu-id="c64a6-102">MResetX, operacja</span><span class="sxs-lookup"><span data-stu-id="c64a6-102">MResetX operation</span></span>

<span data-ttu-id="c64a6-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="c64a6-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="c64a6-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c64a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c64a6-105">Mierzy pojedynczy qubit w bazie X, a następnie resetuje go do ustalonego stanu początkowego po pomiar.</span><span class="sxs-lookup"><span data-stu-id="c64a6-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="c64a6-106">Opis</span><span class="sxs-lookup"><span data-stu-id="c64a6-106">Description</span></span>

<span data-ttu-id="c64a6-107">Wykonuje pomiar pojedynczej qubit na podstawie $X $ i zapewnia, że qubit jest zwracany do $ \ket {0} $ po pomiarze.</span><span class="sxs-lookup"><span data-stu-id="c64a6-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="c64a6-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c64a6-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="c64a6-109">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c64a6-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c64a6-110">Pojedyncze qubit, które mają być mierzone.</span><span class="sxs-lookup"><span data-stu-id="c64a6-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c64a6-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="c64a6-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="c64a6-112">Wynik pomiaru `target` w Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="c64a6-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>