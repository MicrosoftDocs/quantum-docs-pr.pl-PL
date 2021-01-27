---
title: Ładowanie danych klasycznych
description: Dowiedz się, jak załadować własny zestaw danych, aby szkolić model klasyfikatora przy użyciu Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7ebfe085e50d4647fdb1027250cf3134f8d8f8c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856452"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="e40bd-103">Załaduj i Klasyfikuj własne zestawy danych</span><span class="sxs-lookup"><span data-stu-id="e40bd-103">Load and classify your own datasets</span></span>

<span data-ttu-id="e40bd-104">W tym krótkim samouczku będziemy dowiedzieć się, jak załadować własny zestaw danych, aby szkolić model klasyfikatora przy użyciu zestawu Quantum Development Kit (QDK).</span><span class="sxs-lookup"><span data-stu-id="e40bd-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="e40bd-105">Zdecydowanie zalecamy użycie standardowego formatu serializacji, takiego jak [pliki JSON](https://en.wikipedia.org/wiki/JSON) do przechowywania danych.</span><span class="sxs-lookup"><span data-stu-id="e40bd-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="e40bd-106">Takie formaty oferują wysoką zgodność z różnymi strukturami, takimi jak Python i ekosystemem .NET.</span><span class="sxs-lookup"><span data-stu-id="e40bd-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="e40bd-107">W szczególności zalecamy używanie naszego szablonu do ładowania danych, dzięki czemu można kopiować kod bezpośrednio z przykładów.</span><span class="sxs-lookup"><span data-stu-id="e40bd-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="e40bd-108">Szablon do ładowania zestawów danych</span><span class="sxs-lookup"><span data-stu-id="e40bd-108">Template for loading your datasets</span></span>

<span data-ttu-id="e40bd-109">Załóżmy, że mamy zestaw danych szkoleniowych $ (x, y) $ o rozmiarze $N = $2, gdzie każde wystąpienie $x _i $ z $x $ ma trzy funkcje: $x _ {I1} $, $x _ {I2} $ i $x _ {i3} $.</span><span class="sxs-lookup"><span data-stu-id="e40bd-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="e40bd-110">Zestaw danych walidacji ma tę samą strukturę.</span><span class="sxs-lookup"><span data-stu-id="e40bd-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="e40bd-111">Datsets te mogą być reprezentowane przez `data.json` plik podobny do poniższego:</span><span class="sxs-lookup"><span data-stu-id="e40bd-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

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

### <a name="example-using-the-template"></a><span data-ttu-id="e40bd-112">Przykład przy użyciu szablonu</span><span class="sxs-lookup"><span data-stu-id="e40bd-112">Example using the template</span></span>

<span data-ttu-id="e40bd-113">Załóżmy, że mamy mały zestaw danych z wysokością i wagami różnych kotów i psów.</span><span class="sxs-lookup"><span data-stu-id="e40bd-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="e40bd-114">Ten zestaw danych jest bardzo mały, aby szkolić model, ale będzie wystarczający do wyświetlania procesu ładowania zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="e40bd-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="e40bd-115">Wysokość (m)</span><span class="sxs-lookup"><span data-stu-id="e40bd-115">Height (m)</span></span> | <span data-ttu-id="e40bd-116">Waga (kg)</span><span class="sxs-lookup"><span data-stu-id="e40bd-116">Weight (kg)</span></span> | <span data-ttu-id="e40bd-117">Wtargnięcia zwierząt</span><span class="sxs-lookup"><span data-stu-id="e40bd-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="e40bd-118">0,54</span><span class="sxs-lookup"><span data-stu-id="e40bd-118">0.54</span></span>      | <span data-ttu-id="e40bd-119">30</span><span class="sxs-lookup"><span data-stu-id="e40bd-119">30</span></span>         | <span data-ttu-id="e40bd-120">Gięt</span><span class="sxs-lookup"><span data-stu-id="e40bd-120">Dog</span></span>    |
| <span data-ttu-id="e40bd-121">0,30</span><span class="sxs-lookup"><span data-stu-id="e40bd-121">0.30</span></span>      | <span data-ttu-id="e40bd-122">8</span><span class="sxs-lookup"><span data-stu-id="e40bd-122">8</span></span>          | <span data-ttu-id="e40bd-123">Kot</span><span class="sxs-lookup"><span data-stu-id="e40bd-123">Cat</span></span>    |
| <span data-ttu-id="e40bd-124">0,91</span><span class="sxs-lookup"><span data-stu-id="e40bd-124">0.91</span></span>      | <span data-ttu-id="e40bd-125">44</span><span class="sxs-lookup"><span data-stu-id="e40bd-125">44</span></span>         | <span data-ttu-id="e40bd-126">Gięt</span><span class="sxs-lookup"><span data-stu-id="e40bd-126">Dog</span></span>    |
| <span data-ttu-id="e40bd-127">0,86</span><span class="sxs-lookup"><span data-stu-id="e40bd-127">0.86</span></span>      | <span data-ttu-id="e40bd-128">31</span><span class="sxs-lookup"><span data-stu-id="e40bd-128">31</span></span>          | <span data-ttu-id="e40bd-129">Gięt</span><span class="sxs-lookup"><span data-stu-id="e40bd-129">Dog</span></span>    |
| <span data-ttu-id="e40bd-130">0,32</span><span class="sxs-lookup"><span data-stu-id="e40bd-130">0.32</span></span>      | <span data-ttu-id="e40bd-131">5</span><span class="sxs-lookup"><span data-stu-id="e40bd-131">5</span></span>         | <span data-ttu-id="e40bd-132">Kot</span><span class="sxs-lookup"><span data-stu-id="e40bd-132">Cat</span></span>    |
| <span data-ttu-id="e40bd-133">0,25</span><span class="sxs-lookup"><span data-stu-id="e40bd-133">0.25</span></span>      | <span data-ttu-id="e40bd-134">4</span><span class="sxs-lookup"><span data-stu-id="e40bd-134">4</span></span>          | <span data-ttu-id="e40bd-135">Kot</span><span class="sxs-lookup"><span data-stu-id="e40bd-135">Cat</span></span>    |

<span data-ttu-id="e40bd-136">Proces jest:</span><span class="sxs-lookup"><span data-stu-id="e40bd-136">The process is:</span></span>

- <span data-ttu-id="e40bd-137">Najpierw musimy rozdzielić zestaw danych na szkolenia i weryfikację.</span><span class="sxs-lookup"><span data-stu-id="e40bd-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="e40bd-138">W takim przypadku możemy pobrać trzy pierwsze przykłady dla szkolenia i reszty przykładów do weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="e40bd-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="e40bd-139">Ogólnie rzecz biorąc, dobrym sposobem jest próbkowanie losowo przeszkolenie i sprawdzanie poprawności zestawu danych, aby uniknąć niepożądanych odchyleń danych szkoleniowych.</span><span class="sxs-lookup"><span data-stu-id="e40bd-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="e40bd-140">Po drugie musimy przypisać etykietę liczbową do każdej klasy.</span><span class="sxs-lookup"><span data-stu-id="e40bd-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="e40bd-141">Należy pamiętać, że w tym momencie Biblioteka QML tylko przyjmuje binarne problemy klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="e40bd-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="e40bd-142">Dlatego do klasy zostanie przypisana etykieta 0 `Dog` i liczba 1 `Cat` .</span><span class="sxs-lookup"><span data-stu-id="e40bd-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="e40bd-143">Na koniec Wypełnijmy szablon przy użyciu danych z naszego zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="e40bd-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="e40bd-144">Należy pamiętać, że w przypadku dużych zestawów danych należy utworzyć mały skrypt, aby automatycznie generować szablon z określonego zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="e40bd-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="e40bd-145">Ten skrypt będzie zależeć od oryginalnego formatu zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="e40bd-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="e40bd-146">Dla naszego zestawu danych `data.json` plik jest:</span><span class="sxs-lookup"><span data-stu-id="e40bd-146">For our dataset the `data.json` file is:</span></span>

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

## <a name="loading-the-data"></a><span data-ttu-id="e40bd-147">Ładowanie danych</span><span class="sxs-lookup"><span data-stu-id="e40bd-147">Loading the data</span></span>

<span data-ttu-id="e40bd-148">Gdy dane są serializowane jako plik JSON, można je załadować przy użyciu bibliotek JSON dostarczonych z wybranym językiem hosta.</span><span class="sxs-lookup"><span data-stu-id="e40bd-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="e40bd-149">Python</span><span class="sxs-lookup"><span data-stu-id="e40bd-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="e40bd-150">Język Python udostępnia [wbudowany `json` pakiet](https://docs.python.org/3.7/library/json.html) do pracy z danymi serializowanymi w formacie JSON:</span><span class="sxs-lookup"><span data-stu-id="e40bd-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="e40bd-151">C#</span><span class="sxs-lookup"><span data-stu-id="e40bd-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="e40bd-152">Platforma .NET Core udostępnia [ `System.Text.Json` pakiet](https://www.nuget.org/packages/System.Text.Json) do pracy z danymi serializowanymi w formacie JSON:</span><span class="sxs-lookup"><span data-stu-id="e40bd-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="e40bd-153">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="e40bd-153">Next steps</span></span>

<span data-ttu-id="e40bd-154">Teraz wszystko jest gotowe do rozpoczęcia uruchamiania własnych eksperymentów z własnymi zestawami danych.</span><span class="sxs-lookup"><span data-stu-id="e40bd-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="e40bd-155">Wypróbuj różne klasyfikatory i zestaw danych i współtworzyj społeczności, udostępniając Twoje wyniki.</span><span class="sxs-lookup"><span data-stu-id="e40bd-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
