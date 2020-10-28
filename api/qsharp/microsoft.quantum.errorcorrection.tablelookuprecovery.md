---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712049"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="1640c-102">TableLookupRecovery, funkcja</span><span class="sxs-lookup"><span data-stu-id="1640c-102">TableLookupRecovery function</span></span>

<span data-ttu-id="1640c-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1640c-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1640c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1640c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1640c-105">Dla danej tabeli operacji Pauli w danym rejestrze qubits, ta funkcja zwraca obiekt typu `RecoveryFn` , który zawiera wszystkie informacje, które są konieczne do wykonania dekodowania wyszukiwania w tabeli w odniesieniu do danej tablicy operacji Pauli.</span><span class="sxs-lookup"><span data-stu-id="1640c-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="1640c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1640c-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="1640c-107">Tabela: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="1640c-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="1640c-108">Tabela operacji Pauli, które działają na danym rejestrze qubit</span><span class="sxs-lookup"><span data-stu-id="1640c-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="1640c-109">Wynik: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="1640c-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="1640c-110">Obiekt typu `RecoveryFn` , czyli mapa, `Syndrome -> Pauli[]` która jest skojarzona z daną tablicą Syndrome odpowiednią operacją korekcji Pauli.</span><span class="sxs-lookup"><span data-stu-id="1640c-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>