---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 0a40d9674c011567b2fa9c838f31a0ee115e4268
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826077"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="5dcfb-102">FiveQubitCodeEncoderImpl, operacja</span><span class="sxs-lookup"><span data-stu-id="5dcfb-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="5dcfb-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="5dcfb-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="5dcfb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5dcfb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5dcfb-105">Operacja prywatna używana do implementowania zarówno kodera qubit, jak i dekodera.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5dcfb-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5dcfb-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="5dcfb-107">dane: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5dcfb-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5dcfb-108">Tablica zawierająca 1 qubit, która jest wejściowym qubit.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="5dcfb-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5dcfb-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5dcfb-110">Tablica zawierająca 4 qubits, która umożliwia dodawanie nadmiarowości.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5dcfb-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5dcfb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5dcfb-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5dcfb-112">Remarks</span></span>

<span data-ttu-id="5dcfb-113">Wybrany koder został pobrany z papieru V. Kliuchnikov i D. Maslov, "Optymalizacja obwodów Clifford," Bio. Rev. cz. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Rysunek 4b) i wymaga łącznie 11 bram.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>