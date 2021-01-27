---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 204ae621b77559a894f0bce14e494824d58e4ad6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835395"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="ebd65-102">MeasurementOperators, funkcja</span><span class="sxs-lookup"><span data-stu-id="ebd65-102">MeasurementOperators function</span></span>

<span data-ttu-id="ebd65-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="ebd65-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="ebd65-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ebd65-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="ebd65-105">Oblicza wszystkie operatory pomiarów wymagane do obliczenia oczekiwania Jordan-Wigner warunku.</span><span class="sxs-lookup"><span data-stu-id="ebd65-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="ebd65-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ebd65-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="ebd65-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebd65-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebd65-108">Liczba qubits wymaganych do symulowania systemu cząsteczkowego.</span><span class="sxs-lookup"><span data-stu-id="ebd65-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="ebd65-109">indeksy: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ebd65-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ebd65-110">Tablica zawierająca indeksy qubit każdy operator Pauli jest stosowany do.</span><span class="sxs-lookup"><span data-stu-id="ebd65-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="ebd65-111">termtype: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebd65-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebd65-112">Typ warunku Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="ebd65-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="ebd65-113">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="ebd65-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="ebd65-114">Tablica operatorów pomiarów (każda jest tablicą Pauli).</span><span class="sxs-lookup"><span data-stu-id="ebd65-114">An array of measurement operators (each being an array of Pauli).</span></span>