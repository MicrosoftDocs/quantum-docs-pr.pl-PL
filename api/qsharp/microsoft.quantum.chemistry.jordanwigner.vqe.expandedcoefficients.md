---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713715"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="9fe83-102">ExpandedCoefficients, funkcja</span><span class="sxs-lookup"><span data-stu-id="9fe83-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="9fe83-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="9fe83-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="9fe83-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fe83-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9fe83-105">Rozwija kompaktową reprezentację Jordan-Wigner współczynników, aby uzyskać mapowanie jeden do jednego między tymi i Pauli.</span><span class="sxs-lookup"><span data-stu-id="9fe83-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="9fe83-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9fe83-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="9fe83-107">coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9fe83-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9fe83-108">Tablica współczynników, jako przeczytana ze struktury danych Jordan-Wigner hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="9fe83-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="9fe83-109">termtype: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9fe83-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9fe83-110">Typ warunku Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="9fe83-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="9fe83-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9fe83-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9fe83-112">Rozwinięte tablice współczynników, jeden na termin Pauli.</span><span class="sxs-lookup"><span data-stu-id="9fe83-112">Expanded arrays of coefficients, one per Pauli term.</span></span>