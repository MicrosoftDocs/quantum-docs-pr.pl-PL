---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714924"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="838a5-102">SingleQubitProcessTomographyMeasurement, operacja</span><span class="sxs-lookup"><span data-stu-id="838a5-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="838a5-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="838a5-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="838a5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="838a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="838a5-105">Wykonuje pojedynczy qubit proces pomiaru Tomography w bazie Pauli, z uwzględnieniem konkretnego kanału zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="838a5-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="838a5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="838a5-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="838a5-107">Przygotowanie: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="838a5-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="838a5-108">Element Pauli $P $, w którym ma zostać przygotowany qubit.</span><span class="sxs-lookup"><span data-stu-id="838a5-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="838a5-109">Pomiar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="838a5-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="838a5-110">Element bazowy Pauli $Q $, w którym ma być mierzona wartość qubit.</span><span class="sxs-lookup"><span data-stu-id="838a5-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="838a5-111">Channel: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="838a5-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="838a5-112">Pojedynczy qubit kanału $ \Lambda $, którego zachowanie jest szacowane przy użyciu Tomography procesu.</span><span class="sxs-lookup"><span data-stu-id="838a5-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="838a5-113">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="838a5-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="838a5-114">Wynik `Zero` z prawdopodobieństwem $ $ \Begin{align} \Pr (\texttt{zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).</span><span class="sxs-lookup"><span data-stu-id="838a5-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="838a5-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="838a5-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="838a5-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="838a5-116">Remarks</span></span>

<span data-ttu-id="838a5-117">Dystrybucja względem wyników zwróconych przez tę operację jest szczególnym przypadkiem dwóch qubit stanu Tomography.</span><span class="sxs-lookup"><span data-stu-id="838a5-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="838a5-118">Let $ \rho = J (\Lambda)/$2 to stan Choi – Jamiłkowski dla $ \Lambda $.</span><span class="sxs-lookup"><span data-stu-id="838a5-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="838a5-119">Następnie powyższa dystrybucja jest taka sama jak $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ WHERE $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 to efektywne pomiary odpowiadające $P $ i $Q $.</span><span class="sxs-lookup"><span data-stu-id="838a5-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>