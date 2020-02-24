---
title: Tworzenie kwantowego generatora liczb losowych
description: Utwórz projekt języka Q# demonstrujący podstawowe koncepcje kwantowe, takie jak superpozycja, tworząc kwantowy generator liczb losowych.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: d1ad2c1153814e2fa19a38307b2c668c77eae4e3
ms.sourcegitcommit: b7e205aaa7fa1ca9f0daa163e46154945f4bc965
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2020
ms.locfileid: "77441072"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="05ac3-103">Szybki start: Implementowanie kwantowego generatora liczb losowych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="05ac3-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="05ac3-104">Prostym przykładem kwantowego algorytmu napisanego w języku Q# jest kwantowy generator liczb losowych.</span><span class="sxs-lookup"><span data-stu-id="05ac3-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="05ac3-105">Ten algorytm wykorzystuje zjawiska mechaniki kwantowej, aby utworzyć liczbę losową.</span><span class="sxs-lookup"><span data-stu-id="05ac3-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="05ac3-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="05ac3-106">Prerequisites</span></span>

- <span data-ttu-id="05ac3-107">Zestaw Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="05ac3-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="05ac3-108">Tworzenie projektu języka Q#</span><span class="sxs-lookup"><span data-stu-id="05ac3-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="05ac3-109">Tworzenie operacji w języku Q#</span><span class="sxs-lookup"><span data-stu-id="05ac3-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="05ac3-110">Kod operacji języka Q#</span><span class="sxs-lookup"><span data-stu-id="05ac3-110">Q# operation code</span></span>

1. <span data-ttu-id="05ac3-111">Zastąp zawartość pliku Operation.qs następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="05ac3-111">Replace the contents of the Operation.qs file with the following code:</span></span>

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

<span data-ttu-id="05ac3-112">Jak wspomniano w artykule [Co to są obliczenia kwantowe?](xref:microsoft.quantum.overview.what), kubit jest jednostką informacji kwantowych, która może być w superpozycji.</span><span class="sxs-lookup"><span data-stu-id="05ac3-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="05ac3-113">Przy pomiarze kubit może mieć tylko wartość 0 lub 1.</span><span class="sxs-lookup"><span data-stu-id="05ac3-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="05ac3-114">Jednak podczas wykonywania stan kubitu reprezentuje prawdopodobieństwo odczytania wartości 0 lub 1 przy pomiarze.</span><span class="sxs-lookup"><span data-stu-id="05ac3-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="05ac3-115">Ten stan probabilistyczny jest nazywany superpozycją.</span><span class="sxs-lookup"><span data-stu-id="05ac3-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="05ac3-116">Przy użyciu tego prawdopodobieństwa można generować liczby losowe.</span><span class="sxs-lookup"><span data-stu-id="05ac3-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="05ac3-117">W naszej operacji języka Q# wprowadzamy typ danych `Qubit` (natywny dla języka Q#).</span><span class="sxs-lookup"><span data-stu-id="05ac3-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="05ac3-118">Element `Qubit` można przydzielić tylko za pomocą instrukcji `using`.</span><span class="sxs-lookup"><span data-stu-id="05ac3-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="05ac3-119">Po przydzieleniu kubit jest zawsze w stanie `Zero`.</span><span class="sxs-lookup"><span data-stu-id="05ac3-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="05ac3-120">Za pomocą operacji `H` można wprowadzić element `Qubit` w stan superpozycji.</span><span class="sxs-lookup"><span data-stu-id="05ac3-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="05ac3-121">Aby zmierzyć kubit i odczytać jego wartość, użyj operacji wewnętrznej `M`.</span><span class="sxs-lookup"><span data-stu-id="05ac3-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="05ac3-122">Gdy wprowadzimy element `Qubit` w stan superpozycji i wykonamy na nim pomiar, wartość wyniku będzie inna przy każdym wywołaniu kodu.</span><span class="sxs-lookup"><span data-stu-id="05ac3-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="05ac3-123">Po cofnięciu przydziału elementu `Qubit` należy z powrotem jawnie ustawić dla niego stan `Zero` — w przeciwnym razie symulator zgłosi błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="05ac3-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="05ac3-124">Można to łatwo zrobić, wywołując funkcję `Reset`.</span><span class="sxs-lookup"><span data-stu-id="05ac3-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="05ac3-125">Wizualizowanie kodu za pomocą sfery Blocha</span><span class="sxs-lookup"><span data-stu-id="05ac3-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="05ac3-126">Na sferze Blocha biegun północny reprezentuje wartość klasyczną **0**, a biegun południowy reprezentuje wartość klasyczną **1**.</span><span class="sxs-lookup"><span data-stu-id="05ac3-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="05ac3-127">Każdą superpozycję można przedstawić jako punkt na sferze (reprezentowany przez strzałkę).</span><span class="sxs-lookup"><span data-stu-id="05ac3-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="05ac3-128">Im bliżej od końca strzałki do bieguna, tym większe jest prawdopodobieństwo, że przy pomiarze kubit ulegnie kolapsowi do wartości klasycznej przypisanej do tego bieguna.</span><span class="sxs-lookup"><span data-stu-id="05ac3-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="05ac3-129">Na przykład stan kubitu reprezentowany przez czerwoną strzałkę poniżej ma większe prawdopodobieństwo zwrócenia wartości **0** przy pomiarze.</span><span class="sxs-lookup"><span data-stu-id="05ac3-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175">

<span data-ttu-id="05ac3-130">Ta reprezentacja może posłużyć do wizualizacji działania kodu:</span><span class="sxs-lookup"><span data-stu-id="05ac3-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="05ac3-131">Zaczniemy od kubitu zainicjowanego w stanie **0** i zastosujemy funkcję `H`, aby utworzyć superpozycję, w której prawdopodobieństwa wartości **0** i **1** są jednakowe.</span><span class="sxs-lookup"><span data-stu-id="05ac3-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450">

* <span data-ttu-id="05ac3-132">Następnie zmierzymy kubit i zapiszemy dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="05ac3-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450">

<span data-ttu-id="05ac3-133">Ponieważ wynik pomiaru jest całkowicie losowy, uzyskaliśmy losowy bit.</span><span class="sxs-lookup"><span data-stu-id="05ac3-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="05ac3-134">Możemy wywołać tę operację kilka razy, aby utworzyć liczby całkowite.</span><span class="sxs-lookup"><span data-stu-id="05ac3-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="05ac3-135">Jeśli na przykład wywołamy operację trzykrotnie w celu uzyskania trzech losowych bitów, możemy utworzyć losowe liczby 3-bitowe (czyli liczbę losową z zakresu od 0 do 7).</span><span class="sxs-lookup"><span data-stu-id="05ac3-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a><span data-ttu-id="05ac3-136">Tworzenie kompletnego generatora liczb losowych przy użyciu programu hosta</span><span class="sxs-lookup"><span data-stu-id="05ac3-136">Creating a complete random number generator using a host program</span></span>

<span data-ttu-id="05ac3-137">Teraz, gdy mamy operację Q#, która generuje losowe bity, możemy jej użyć do utworzenia kompletnego kwantowego generatora liczb losowych przy użyciu programu hosta.</span><span class="sxs-lookup"><span data-stu-id="05ac3-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator with a host program.</span></span>

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="05ac3-138">Język Python z programem Visual Studio Code lub wierszem polecenia</span><span class="sxs-lookup"><span data-stu-id="05ac3-138">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)
 
 <span data-ttu-id="05ac3-139">Aby uruchomić nowy program języka Q# z poziomu środowiska Python, zapisz następujący kod jako `host.py`:</span><span class="sxs-lookup"><span data-stu-id="05ac3-139">To run your new Q# program from Python, save the following code as `host.py`:</span></span>
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 <span data-ttu-id="05ac3-140">Następnie możesz uruchomić program hosta języka Python z poziomu wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="05ac3-140">You can then run your Python host program from the command line:</span></span>
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="05ac3-141">Język C# z programem Visual Studio Code lub wierszem polecenia</span><span class="sxs-lookup"><span data-stu-id="05ac3-141">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)
 
 <span data-ttu-id="05ac3-142">Aby uruchomić nowy program języka Q# z poziomu środowiska C#, zmodyfikuj element `Driver.cs` tak, aby zawierał następujący kod języka C#:</span><span class="sxs-lookup"><span data-stu-id="05ac3-142">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 <span data-ttu-id="05ac3-143">Następnie możesz uruchomić program hosta języka C# z poziomu wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="05ac3-143">You can then run your C# host program from the command line:</span></span>
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="05ac3-144">Język C# w programie Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="05ac3-144">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

 <span data-ttu-id="05ac3-145">Aby uruchomić nowy program języka Q# z poziomu środowiska C# w programie Visual Studio, zmodyfikuj element `Driver.cs` tak, aby zawierał następujący kod języka C#:</span><span class="sxs-lookup"><span data-stu-id="05ac3-145">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 <span data-ttu-id="05ac3-146">Następnie naciśnij klawisz F5. Program zacznie działać i pojawi się nowe okno z wygenerowaną liczbą losową:</span><span class="sxs-lookup"><span data-stu-id="05ac3-146">Then press F5, the program will start execution and a new window will pop up with the random number generated:</span></span> 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
