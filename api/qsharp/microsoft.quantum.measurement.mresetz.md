---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853737"
---
# <a name="mresetz-operation"></a><span data-ttu-id="56a31-102">MResetZ, operacja</span><span class="sxs-lookup"><span data-stu-id="56a31-102">MResetZ operation</span></span>

<span data-ttu-id="56a31-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="56a31-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="56a31-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="56a31-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="56a31-105">Mierzy pojedynczy qubit w bazie Z i resetuje go do ustalonego stanu początkowego po pomiar.</span><span class="sxs-lookup"><span data-stu-id="56a31-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="56a31-106">Opis</span><span class="sxs-lookup"><span data-stu-id="56a31-106">Description</span></span>

<span data-ttu-id="56a31-107">Wykonuje pomiar pojedynczej qubit na podstawie $Z $ i zapewnia, że qubit jest zwracany do $ \ket {0} $ po pomiarze.</span><span class="sxs-lookup"><span data-stu-id="56a31-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="56a31-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="56a31-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="56a31-109">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="56a31-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="56a31-110">Pojedyncze qubit, które mają być mierzone.</span><span class="sxs-lookup"><span data-stu-id="56a31-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="56a31-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="56a31-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="56a31-112">Wynik pomiaru `target` w Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="56a31-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>