---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721356"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="72420-102">BigEndian typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="72420-102">BigEndian user defined type</span></span>

<span data-ttu-id="72420-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="72420-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="72420-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72420-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72420-105">Zarejestruj, który koduje liczbę całkowitą bez znaku w kolejności big-endian.</span><span class="sxs-lookup"><span data-stu-id="72420-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="72420-106">Qubit z indeksem `0` koduje największą liczbę liczb całkowitych bez znaku.</span><span class="sxs-lookup"><span data-stu-id="72420-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="72420-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="72420-107">Remarks</span></span>

<span data-ttu-id="72420-108">Skracamy `BigEndian` `BE` się w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="72420-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>