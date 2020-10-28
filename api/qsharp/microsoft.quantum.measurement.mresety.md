---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725008"
---
# <a name="mresety-operation"></a><span data-ttu-id="8d73d-102">MResetY, operacja</span><span class="sxs-lookup"><span data-stu-id="8d73d-102">MResetY operation</span></span>

<span data-ttu-id="8d73d-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="8d73d-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="8d73d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d73d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d73d-105">Mierzy pojedynczy qubit w bazie Y i resetuje go do ustalonego stanu początkowego po pomiar.</span><span class="sxs-lookup"><span data-stu-id="8d73d-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="8d73d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="8d73d-106">Description</span></span>

<span data-ttu-id="8d73d-107">Wykonuje pomiar pojedynczej qubit na podstawie $Y $ i zapewnia, że qubit jest zwracany do $ \ket {0} $ po pomiarze.</span><span class="sxs-lookup"><span data-stu-id="8d73d-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="8d73d-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8d73d-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="8d73d-109">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8d73d-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8d73d-110">Pojedyncze qubit, które mają być mierzone.</span><span class="sxs-lookup"><span data-stu-id="8d73d-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="8d73d-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="8d73d-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="8d73d-112">Wynik pomiaru `target` w Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="8d73d-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>