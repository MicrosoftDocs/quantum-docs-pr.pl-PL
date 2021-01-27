---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: ac254b7556878550216d5c0c9222620fdc5c5702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855930"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="79c88-102">ContinuousOracle typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="79c88-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="79c88-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="79c88-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="79c88-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79c88-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79c88-105">Reprezentuje ciągły czas Oracle.</span><span class="sxs-lookup"><span data-stu-id="79c88-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="79c88-106">Jest to Oracle, który implementuje $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ przez wszystkie czasy $t $, gdzie $U $ jest stałą operacją i gdzie $ \delta t $ jest nieujemną liczbą rzeczywistą.</span><span class="sxs-lookup"><span data-stu-id="79c88-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

