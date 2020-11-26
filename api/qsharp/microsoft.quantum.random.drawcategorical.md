---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192999"
---
# <a name="drawcategorical-operation"></a>DrawCategorical, operacja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Rysuje losową próbkę z dystrybucji kategorii określonej przez listę probablities.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Opis

Prawdopodobieństwo wyboru określonego indeksu jest proporcjonalne do wartości elementu tablicy w tym indeksie.
Elementy tablicy, które są równe zeru, są ignorowane, a ich indeksy nigdy nie są zwracane. Jeśli którykolwiek element tablicy jest mniejszy od zera lub żaden element tablicy nie jest większy niż zero, operacja kończy się niepowodzeniem.

## <a name="input"></a>Dane wejściowe

### <a name="probs--double"></a>PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)[]

Tablica liczb zmiennoprzecinkowych proporcjonalnie do prawdopodobieństwa zaznaczenia poszczególnych indeksów.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita $i $ z prawdopodobieństwem $ \Pr (i) = p_i/\ sum_i p_i $, gdzie $p _i $ to $i $ ty elementu `probs` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Random. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)