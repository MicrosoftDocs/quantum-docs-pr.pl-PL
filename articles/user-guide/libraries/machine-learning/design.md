---
title: Projektowanie własnego klasyfikatora przy użyciu QDK
description: Zapoznaj się z podstawowymi pojęciami dotyczącymi projektowania modeli obwodów dla klasyfikatora zorientowanego obwodu Quantum.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: b304b9d1a15f164f4dfe758aaed31b7b2369b18c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276036"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="47ad6-103">Projektowanie własnego klasyfikatora</span><span class="sxs-lookup"><span data-stu-id="47ad6-103">Design your own classifier</span></span>

<span data-ttu-id="47ad6-104">W tym przewodniku przedstawiono podstawowe pojęcia związane z projektowaniem modeli obwodów dla klasyfikatora zorientowanego obwodu Quantum.</span><span class="sxs-lookup"><span data-stu-id="47ad6-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="47ad6-105">Podobnie jak w przypadku klasycznej uczenia głębokiego, nie ma żadnej ogólnej reguły wyboru określonej architektury.</span><span class="sxs-lookup"><span data-stu-id="47ad6-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="47ad6-106">W zależności od problemu niektóre architektury będą działać lepiej niż inne.</span><span class="sxs-lookup"><span data-stu-id="47ad6-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="47ad6-107">Ale istnieją pewne koncepcje, które mogą być przydatne podczas projektowania obwodu:</span><span class="sxs-lookup"><span data-stu-id="47ad6-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="47ad6-108">Duża liczba parametrów implikuje bardziej elastyczny model, który może być odpowiedni do rysowania złożonych granic klasyfikacji, ale może być również bardziej podatny na zamontowanie.</span><span class="sxs-lookup"><span data-stu-id="47ad6-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="47ad6-109">Bramy Entangling między qubitsami są niezbędne do przechwytywania korelacji między funkcjami Quantum.</span><span class="sxs-lookup"><span data-stu-id="47ad6-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="47ad6-110">Jak utworzyć klasyfikator przy użyciu Q\#</span><span class="sxs-lookup"><span data-stu-id="47ad6-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="47ad6-111">Aby skompilować klasyfikator, zamierzamy połączyć kontrolowane rotacje w modelu obwodu.</span><span class="sxs-lookup"><span data-stu-id="47ad6-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="47ad6-112">Aby to zrobić, można użyć typu [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) zdefiniowanego w bibliotece Quantum Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="47ad6-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="47ad6-113">Ten typ akceptuje cztery argumenty, które określają: indeks elementu docelowego qubit, tablicę indeksów qubits kontrolki, oś obrotu i indeks skojarzonego parametru w tablicy parametrów definiujących model.</span><span class="sxs-lookup"><span data-stu-id="47ad6-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="47ad6-114">Zobaczmy przykład klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="47ad6-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="47ad6-115">W [przykładzie Half księżyca](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)możemy znaleźć następujący klasyfikator zdefiniowany w pliku `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="47ad6-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

<span data-ttu-id="47ad6-116">To, co definiujemy w tym miejscu, jest funkcja, która zwraca tablicę `ControlledRotation` elementów, która razem z tablicą parametrów i odchylenia będzie definiować nasze [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) .</span><span class="sxs-lookup"><span data-stu-id="47ad6-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="47ad6-117">Ten typ jest fundamentalny w bibliotece Machine Learning Quantum i definiuje klasyfikatora.</span><span class="sxs-lookup"><span data-stu-id="47ad6-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="47ad6-118">Obwód zdefiniowany w funkcji powyżej jest częścią klasyfikatora, w którym każda próbka zestawu danych zawiera dwie funkcje.</span><span class="sxs-lookup"><span data-stu-id="47ad6-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="47ad6-119">W związku z tym potrzebujemy tylko dwóch qubits.</span><span class="sxs-lookup"><span data-stu-id="47ad6-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="47ad6-120">Graficzna reprezentacja obwodu to:</span><span class="sxs-lookup"><span data-stu-id="47ad6-120">The graphical representation of the circuit is:</span></span>

 ![Przykład modelu obwodu](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="47ad6-122">Używanie funkcji biblioteki do zapisywania warstw bram</span><span class="sxs-lookup"><span data-stu-id="47ad6-122">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="47ad6-123">Załóżmy, że mamy zestaw danych o 784 funkcjach na wystąpienie, np. obrazy 28 × 28 pikseli, takie jak zestaw danych MNIST ręcznie.</span><span class="sxs-lookup"><span data-stu-id="47ad6-123">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="47ad6-124">W takim przypadku szerokość obwodu jest wystarczająco duża, aby można było pisać każdą bramę indywidualnie, ale niepraktyczne zadanie.</span><span class="sxs-lookup"><span data-stu-id="47ad6-124">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="47ad6-125">Dlatego Biblioteka Quantum Machine Learning udostępnia zestaw narzędzi do automatycznego generowania warstw z parametrami.</span><span class="sxs-lookup"><span data-stu-id="47ad6-125">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="47ad6-126">Na przykład funkcja [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) zwraca tablicę niekontrolowanych rotacji qubit na daną oś, z jednym obrotem dla każdego qubit w rejestrze, z których każdy jest określany przez inny parametr modelu.</span><span class="sxs-lookup"><span data-stu-id="47ad6-126">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="47ad6-127">Na przykład `LocalRotationsLayer(4, X)` zwraca następujący zestaw bram:</span><span class="sxs-lookup"><span data-stu-id="47ad6-127">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Warstwa obrotów lokalnych](~/media/local_rotations_layer.PNG)

<span data-ttu-id="47ad6-129">Zalecamy zapoznanie się z [biblioteką interfejsów API Machine Learning Quantum](xref:microsoft.quantum.machinelearning) , aby poznać wszystkie narzędzia dostępne do usprawnienia projektowania obwodu.</span><span class="sxs-lookup"><span data-stu-id="47ad6-129">We recommend you explore the [API reference of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="47ad6-130">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="47ad6-130">Next steps</span></span>

 <span data-ttu-id="47ad6-131">Wypróbuj różne struktury w przykładach dostarczonych przez przykłady.</span><span class="sxs-lookup"><span data-stu-id="47ad6-131">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="47ad6-132">Czy widzisz zmiany w wydajności modelu?</span><span class="sxs-lookup"><span data-stu-id="47ad6-132">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="47ad6-133">W następnym samouczku [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) dowiesz się, jak ładować zestawy danych, aby próbować i eksplorować nowe architektury klasyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="47ad6-133">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
