---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 6185e66e08d2af3aa0b35791638820b4dcc5af35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715633"
---
# <a name="rall0-operation"></a><span data-ttu-id="a9198-102">RAll0, operacja</span><span class="sxs-lookup"><span data-stu-id="a9198-102">RAll0 operation</span></span>

<span data-ttu-id="a9198-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a9198-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a9198-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9198-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9198-105">Wykonuje operację przesunięcia fazy.</span><span class="sxs-lookup"><span data-stu-id="a9198-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="a9198-106">$R = \boldone-(1-e ^ {i \phi}) \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="a9198-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a9198-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a9198-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="a9198-108">Faza: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9198-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a9198-109">Faza $ \phi $ zastosowana do stanu $ \ket{0\cdots 0} \bra{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="a9198-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a9198-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a9198-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a9198-111">Rejestr, którego stan ma zostać obrócony przez $R $.</span><span class="sxs-lookup"><span data-stu-id="a9198-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9198-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9198-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a9198-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a9198-113">See Also</span></span>

- [<span data-ttu-id="a9198-114">Microsoft. Quantum. Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="a9198-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)