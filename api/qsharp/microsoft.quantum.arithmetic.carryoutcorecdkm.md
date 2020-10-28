---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721305"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="259e3-102">CarryOutCoreCDKM, operacja</span><span class="sxs-lookup"><span data-stu-id="259e3-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="259e3-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="259e3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="259e3-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="259e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="259e3-105">Operacja podstawowa w RippleCarryAdderCDKM, używana z powyższą operacją ApplyOuterCDKMAdder, czyli sprzężona z tą operacją w celu uzyskania wewnętrznej operacji RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="259e3-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="259e3-106">Ta operacja oblicza qubit przeprowadzenia i stosuje sekwencję nieobecności bram w ramach danych wejściowych `ys` .</span><span class="sxs-lookup"><span data-stu-id="259e3-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="259e3-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="259e3-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="259e3-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="259e3-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="259e3-109">Pierwszy rejestr qubit.</span><span class="sxs-lookup"><span data-stu-id="259e3-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="259e3-110">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="259e3-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="259e3-111">Drugi rejestr qubit.</span><span class="sxs-lookup"><span data-stu-id="259e3-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="259e3-112">Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="259e3-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="259e3-113">Ancilla qubit używany w RippleCarryAdderCDKM przeszedł do tej operacji.</span><span class="sxs-lookup"><span data-stu-id="259e3-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="259e3-114">Przenieś: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="259e3-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="259e3-115">Przeprowadzenie qubit w operacji RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="259e3-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="259e3-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="259e3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="259e3-117">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="259e3-117">References</span></span>

- <span data-ttu-id="259e3-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum Ripple-przenieść obwód dodawania", 2004.</span><span class="sxs-lookup"><span data-stu-id="259e3-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1