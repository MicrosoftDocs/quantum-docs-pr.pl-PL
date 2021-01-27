---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854675"
---
# <a name="measureallz-operation"></a><span data-ttu-id="e82ab-102">MeasureAllZ, operacja</span><span class="sxs-lookup"><span data-stu-id="e82ab-102">MeasureAllZ operation</span></span>

<span data-ttu-id="e82ab-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e82ab-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e82ab-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e82ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e82ab-105">Wspólnie mierzy rejestr qubits na bazie Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="e82ab-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="e82ab-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e82ab-106">Description</span></span>

<span data-ttu-id="e82ab-107">Mierzy rejestr qubits w $Z \otimes Z \otimes \cdots \otimes Z $, reprezentujący parzystość całego rejestru.</span><span class="sxs-lookup"><span data-stu-id="e82ab-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="e82ab-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e82ab-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="e82ab-109">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e82ab-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e82ab-110">Rejestr, który ma być mierzony.</span><span class="sxs-lookup"><span data-stu-id="e82ab-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e82ab-111">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="e82ab-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="e82ab-112">Wynik pomiaru $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="e82ab-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>