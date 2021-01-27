---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848443"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="02a92-102">FeatureRegisterSize, funkcja</span><span class="sxs-lookup"><span data-stu-id="02a92-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="02a92-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="02a92-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="02a92-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="02a92-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="02a92-105">Zwraca liczbę qubits wymaganych do zakodowania określonego wektora funkcji.</span><span class="sxs-lookup"><span data-stu-id="02a92-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="02a92-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="02a92-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="02a92-107">przykład: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="02a92-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="02a92-108">Przykładowy wektor funkcji, który ma zostać zakodowany w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="02a92-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="02a92-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="02a92-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="02a92-110">Rozmiar wymagany do kodowania `sample` w rejestrze qubit wyrażony jako liczba qubits.</span><span class="sxs-lookup"><span data-stu-id="02a92-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>