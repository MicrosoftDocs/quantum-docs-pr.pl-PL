---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723286"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="0c9cf-102">FeatureRegisterSize, funkcja</span><span class="sxs-lookup"><span data-stu-id="0c9cf-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="0c9cf-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0c9cf-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0c9cf-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c9cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c9cf-105">Zwraca liczbę qubits wymaganych do zakodowania określonego wektora funkcji.</span><span class="sxs-lookup"><span data-stu-id="0c9cf-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="0c9cf-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0c9cf-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="0c9cf-107">przykład: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0c9cf-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0c9cf-108">Przykładowy wektor funkcji, który ma zostać zakodowany w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="0c9cf-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="0c9cf-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0c9cf-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0c9cf-110">Rozmiar wymagany do kodowania `sample` w rejestrze qubit wyrażony jako liczba qubits.</span><span class="sxs-lookup"><span data-stu-id="0c9cf-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>