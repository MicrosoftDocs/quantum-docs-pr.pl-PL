---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222783"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="ab847-102">LittleEndian typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="ab847-102">LittleEndian user defined type</span></span>

<span data-ttu-id="ab847-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ab847-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ab847-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab847-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab847-105">Zarejestruj, który koduje liczbę całkowitą bez znaku w kolejności little-endian.</span><span class="sxs-lookup"><span data-stu-id="ab847-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="ab847-106">Qubit z indeksem `0` koduje najniższy bit liczby całkowitej bez znaku.</span><span class="sxs-lookup"><span data-stu-id="ab847-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="ab847-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ab847-107">Remarks</span></span>

<span data-ttu-id="ab847-108">Skracamy `LittleEndian` `LE` się w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="ab847-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>