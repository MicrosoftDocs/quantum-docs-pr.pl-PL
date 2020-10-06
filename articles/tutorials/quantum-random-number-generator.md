---
title: Tworzenie kwantowego generatora liczb losowych
description: Utwórz Q# projekt, który pokazuje podstawowe koncepcje Quantum, takie jak Podpozycja, tworząc generator liczb losowych Quantum.
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: cefe35a10dd89c14d2f1abc3080d52ab125236d1
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771283"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="b4e1e-103">Samouczek: implementowanie kwantowego generatora liczb losowych w języku Q\#</span><span class="sxs-lookup"><span data-stu-id="b4e1e-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="b4e1e-104">Prosty przykład algorytmu Quantum zapisany w Q# jest generatorem liczb losowych Quantum.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="b4e1e-105">Ten algorytm wykorzystuje zjawiska mechaniki kwantowej, aby utworzyć liczbę losową.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b4e1e-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b4e1e-106">Prerequisites</span></span>

- <span data-ttu-id="b4e1e-107">Zestaw Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b4e1e-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="b4e1e-108">Utwórz Q# projekt dla [ Q# aplikacji](xref:microsoft.quantum.install.standalone), za pomocą [programu hosta Python](xref:microsoft.quantum.install.python)lub [programu hosta języka C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="b4e1e-108">Create a Q# project for either a [Q# application](xref:microsoft.quantum.install.standalone), with a [Python host program](xref:microsoft.quantum.install.python), or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-no-locq-operation"></a><span data-ttu-id="b4e1e-109">Napisz Q# operację</span><span class="sxs-lookup"><span data-stu-id="b4e1e-109">Write a Q# operation</span></span>

### <a name="no-locq-operation-code"></a><span data-ttu-id="b4e1e-110">Q# kod operacji</span><span class="sxs-lookup"><span data-stu-id="b4e1e-110">Q# operation code</span></span>

1. <span data-ttu-id="b4e1e-111">Zastąp zawartość pliku Program.qs następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="b4e1e-112">Jak wspomniano w artykule [Informacje na temat obliczeń kwantowych](xref:microsoft.quantum.overview.understanding), kubit jest jednostką informacji kwantowych, która może być w superpozycji.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="b4e1e-113">Przy pomiarze kubit może mieć tylko wartość 0 lub 1.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="b4e1e-114">Jednak przed pomiarem stan qubit reprezentuje prawdopodobieństwo odczytu 0 lub 1 z pomiarem.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-114">However, before measurement, the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="b4e1e-115">Ten stan probabilistyczny jest nazywany superpozycją.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="b4e1e-116">Przy użyciu tego prawdopodobieństwa można generować liczby losowe.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="b4e1e-117">W naszej Q# operacji wprowadzamy `Qubit` Typ danych, natywny dla Q# .</span><span class="sxs-lookup"><span data-stu-id="b4e1e-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="b4e1e-118">Element `Qubit` można przydzielić tylko za pomocą instrukcji `using`.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="b4e1e-119">Po przydzieleniu kubit jest zawsze w stanie `Zero`.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="b4e1e-120">Za pomocą operacji `H` można wprowadzić element `Qubit` w stan superpozycji.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="b4e1e-121">Aby zmierzyć kubit i odczytać jego wartość, użyj operacji wewnętrznej `M`.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="b4e1e-122">Gdy wprowadzimy element `Qubit` w stan superpozycji i wykonamy na nim pomiar, wartość wyniku będzie inna przy każdym wywołaniu kodu.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="b4e1e-123">Po cofnięciu przydziału elementu `Qubit` należy z powrotem jawnie ustawić dla niego stan `Zero` — w przeciwnym razie symulator zgłosi błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="b4e1e-124">Można to łatwo zrobić, wywołując funkcję `Reset`.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="b4e1e-125">Wizualizowanie kodu za pomocą sfery Blocha</span><span class="sxs-lookup"><span data-stu-id="b4e1e-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="b4e1e-126">Na sferze Blocha biegun północny reprezentuje wartość klasyczną **0**, a biegun południowy reprezentuje wartość klasyczną **1**.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="b4e1e-127">Każdą superpozycję można przedstawić jako punkt na sferze (reprezentowany przez strzałkę).</span><span class="sxs-lookup"><span data-stu-id="b4e1e-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="b4e1e-128">Im bliżej od końca strzałki do bieguna, tym większe jest prawdopodobieństwo, że przy pomiarze kubit ulegnie kolapsowi do wartości klasycznej przypisanej do tego bieguna.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="b4e1e-129">Na przykład stan kubitu reprezentowany przez czerwoną strzałkę poniżej ma większe prawdopodobieństwo zwrócenia wartości **0** przy pomiarze.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="b4e1e-130">Ta reprezentacja może posłużyć do wizualizacji działania kodu:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="b4e1e-131">Zaczniemy od kubitu zainicjowanego w stanie **0** i zastosujemy funkcję `H`, aby utworzyć superpozycję, w której prawdopodobieństwa wartości **0** i **1** są jednakowe.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="b4e1e-132">Następnie zmierzymy kubit i zapiszemy dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="b4e1e-133">Ponieważ wynik pomiaru jest całkowicie losowy, uzyskaliśmy losowy bit.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="b4e1e-134">Możemy wywołać tę operację kilka razy, aby utworzyć liczby całkowite.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="b4e1e-135">Jeśli na przykład wywołamy operację trzykrotnie w celu uzyskania trzech losowych bitów, możemy utworzyć losowe liczby 3-bitowe (czyli liczbę losową z zakresu od 0 do 7).</span><span class="sxs-lookup"><span data-stu-id="b4e1e-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="b4e1e-136">Tworzenie kompletnego generatora liczb losowych</span><span class="sxs-lookup"><span data-stu-id="b4e1e-136">Creating a complete random number generator</span></span>

<span data-ttu-id="b4e1e-137">Teraz, gdy mamy Q# operację generującą bity losowe, możemy użyć jej do utworzenia kompletnego generatora liczb losowych Quantum.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="b4e1e-138">Możemy użyć Q# aplikacji lub użyć programu hosta.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-138">We can use a Q# application or use a host program.</span></span>



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="b4e1e-139">Q# aplikacje z programem Visual Studio lub Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b4e1e-139">Q# applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="b4e1e-140">Aby utworzyć pełną Q# aplikację, Dodaj następujący punkt wejścia do Q# programu:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-140">To create the full Q# application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="b4e1e-141">Program uruchomi operację lub funkcję oznaczoną `@EntryPoint()` atrybutem na symulatorze lub szacowania zasobów, w zależności od konfiguracji projektu i opcji wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-141">The program will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="b4e1e-142">W programie Visual Studio po prostu naciśnij kombinację klawiszy CTRL + F5, aby uruchomić skrypt.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-142">In Visual Studio, simply press Ctrl + F5 to run the script.</span></span>

<span data-ttu-id="b4e1e-143">W programie VS Code za pierwszym razem skompiluj plik Program.qs, wpisując w terminalu następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="b4e1e-144">Przy kolejnych uruchomieniach nie musisz ponownie kompilować pliku.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="b4e1e-145">Aby go uruchomić, wprowadź następujące polecenie i naciśnij klawisz Enter:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[<span data-ttu-id="b4e1e-146">Python z Visual Studio Code lub wiersz polecenia</span><span class="sxs-lookup"><span data-stu-id="b4e1e-146">Python with Visual Studio Code or the command prompt</span></span>](#tab/tabid-python)

<span data-ttu-id="b4e1e-147">Aby uruchomić nowy Q# program z języka Python, Zapisz następujący kod jako `host.py` :</span><span class="sxs-lookup"><span data-stu-id="b4e1e-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="b4e1e-148">Następnie można uruchomić program hosta języka Python z poziomu wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-148">You can then run your Python host program from the command prompt:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="b4e1e-149">Język C# w programie Visual Studio Code lub Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b4e1e-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b4e1e-150">Aby uruchomić nowy Q# program w języku c#, zmodyfikuj, `Driver.cs` aby zawierał następujący kod w języku c#:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="b4e1e-151">Następnie można uruchomić program hosta C# z wiersza polecenia (w programie Visual Studio należy nacisnąć klawisz F5):</span><span class="sxs-lookup"><span data-stu-id="b4e1e-151">You can then run your C# host program from the command prompt (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
