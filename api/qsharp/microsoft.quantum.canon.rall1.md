---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 45892f9811faf56d7b9a0eb34e4bde0a32d5586d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715624"
---
# <a name="rall1-operation"></a><span data-ttu-id="81bc0-102">RAll1, operacja</span><span class="sxs-lookup"><span data-stu-id="81bc0-102">RAll1 operation</span></span>

<span data-ttu-id="81bc0-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="81bc0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="81bc0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81bc0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81bc0-105">Wykonuje operację przesunięcia fazy.</span><span class="sxs-lookup"><span data-stu-id="81bc0-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="81bc0-106">$R = \boldone-(1-e ^ {i \phi}) \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="81bc0-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="81bc0-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="81bc0-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="81bc0-108">Faza: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81bc0-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81bc0-109">Faza $ \phi $ została zastosowana do stanu $ \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="81bc0-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="81bc0-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="81bc0-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="81bc0-111">Rejestr, którego stan ma zostać obrócony przez $R $.</span><span class="sxs-lookup"><span data-stu-id="81bc0-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81bc0-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81bc0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

