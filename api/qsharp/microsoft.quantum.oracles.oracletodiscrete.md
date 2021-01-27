---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842534"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="25251-102">OracleToDiscrete, funkcja</span><span class="sxs-lookup"><span data-stu-id="25251-102">OracleToDiscrete function</span></span>

<span data-ttu-id="25251-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="25251-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="25251-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25251-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25251-105">W wyniku operacji reprezentowanej przez firmę Oracle "Black-Box" funkcja zwraca osobne oprogramowanie Oracle, które reprezentuje wielokrotnie powtórzone oprogramowanie Oracle.</span><span class="sxs-lookup"><span data-stu-id="25251-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="25251-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="25251-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="25251-107">blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="25251-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="25251-108">Operacja do exponentiated.</span><span class="sxs-lookup"><span data-stu-id="25251-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="25251-109">Wynik: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="25251-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="25251-110">Operacja częściowo zastosowana w odniesieniu do "czarnego" "firmy Oracle reprezentującej oprogramowanie Oracle w czasie dyskretnym</span><span class="sxs-lookup"><span data-stu-id="25251-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>

## <a name="example"></a><span data-ttu-id="25251-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="25251-111">Example</span></span>

<span data-ttu-id="25251-112">`OracleToDiscrete(U)(3, target)` jest równoważne `U(target)` powtórzonym trzykrotnie.</span><span class="sxs-lookup"><span data-stu-id="25251-112">`OracleToDiscrete(U)(3, target)` is equivalent to `U(target)` repeated three times.</span></span>