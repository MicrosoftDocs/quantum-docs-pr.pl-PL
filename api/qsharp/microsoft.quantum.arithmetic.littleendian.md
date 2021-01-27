---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846565"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="ee3c1-102">LittleEndian typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="ee3c1-102">LittleEndian user defined type</span></span>

<span data-ttu-id="ee3c1-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ee3c1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ee3c1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee3c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee3c1-105">Zarejestruj, który koduje liczbę całkowitą bez znaku w kolejności little-endian.</span><span class="sxs-lookup"><span data-stu-id="ee3c1-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="ee3c1-106">Qubit z indeksem `0` koduje najniższy bit liczby całkowitej bez znaku.</span><span class="sxs-lookup"><span data-stu-id="ee3c1-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="ee3c1-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ee3c1-107">Remarks</span></span>

<span data-ttu-id="ee3c1-108">Skracamy `LittleEndian` `LE` się w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="ee3c1-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>