---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193849"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="9b833-102">OracleToDiscrete, funkcja</span><span class="sxs-lookup"><span data-stu-id="9b833-102">OracleToDiscrete function</span></span>

<span data-ttu-id="9b833-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9b833-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9b833-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b833-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b833-105">W wyniku operacji reprezentowanej przez firmę Oracle "Black-Box" funkcja zwraca osobne oprogramowanie Oracle, które reprezentuje wielokrotnie powtórzone oprogramowanie Oracle.</span><span class="sxs-lookup"><span data-stu-id="9b833-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="9b833-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9b833-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="9b833-107">blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="9b833-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9b833-108">Operacja do exponentiated.</span><span class="sxs-lookup"><span data-stu-id="9b833-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="9b833-109">Wynik: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="9b833-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="9b833-110">Operacja częściowo zastosowana w odniesieniu do "czarnego" "firmy Oracle reprezentującej oprogramowanie Oracle w czasie dyskretnym</span><span class="sxs-lookup"><span data-stu-id="9b833-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>