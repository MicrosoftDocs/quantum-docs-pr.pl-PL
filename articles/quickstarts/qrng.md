---
title: Tworzenie kwantowego generatora liczb losowych
description: Utwórz projekt języka Q# demonstrujący podstawowe koncepcje kwantowe, takie jak superpozycja, tworząc kwantowy generator liczb losowych.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: c3039b92c4b3235a397d5cf31280ac2673706e9d
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462836"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="e57c4-103">Szybki start: Implementowanie kwantowego generatora liczb losowych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="e57c4-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="e57c4-104">Prostym przykładem kwantowego algorytmu napisanego w języku Q# jest kwantowy generator liczb losowych.</span><span class="sxs-lookup"><span data-stu-id="e57c4-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="e57c4-105">Ten algorytm wykorzystuje zjawiska mechaniki kwantowej, aby utworzyć liczbę losową.</span><span class="sxs-lookup"><span data-stu-id="e57c4-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e57c4-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="e57c4-106">Prerequisites</span></span>

- <span data-ttu-id="e57c4-107">Zestaw Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="e57c4-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="e57c4-108">Tworzenie projektu języka Q#</span><span class="sxs-lookup"><span data-stu-id="e57c4-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="e57c4-109">Tworzenie operacji w języku Q#</span><span class="sxs-lookup"><span data-stu-id="e57c4-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="e57c4-110">Kod operacji języka Q#</span><span class="sxs-lookup"><span data-stu-id="e57c4-110">Q# operation code</span></span>

1. <span data-ttu-id="e57c4-111">Zastąp zawartość pliku Operation.qs następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="e57c4-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="e57c4-112">Jak wspomniano w artykule [Co to są obliczenia kwantowe?](xref:microsoft.quantum.overview.what), kubit jest jednostką informacji kwantowych, która może być w superpozycji.</span><span class="sxs-lookup"><span data-stu-id="e57c4-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="e57c4-113">Przy pomiarze kubit może mieć tylko wartość 0 lub 1.</span><span class="sxs-lookup"><span data-stu-id="e57c4-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="e57c4-114">Jednak podczas wykonywania stan kubitu reprezentuje prawdopodobieństwo odczytania wartości 0 lub 1 przy pomiarze.</span><span class="sxs-lookup"><span data-stu-id="e57c4-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="e57c4-115">Ten stan probabilistyczny jest nazywany superpozycją.</span><span class="sxs-lookup"><span data-stu-id="e57c4-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="e57c4-116">Przy użyciu tego prawdopodobieństwa można generować liczby losowe.</span><span class="sxs-lookup"><span data-stu-id="e57c4-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="e57c4-117">W naszej operacji języka Q# wprowadzamy typ danych `Qubit` (natywny dla języka Q#).</span><span class="sxs-lookup"><span data-stu-id="e57c4-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="e57c4-118">Element `Qubit` można przydzielić tylko za pomocą instrukcji `using`.</span><span class="sxs-lookup"><span data-stu-id="e57c4-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="e57c4-119">Po przydziale kubit jest zawsze w stanie `Zero`.</span><span class="sxs-lookup"><span data-stu-id="e57c4-119">When it gets allocated a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="e57c4-120">Za pomocą operacji `H` można wprowadzić element `Qubit` w stan superpozycji.</span><span class="sxs-lookup"><span data-stu-id="e57c4-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="e57c4-121">Aby zmierzyć kubit i odczytać jego wartość, użyj operacji wewnętrznej `M`.</span><span class="sxs-lookup"><span data-stu-id="e57c4-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="e57c4-122">Gdy wprowadzimy element `Qubit` w stan superpozycji i wykonamy na nim pomiar, wartość wyniku będzie inna przy każdym wywołaniu kodu.</span><span class="sxs-lookup"><span data-stu-id="e57c4-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="e57c4-123">Po cofnięciu przydziału elementu `Qubit` należy z powrotem jawnie ustawić dla niego stan `Zero` — w przeciwnym razie symulator zgłosi błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="e57c4-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="e57c4-124">Można to łatwo zrobić, wywołując funkcję `Reset`.</span><span class="sxs-lookup"><span data-stu-id="e57c4-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="e57c4-125">Wizualizowanie kodu za pomocą sfery Blocha</span><span class="sxs-lookup"><span data-stu-id="e57c4-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="e57c4-126">Na sferze Blocha biegun północny reprezentuje wartość klasyczną **0**, a biegun południowy reprezentuje wartość klasyczną **1**.</span><span class="sxs-lookup"><span data-stu-id="e57c4-126">In the Bloch sphere the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="e57c4-127">Każdą superpozycję można przedstawić jako punkt na sferze (reprezentowany przez strzałkę).</span><span class="sxs-lookup"><span data-stu-id="e57c4-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="e57c4-128">Im bliżej od końca strzałki do bieguna, tym większe jest prawdopodobieństwo, że przy pomiarze kubit ulegnie kolapsowi do wartości klasycznej przypisanej do tego bieguna.</span><span class="sxs-lookup"><span data-stu-id="e57c4-128">When the closer the end of the arrow to a pole, the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="e57c4-129">Na przykład stan kubitu reprezentowany przez czerwoną strzałkę poniżej ma większe prawdopodobieństwo zwrócenia wartości **0** przy pomiarze.</span><span class="sxs-lookup"><span data-stu-id="e57c4-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="./Bloch.svg" width="175">

<span data-ttu-id="e57c4-130">Ta reprezentacja może posłużyć do wizualizacji działania kodu:</span><span class="sxs-lookup"><span data-stu-id="e57c4-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="e57c4-131">Zaczniemy od kubitu zainicjowanego w stanie **0** i zastosujemy funkcję `H`, aby utworzyć superpozycję, w której prawdopodobieństwa wartości **0** i **1** są jednakowe.</span><span class="sxs-lookup"><span data-stu-id="e57c4-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="./H.svg" width="450">

* <span data-ttu-id="e57c4-132">Następnie zmierzymy kubit i zapiszemy dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="e57c4-132">Then we measure the qubit and save the output:</span></span>

<img src="./Measurement2.svg" width="450">

<span data-ttu-id="e57c4-133">Ponieważ wynik pomiaru jest całkowicie losowy, uzyskaliśmy losowy bit.</span><span class="sxs-lookup"><span data-stu-id="e57c4-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="e57c4-134">Możemy wywołać tę operację kilka razy, aby utworzyć liczby całkowite.</span><span class="sxs-lookup"><span data-stu-id="e57c4-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="e57c4-135">Jeśli na przykład wywołamy operację trzykrotnie w celu uzyskania trzech losowych bitów, możemy utworzyć losowe liczby 3-bitowe (czyli liczbę losową z zakresu od 0 do 7).</span><span class="sxs-lookup"><span data-stu-id="e57c4-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>
