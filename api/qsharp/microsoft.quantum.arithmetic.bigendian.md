---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843396"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="2278e-102">BigEndian typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="2278e-102">BigEndian user defined type</span></span>

<span data-ttu-id="2278e-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2278e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2278e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2278e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2278e-105">Zarejestruj, który koduje liczbę całkowitą bez znaku w kolejności big-endian.</span><span class="sxs-lookup"><span data-stu-id="2278e-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="2278e-106">Qubit z indeksem `0` koduje największą liczbę liczb całkowitych bez znaku.</span><span class="sxs-lookup"><span data-stu-id="2278e-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="2278e-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2278e-107">Remarks</span></span>

<span data-ttu-id="2278e-108">Skracamy `BigEndian` `BE` się w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="2278e-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>