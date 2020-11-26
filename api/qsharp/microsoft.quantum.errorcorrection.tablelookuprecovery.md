---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: e4136add99ab7fb6904d7cac3c7f3e5076cc3176
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213671"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="4881f-102">TableLookupRecovery, funkcja</span><span class="sxs-lookup"><span data-stu-id="4881f-102">TableLookupRecovery function</span></span>

<span data-ttu-id="4881f-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4881f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4881f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4881f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4881f-105">Dla danej tabeli operacji Pauli w danym rejestrze qubits, ta funkcja zwraca obiekt typu `RecoveryFn` , który zawiera wszystkie informacje, które są konieczne do wykonania dekodowania wyszukiwania w tabeli w odniesieniu do danej tablicy operacji Pauli.</span><span class="sxs-lookup"><span data-stu-id="4881f-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="4881f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4881f-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="4881f-107">Tabela: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="4881f-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="4881f-108">Tabela operacji Pauli, które działają na danym rejestrze qubit</span><span class="sxs-lookup"><span data-stu-id="4881f-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="4881f-109">Wynik: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="4881f-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="4881f-110">Obiekt typu `RecoveryFn` , czyli mapa, `Syndrome -> Pauli[]` która jest skojarzona z daną tablicą Syndrome odpowiednią operacją korekcji Pauli.</span><span class="sxs-lookup"><span data-stu-id="4881f-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>