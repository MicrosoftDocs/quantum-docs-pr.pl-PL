---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: Operacja _prepareEntangledState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713132"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="acb49-102">Operacja _prepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="acb49-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="acb49-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="acb49-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="acb49-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="acb49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="acb49-105">W przypadku dwóch rejestrów przygotowuje stan Maximally Entangled między każdą parą qubits na odpowiednich rejestrach.</span><span class="sxs-lookup"><span data-stu-id="acb49-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="acb49-106">Wszystkie qubits muszą zostać uruchomione w stanie | 0 ⟩.</span><span class="sxs-lookup"><span data-stu-id="acb49-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="acb49-107">Wynikiem jest to, że odpowiadające pary qubits z poszczególnych rejestrów znajdują się w $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.</span><span class="sxs-lookup"><span data-stu-id="acb49-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="acb49-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="acb49-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="acb49-109">Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="acb49-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="acb49-110">Tablica qubit w stanie $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="acb49-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="acb49-111">Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="acb49-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="acb49-112">Tablica qubit w stanie $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="acb49-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="acb49-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="acb49-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

