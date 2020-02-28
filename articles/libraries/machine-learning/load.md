---
title: Ładowanie danych klasycznych
description: Dowiedz się, jak załadować własny zestaw danych, aby szkolić model klasyfikatora przy użyciu Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: 15e63ced6223759a332ce22a43c133a7899f482a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909963"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="0ee60-103">Załaduj i Klasyfikuj własne zestawy danych</span><span class="sxs-lookup"><span data-stu-id="0ee60-103">Load and classify your own datasets</span></span>

<span data-ttu-id="0ee60-104">W tym krótkim samouczku będziemy dowiedzieć się, jak załadować własny zestaw danych, aby szkolić model klasyfikatora przy użyciu zestawu Quantum Development Kit (QDK).</span><span class="sxs-lookup"><span data-stu-id="0ee60-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="0ee60-105">Zdecydowanie zalecamy użycie standardowego formatu serializacji, takiego jak [pliki JSON](https://en.wikipedia.org/wiki/JSON) do przechowywania danych.</span><span class="sxs-lookup"><span data-stu-id="0ee60-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="0ee60-106">Takie formaty oferują wysoką zgodność z różnymi strukturami, takimi jak Python i ekosystemem .NET.</span><span class="sxs-lookup"><span data-stu-id="0ee60-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="0ee60-107">W szczególności zalecamy używanie naszego szablonu do ładowania danych, dzięki czemu można kopiować kod bezpośrednio z przykładów.</span><span class="sxs-lookup"><span data-stu-id="0ee60-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="0ee60-108">Szablon do ładowania zestawów danych</span><span class="sxs-lookup"><span data-stu-id="0ee60-108">Template for loading your datasets</span></span>

<span data-ttu-id="0ee60-109">Załóżmy, że mamy zestaw danych szkoleniowych $ (x, y) $ o rozmiarze $N = $2, gdzie każde wystąpienie $x _i $ z $x $ ma trzy funkcje: $x _ {I1} $, $x _ {I2} $ i $x _ {i3} $.</span><span class="sxs-lookup"><span data-stu-id="0ee60-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="0ee60-110">Zestaw danych walidacji ma tę samą strukturę.</span><span class="sxs-lookup"><span data-stu-id="0ee60-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="0ee60-111">Datsets te mogą być reprezentowane przez plik `data.json` podobny do poniższego:</span><span class="sxs-lookup"><span data-stu-id="0ee60-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

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

### <a name="example-using-the-template"></a><span data-ttu-id="0ee60-112">Przykład przy użyciu szablonu</span><span class="sxs-lookup"><span data-stu-id="0ee60-112">Example using the template</span></span>

<span data-ttu-id="0ee60-113">Załóżmy, że mamy mały zestaw danych z wysokością i wagami różnych kotów i psów.</span><span class="sxs-lookup"><span data-stu-id="0ee60-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="0ee60-114">Ten zestaw danych jest bardzo mały, aby szkolić model, ale będzie wystarczający do wyświetlania procesu ładowania zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="0ee60-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="0ee60-115">Wysokość (m)</span><span class="sxs-lookup"><span data-stu-id="0ee60-115">Height (m)</span></span> | <span data-ttu-id="0ee60-116">Waga (kg)</span><span class="sxs-lookup"><span data-stu-id="0ee60-116">Weight (kg)</span></span> | <span data-ttu-id="0ee60-117">Wtargnięcia zwierząt</span><span class="sxs-lookup"><span data-stu-id="0ee60-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="0ee60-118">0,54</span><span class="sxs-lookup"><span data-stu-id="0ee60-118">0.54</span></span>      | <span data-ttu-id="0ee60-119">30</span><span class="sxs-lookup"><span data-stu-id="0ee60-119">30</span></span>         | <span data-ttu-id="0ee60-120">Gięt</span><span class="sxs-lookup"><span data-stu-id="0ee60-120">Dog</span></span>    |
| <span data-ttu-id="0ee60-121">0,30</span><span class="sxs-lookup"><span data-stu-id="0ee60-121">0.30</span></span>      | <span data-ttu-id="0ee60-122">8</span><span class="sxs-lookup"><span data-stu-id="0ee60-122">8</span></span>          | <span data-ttu-id="0ee60-123">Cat</span><span class="sxs-lookup"><span data-stu-id="0ee60-123">Cat</span></span>    |
| <span data-ttu-id="0ee60-124">0,91</span><span class="sxs-lookup"><span data-stu-id="0ee60-124">0.91</span></span>      | <span data-ttu-id="0ee60-125">44</span><span class="sxs-lookup"><span data-stu-id="0ee60-125">44</span></span>         | <span data-ttu-id="0ee60-126">Gięt</span><span class="sxs-lookup"><span data-stu-id="0ee60-126">Dog</span></span>    |
| <span data-ttu-id="0ee60-127">0,86</span><span class="sxs-lookup"><span data-stu-id="0ee60-127">0.86</span></span>      | <span data-ttu-id="0ee60-128">31</span><span class="sxs-lookup"><span data-stu-id="0ee60-128">31</span></span>          | <span data-ttu-id="0ee60-129">Gięt</span><span class="sxs-lookup"><span data-stu-id="0ee60-129">Dog</span></span>    |
| <span data-ttu-id="0ee60-130">0,32</span><span class="sxs-lookup"><span data-stu-id="0ee60-130">0.32</span></span>      | <span data-ttu-id="0ee60-131">5</span><span class="sxs-lookup"><span data-stu-id="0ee60-131">5</span></span>         | <span data-ttu-id="0ee60-132">Cat</span><span class="sxs-lookup"><span data-stu-id="0ee60-132">Cat</span></span>    |
| <span data-ttu-id="0ee60-133">0.25</span><span class="sxs-lookup"><span data-stu-id="0ee60-133">0.25</span></span>      | <span data-ttu-id="0ee60-134">4</span><span class="sxs-lookup"><span data-stu-id="0ee60-134">4</span></span>          | <span data-ttu-id="0ee60-135">Cat</span><span class="sxs-lookup"><span data-stu-id="0ee60-135">Cat</span></span>    |

<span data-ttu-id="0ee60-136">Ten proces to:</span><span class="sxs-lookup"><span data-stu-id="0ee60-136">The process is:</span></span>

- <span data-ttu-id="0ee60-137">Najpierw musimy rozdzielić zestaw danych na szkolenia i weryfikację.</span><span class="sxs-lookup"><span data-stu-id="0ee60-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="0ee60-138">W takim przypadku możemy pobrać trzy pierwsze przykłady dla szkolenia i reszty przykładów do weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="0ee60-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="0ee60-139">Ogólnie rzecz biorąc, dobrym sposobem jest próbkowanie losowo przeszkolenie i sprawdzanie poprawności zestawu danych, aby uniknąć niepożądanych odchyleń danych szkoleniowych.</span><span class="sxs-lookup"><span data-stu-id="0ee60-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="0ee60-140">Po drugie musimy przypisać etykietę liczbową do każdej klasy.</span><span class="sxs-lookup"><span data-stu-id="0ee60-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="0ee60-141">Należy pamiętać, że w tym momencie Biblioteka QML tylko przyjmuje binarne problemy klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="0ee60-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="0ee60-142">Dlatego przypiszemy etykietę 0 do klasy `Dog` i liczbę 1 do klasy `Cat`.</span><span class="sxs-lookup"><span data-stu-id="0ee60-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="0ee60-143">Na koniec Wypełnijmy szablon przy użyciu danych z naszego zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="0ee60-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="0ee60-144">Należy pamiętać, że w przypadku dużych zestawów danych należy utworzyć mały skrypt, aby automatycznie generować szablon z określonego zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="0ee60-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="0ee60-145">Ten skrypt będzie zależeć od oryginalnego formatu zestawu danych.</span><span class="sxs-lookup"><span data-stu-id="0ee60-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="0ee60-146">Dla naszego zestawu danych `data.json` plik jest:</span><span class="sxs-lookup"><span data-stu-id="0ee60-146">For our dataset the `data.json` file is:</span></span>

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

## <a name="loading-the-data"></a><span data-ttu-id="0ee60-147">Ładowanie danych</span><span class="sxs-lookup"><span data-stu-id="0ee60-147">Loading the data</span></span>

<span data-ttu-id="0ee60-148">Gdy dane są serializowane jako plik JSON, można je załadować przy użyciu bibliotek JSON dostarczonych z wybranym językiem hosta.</span><span class="sxs-lookup"><span data-stu-id="0ee60-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="0ee60-149">Python</span><span class="sxs-lookup"><span data-stu-id="0ee60-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="0ee60-150">Język Python udostępnia [wbudowany pakiet `json`](https://docs.python.org/3.7/library/json.html) do pracy z danymi serializowanymi w formacie JSON:</span><span class="sxs-lookup"><span data-stu-id="0ee60-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="0ee60-151">C#</span><span class="sxs-lookup"><span data-stu-id="0ee60-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="0ee60-152">Platforma .NET Core udostępnia [pakiet`System.Text.Json`](https://www.nuget.org/packages/System.Text.Json) do pracy z danymi serializowanymi w formacie JSON:</span><span class="sxs-lookup"><span data-stu-id="0ee60-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="whats-next"></a><span data-ttu-id="0ee60-153">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="0ee60-153">What's next?</span></span>

<span data-ttu-id="0ee60-154">Teraz wszystko jest gotowe do rozpoczęcia uruchamiania własnych eksperymentów z własnymi zestawami danych.</span><span class="sxs-lookup"><span data-stu-id="0ee60-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="0ee60-155">Wypróbuj różne klasyfikatory i zestaw danych i współtworzyj społeczności, udostępniając Twoje wyniki.</span><span class="sxs-lookup"><span data-stu-id="0ee60-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
