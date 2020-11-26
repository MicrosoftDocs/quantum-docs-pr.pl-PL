---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196416"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="7490f-102">FeatureRegisterSize, funkcja</span><span class="sxs-lookup"><span data-stu-id="7490f-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="7490f-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7490f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7490f-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7490f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7490f-105">Zwraca liczbę qubits wymaganych do zakodowania określonego wektora funkcji.</span><span class="sxs-lookup"><span data-stu-id="7490f-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="7490f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7490f-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="7490f-107">przykład: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7490f-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7490f-108">Przykładowy wektor funkcji, który ma zostać zakodowany w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="7490f-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="7490f-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7490f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7490f-110">Rozmiar wymagany do kodowania `sample` w rejestrze qubit wyrażony jako liczba qubits.</span><span class="sxs-lookup"><span data-stu-id="7490f-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>