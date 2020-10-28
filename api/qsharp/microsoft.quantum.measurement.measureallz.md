---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711074"
---
# <a name="measureallz-operation"></a><span data-ttu-id="9b456-102">MeasureAllZ, operacja</span><span class="sxs-lookup"><span data-stu-id="9b456-102">MeasureAllZ operation</span></span>

<span data-ttu-id="9b456-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="9b456-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="9b456-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b456-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b456-105">Wspólnie mierzy rejestr qubits na bazie Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="9b456-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="9b456-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9b456-106">Description</span></span>

<span data-ttu-id="9b456-107">Mierzy rejestr qubits w $Z \otimes Z \otimes \cdots \otimes Z $, reprezentujący parzystość całego rejestru.</span><span class="sxs-lookup"><span data-stu-id="9b456-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="9b456-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9b456-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="9b456-109">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9b456-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9b456-110">Rejestr, który ma być mierzony.</span><span class="sxs-lookup"><span data-stu-id="9b456-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9b456-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="9b456-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="9b456-112">Wynik pomiaru $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="9b456-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>