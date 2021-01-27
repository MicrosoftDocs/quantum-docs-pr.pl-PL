---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: 3991ded1a9c70bf4b58d19b0304a1df3b31896d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842017"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="cba13-102">ApplyAndChain, operacja</span><span class="sxs-lookup"><span data-stu-id="cba13-102">ApplyAndChain operation</span></span>

<span data-ttu-id="cba13-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cba13-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cba13-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cba13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cba13-105">Oblicza łańcuchy i bramy</span><span class="sxs-lookup"><span data-stu-id="cba13-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="cba13-106">Opis</span><span class="sxs-lookup"><span data-stu-id="cba13-106">Description</span></span>

<span data-ttu-id="cba13-107">Pomocnicza qubits do obliczenia wyników tymczasowych musi być określona jawnie.</span><span class="sxs-lookup"><span data-stu-id="cba13-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="cba13-108">Długość tego rejestru ma miejsce `Length(ctrlRegister) - 2` , jeśli istnieją co najmniej dwie kontrolki, w przeciwnym razie długość wynosi 0.</span><span class="sxs-lookup"><span data-stu-id="cba13-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="cba13-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cba13-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="cba13-110">auxRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cba13-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="cba13-111">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cba13-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="cba13-112">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cba13-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="cba13-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cba13-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

