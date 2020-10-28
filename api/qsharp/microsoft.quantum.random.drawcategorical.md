---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720285"
---
# <a name="drawcategorical-operation"></a>DrawCategorical, operacja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package [](https://nuget.org/packages/)


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