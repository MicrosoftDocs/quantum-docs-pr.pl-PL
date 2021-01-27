---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: cb4cf68753468952c7541fae23250ed1fd1914f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843366"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="80e8f-102">BigEndianAsLittleEndian, funkcja</span><span class="sxs-lookup"><span data-stu-id="80e8f-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="80e8f-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="80e8f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="80e8f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80e8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80e8f-105">Konwertuje `BigEndian` Rejestr qubit na `LittleEndian` Rejestr qubit przez odwrócenie kolejności qubit.</span><span class="sxs-lookup"><span data-stu-id="80e8f-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="80e8f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="80e8f-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="80e8f-107">dane wejściowe: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="80e8f-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="80e8f-108">Qubit w `BigEndian` formacie rejestru.</span><span class="sxs-lookup"><span data-stu-id="80e8f-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="80e8f-109">Wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="80e8f-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="80e8f-110">Qubit w `LittleEndian` formacie rejestru.</span><span class="sxs-lookup"><span data-stu-id="80e8f-110">Qubit register in `LittleEndian` format.</span></span>