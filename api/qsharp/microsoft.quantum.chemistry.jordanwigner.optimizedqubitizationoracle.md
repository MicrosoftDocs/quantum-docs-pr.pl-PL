---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle
title: OptimizedQubitizationOracle, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedQubitizationOracle
qsharp.summary: Returns T-count optimized Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: c67dc5890fe1444c1689eb803ed3d24b2dbe5ce2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713888"
---
# <a name="optimizedqubitizationoracle-function"></a><span data-ttu-id="4e1a5-102">OptimizedQubitizationOracle, funkcja</span><span class="sxs-lookup"><span data-stu-id="4e1a5-102">OptimizedQubitizationOracle function</span></span>

<span data-ttu-id="4e1a5-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4e1a5-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4e1a5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e1a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e1a5-105">Zwraca Qubitizationą optymalizację T-Count i parametry niezbędne do jej uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="4e1a5-105">Returns T-count optimized Qubitization operation and the parameters necessary to run it.</span></span>

```qsharp
function OptimizedQubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, targetError : Double) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="4e1a5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4e1a5-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="4e1a5-107">qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="4e1a5-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="4e1a5-108">Hamiltonian opisane przez `JordanWignerEncodingData` Format.</span><span class="sxs-lookup"><span data-stu-id="4e1a5-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="targeterror--double"></a><span data-ttu-id="4e1a5-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4e1a5-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4e1a5-110">Błąd kroku przygotowania stanu Auxillary.</span><span class="sxs-lookup"><span data-stu-id="4e1a5-110">Error of auxillary state preparation step.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="4e1a5-111">Output: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL))</span><span class="sxs-lookup"><span data-stu-id="4e1a5-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="4e1a5-112">Krotka, gdzie: `Int` jest liczbą przydzielonej qubits, `Double` jest jedną normą współczynników hamiltonian, a operacja jest przeszukiwaniem Quantum utworzonym przez Qubitization.</span><span class="sxs-lookup"><span data-stu-id="4e1a5-112">A tuple where: `Int` is the number of qubits allocated, `Double` is the one-norm of Hamiltonian coefficients, and the operation is the Quantum walk created by Qubitization.</span></span>