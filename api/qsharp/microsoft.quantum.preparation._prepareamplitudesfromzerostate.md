---
uid: Microsoft.Quantum.Preparation._PrepareAmplitudesFromZeroState
title: Operacja _PrepareAmplitudesFromZeroState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _PrepareAmplitudesFromZeroState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients. Uses state emulation if supported by the target.
ms.openlocfilehash: 3d90b455bace7b0de1c8c01a5b9b007d719df950
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226591"
---
# <a name="_prepareamplitudesfromzerostate-operation"></a><span data-ttu-id="f851a-102">Operacja _PrepareAmplitudesFromZeroState</span><span class="sxs-lookup"><span data-stu-id="f851a-102">_PrepareAmplitudesFromZeroState operation</span></span>

<span data-ttu-id="f851a-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f851a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f851a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f851a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f851a-105">Na podstawie zestawu współczynników i zakodowanego w postaci little-endian rejestru Quantum unentangled qubits, wszystkie z nich są w stanie zero, przygotowuje stan tego rejestru opisany przez podane współczynniki.</span><span class="sxs-lookup"><span data-stu-id="f851a-105">Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients.</span></span> <span data-ttu-id="f851a-106">Używa emulacji stanu, jeśli jest obsługiwana przez element docelowy.</span><span class="sxs-lookup"><span data-stu-id="f851a-106">Uses state emulation if supported by the target.</span></span>

```qsharp
operation _PrepareAmplitudesFromZeroState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="f851a-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f851a-107">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="f851a-108">współczynniki: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="f851a-108">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>




### <a name="qubits--littleendian"></a><span data-ttu-id="f851a-109">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f851a-109">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="f851a-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f851a-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

