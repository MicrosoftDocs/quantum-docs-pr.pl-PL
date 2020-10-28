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
# <a name="featureregistersize-function"></a>FeatureRegisterSize, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Zwraca liczbę qubits wymaganych do zakodowania określonego wektora funkcji.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="sample--double"></a>przykład: [Double](xref:microsoft.quantum.lang-ref.double)[]

Przykładowy wektor funkcji, który ma zostać zakodowany w rejestrze qubit.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Rozmiar wymagany do kodowania `sample` w rejestrze qubit wyrażony jako liczba qubits.