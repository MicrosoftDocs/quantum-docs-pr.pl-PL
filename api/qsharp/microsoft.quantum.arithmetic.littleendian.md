---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721044"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="026b3-102">LittleEndian typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="026b3-102">LittleEndian user defined type</span></span>

<span data-ttu-id="026b3-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="026b3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="026b3-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="026b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="026b3-105">Zarejestruj, który koduje liczbę całkowitą bez znaku w kolejności little-endian.</span><span class="sxs-lookup"><span data-stu-id="026b3-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="026b3-106">Qubit z indeksem `0` koduje najniższy bit liczby całkowitej bez znaku.</span><span class="sxs-lookup"><span data-stu-id="026b3-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="026b3-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="026b3-107">Remarks</span></span>

<span data-ttu-id="026b3-108">Skracamy `LittleEndian` `LE` się w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="026b3-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>