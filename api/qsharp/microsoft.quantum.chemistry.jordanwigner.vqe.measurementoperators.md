---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: a5ea9a776f522e927f2f4545bd417d35bda83994
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214351"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="8ffb8-102">MeasurementOperators, funkcja</span><span class="sxs-lookup"><span data-stu-id="8ffb8-102">MeasurementOperators function</span></span>

<span data-ttu-id="8ffb8-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="8ffb8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="8ffb8-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="8ffb8-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="8ffb8-105">Oblicza wszystkie operatory pomiarów wymagane do obliczenia oczekiwania Jordan-Wigner warunku.</span><span class="sxs-lookup"><span data-stu-id="8ffb8-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="8ffb8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8ffb8-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="8ffb8-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ffb8-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ffb8-108">Liczba qubits wymaganych do symulowania systemu cząsteczkowego.</span><span class="sxs-lookup"><span data-stu-id="8ffb8-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="8ffb8-109">indeksy: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8ffb8-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8ffb8-110">Tablica zawierająca indeksy qubit każdy operator Pauli jest stosowany do.</span><span class="sxs-lookup"><span data-stu-id="8ffb8-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="8ffb8-111">termtype: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ffb8-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ffb8-112">Typ warunku Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="8ffb8-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="8ffb8-113">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="8ffb8-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="8ffb8-114">Tablica operatorów pomiarów (każda jest tablicą Pauli).</span><span class="sxs-lookup"><span data-stu-id="8ffb8-114">An array of measurement operators (each being an array of Pauli).</span></span>