---
title: Ładowanie danych klasycznych
description: Dowiedz się, jak załadować własny zestaw danych, aby szkolić model klasyfikatora przy użyciu Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: cd6fdb6bb33a65ee02ac8c43f40df9abeff9c841
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833700"
---
# <a name="load-and-classify-your-own-datasets"></a>Załaduj i Klasyfikuj własne zestawy danych

W tym krótkim samouczku będziemy dowiedzieć się, jak załadować własny zestaw danych, aby szkolić model klasyfikatora przy użyciu zestawu Quantum Development Kit (QDK).

Zdecydowanie zalecamy użycie standardowego formatu serializacji, takiego jak [pliki JSON](https://en.wikipedia.org/wiki/JSON) do przechowywania danych.
Takie formaty oferują wysoką zgodność z różnymi strukturami, takimi jak Python i ekosystemem .NET.
W szczególności zalecamy używanie naszego szablonu do ładowania danych, dzięki czemu można kopiować kod bezpośrednio z przykładów.

## <a name="template-for-loading-your-datasets"></a>Szablon do ładowania zestawów danych

Załóżmy, że mamy zestaw danych szkoleniowych $ (x, y) $ o rozmiarze $N = $2, gdzie każde wystąpienie $x _i $ z $x $ ma trzy funkcje: $x _ {I1} $, $x _ {I2} $ i $x _ {i3} $.
Zestaw danych walidacji ma tę samą strukturę.
Datsets te mogą być reprezentowane przez `data.json` plik podobny do poniższego:

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>Przykład przy użyciu szablonu

Załóżmy, że mamy mały zestaw danych z wysokością i wagami różnych kotów i psów. Ten zestaw danych jest bardzo mały, aby szkolić model, ale będzie wystarczający do wyświetlania procesu ładowania zestawu danych.

| Wysokość (m) | Waga (kg) | Wtargnięcia zwierząt |
|-----------|------------|--------|
| 0,54      | 30         | Gięt    |
| 0,30      | 8          | Cat    |
| 0,91      | 44         | Gięt    |
| 0,86      | 31          | Gięt    |
| 0,32      | 5         | Cat    |
| 0,25      | 4          | Cat    |

Proces jest:

- Najpierw musimy rozdzielić zestaw danych na szkolenia i weryfikację. W takim przypadku możemy pobrać trzy pierwsze przykłady dla szkolenia i reszty przykładów do weryfikacji. Ogólnie rzecz biorąc, dobrym sposobem jest próbkowanie losowo przeszkolenie i sprawdzanie poprawności zestawu danych, aby uniknąć niepożądanych odchyleń danych szkoleniowych.
- Po drugie musimy przypisać etykietę liczbową do każdej klasy. Należy pamiętać, że w tym momencie Biblioteka QML tylko przyjmuje binarne problemy klasyfikacji. Dlatego do klasy zostanie przypisana etykieta 0 `Dog` i liczba 1 `Cat` .
- Na koniec Wypełnijmy szablon przy użyciu danych z naszego zestawu danych. Należy pamiętać, że w przypadku dużych zestawów danych należy utworzyć mały skrypt, aby automatycznie generować szablon z określonego zestawu danych. Ten skrypt będzie zależeć od oryginalnego formatu zestawu danych.

Dla naszego zestawu danych `data.json` plik jest:

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>Ładowanie danych

Gdy dane są serializowane jako plik JSON, można je załadować przy użyciu bibliotek JSON dostarczonych z wybranym językiem hosta.

### <a name="python"></a>[Python](#tab/tabid-python)

Język Python udostępnia [wbudowany `json` pakiet](https://docs.python.org/3.7/library/json.html) do pracy z danymi serializowanymi w formacie JSON:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

Platforma .NET Core udostępnia [ `System.Text.Json` pakiet](https://www.nuget.org/packages/System.Text.Json) do pracy z danymi serializowanymi w formacie JSON:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Następne kroki

Teraz wszystko jest gotowe do rozpoczęcia uruchamiania własnych eksperymentów z własnymi zestawami danych. Wypróbuj różne klasyfikatory i zestaw danych i współtworzyj społeczności, udostępniając Twoje wyniki.
