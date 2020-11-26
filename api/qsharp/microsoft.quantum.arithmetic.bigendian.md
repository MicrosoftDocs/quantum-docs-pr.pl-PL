---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223667"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="04cf0-102">BigEndian typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="04cf0-102">BigEndian user defined type</span></span>

<span data-ttu-id="04cf0-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="04cf0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="04cf0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04cf0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04cf0-105">Zarejestruj, który koduje liczbę całkowitą bez znaku w kolejności big-endian.</span><span class="sxs-lookup"><span data-stu-id="04cf0-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="04cf0-106">Qubit z indeksem `0` koduje największą liczbę liczb całkowitych bez znaku.</span><span class="sxs-lookup"><span data-stu-id="04cf0-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="04cf0-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="04cf0-107">Remarks</span></span>

<span data-ttu-id="04cf0-108">Skracamy `BigEndian` `BE` się w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="04cf0-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>