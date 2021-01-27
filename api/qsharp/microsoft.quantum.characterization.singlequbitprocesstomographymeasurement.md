---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839652"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="6f490-102">SingleQubitProcessTomographyMeasurement, operacja</span><span class="sxs-lookup"><span data-stu-id="6f490-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="6f490-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="6f490-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="6f490-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f490-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f490-105">Wykonuje pojedynczy qubit proces pomiaru Tomography w bazie Pauli, z uwzględnieniem konkretnego kanału zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="6f490-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="6f490-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6f490-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="6f490-107">Przygotowanie: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="6f490-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="6f490-108">Element Pauli $P $, w którym ma zostać przygotowany qubit.</span><span class="sxs-lookup"><span data-stu-id="6f490-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="6f490-109">Pomiar: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="6f490-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="6f490-110">Element bazowy Pauli $Q $, w którym ma być mierzona wartość qubit.</span><span class="sxs-lookup"><span data-stu-id="6f490-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="6f490-111">Channel: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f490-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6f490-112">Pojedynczy qubit kanału $ \Lambda $, którego zachowanie jest szacowane przy użyciu Tomography procesu.</span><span class="sxs-lookup"><span data-stu-id="6f490-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6f490-113">Dane wyjściowe __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="6f490-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6f490-114">Wynik `Zero` z prawdopodobieństwem $ $ \Begin{align} \Pr (\texttt{zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).</span><span class="sxs-lookup"><span data-stu-id="6f490-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="6f490-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="6f490-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="6f490-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6f490-116">Remarks</span></span>

<span data-ttu-id="6f490-117">Dystrybucja względem wyników zwróconych przez tę operację jest szczególnym przypadkiem dwóch qubit stanu Tomography.</span><span class="sxs-lookup"><span data-stu-id="6f490-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="6f490-118">Let $ \rho = J (\Lambda)/$2 to stan Choi – Jamiłkowski dla $ \Lambda $.</span><span class="sxs-lookup"><span data-stu-id="6f490-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="6f490-119">Następnie powyższa dystrybucja jest taka sama jak $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ WHERE $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 to efektywne pomiary odpowiadające $P $ i $Q $.</span><span class="sxs-lookup"><span data-stu-id="6f490-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>