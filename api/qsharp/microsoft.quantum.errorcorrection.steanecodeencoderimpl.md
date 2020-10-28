---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712189"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="9ccc8-102">SteaneCodeEncoderImpl, operacja</span><span class="sxs-lookup"><span data-stu-id="9ccc8-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="9ccc8-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9ccc8-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9ccc8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ccc8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ccc8-105">Operacja prywatna używana do implementowania zarówno kodera kodu Steane, jak i dekodera.</span><span class="sxs-lookup"><span data-stu-id="9ccc8-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9ccc8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9ccc8-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="9ccc8-107">dane: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9ccc8-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9ccc8-108">Tablica zawierająca 1 qubit, która jest wejściowym qubit.</span><span class="sxs-lookup"><span data-stu-id="9ccc8-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="9ccc8-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9ccc8-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9ccc8-110">Tablica zawierająca 6 qubits, która umożliwia dodawanie nadmiarowości.</span><span class="sxs-lookup"><span data-stu-id="9ccc8-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ccc8-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ccc8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

