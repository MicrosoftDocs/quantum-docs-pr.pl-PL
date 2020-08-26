---
title: Eksploruj Entanglement z Q#
description: Dowiedz się, jak napisać program Quantum w Q# . Opracowywanie aplikacji stanu Bella za pomocą zestawu QDK (Quantum Development Kit)
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: d815a9a25b8ba5e9489b6d3d27fb0d64ab4aaa1d
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863440"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="708e6-104">Samouczek: Eksplorowanie splątania przy użyciu języka Q\#</span><span class="sxs-lookup"><span data-stu-id="708e6-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="708e6-105">W tym samouczku pokazano, jak napisać Q# program, który manipuluje i mierzy qubits i pokazuje efekty nakładania się i Entanglement.</span><span class="sxs-lookup"><span data-stu-id="708e6-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="708e6-106">Napiszesz aplikację o nazwie Bell, aby zademonstrować splątanie kwantowe.</span><span class="sxs-lookup"><span data-stu-id="708e6-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="708e6-107">Nazwisko Bell odnosi się do stanów Bella — specyficznych stanów kwantowych dwóch kubitów, które są używane do reprezentowania najprostszych przykładów superpozycji i splątania kwantowego.</span><span class="sxs-lookup"><span data-stu-id="708e6-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="708e6-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="708e6-108">Pre-requisites</span></span>

<span data-ttu-id="708e6-109">Gdy wszystko będzie gotowe do rozpoczęcia kodowania, wykonaj następujące kroki przed kontynuowaniem:</span><span class="sxs-lookup"><span data-stu-id="708e6-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="708e6-110">[Zainstaluj](xref:microsoft.quantum.install) zestaw Quantum Development Kit przy użyciu preferowanego języka i środowiska programistycznego.</span><span class="sxs-lookup"><span data-stu-id="708e6-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="708e6-111">Jeśli masz już zainstalowany zestaw QDK, upewnij się, że [zaktualizowano](xref:microsoft.quantum.update) go do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="708e6-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="708e6-112">Możesz również wykonać czynności opisane w opisie, nie instalując QDK, przeglądając omówienia Q# języka programowania i pierwsze koncepcje przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="708e6-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="708e6-113">Z tego samouczka dowiesz się, jak wykonywać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="708e6-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="708e6-114">Tworzenie i łączenie operacji w p\#</span><span class="sxs-lookup"><span data-stu-id="708e6-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="708e6-115">Twórz operacje w celu umieszczenia qubits w położeniu, entangle i mierzenia ich.</span><span class="sxs-lookup"><span data-stu-id="708e6-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="708e6-116">Zademonstrowanie Entanglement Quantum przy użyciu Q# programu uruchamianego w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="708e6-116">Demonstrate quantum entanglement with a Q# program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="708e6-117">Prezentowanie zachowania qubit z QDK</span><span class="sxs-lookup"><span data-stu-id="708e6-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="708e6-118">Bity klasyczne przechowują jedną wartość binarną, taką jak 0 lub 1, natomiast [kubit](xref:microsoft.quantum.glossary#qubit) może być w stanie **superpozycji** wartości 0 i 1.</span><span class="sxs-lookup"><span data-stu-id="708e6-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="708e6-119">Koncepcyjnie, stan qubit można traktować jako kierunek w przestrzeni abstrakcyjnej (znanej również jako wektor).</span><span class="sxs-lookup"><span data-stu-id="708e6-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="708e6-120">Stan qubit może być w dowolnym z możliwych instrukcji.</span><span class="sxs-lookup"><span data-stu-id="708e6-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="708e6-121">Dwa **stany klasyczne** są dwoma określonymi kierunkami — reprezentującymi stuprocentową szansę zmierzenia wartości 0 i stuprocentową szansę zmierzenia wartości 1.</span><span class="sxs-lookup"><span data-stu-id="708e6-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="708e6-122">Pomiar pozwala uzyskać wynik binarny i zmienia stan kubitu.</span><span class="sxs-lookup"><span data-stu-id="708e6-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="708e6-123">Pomiar tworzy wartość binarną, 0 lub 1.</span><span class="sxs-lookup"><span data-stu-id="708e6-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="708e6-124">Kubit przechodzi z superpozycji (dowolny kierunek) do jednego ze stanów klasycznych.</span><span class="sxs-lookup"><span data-stu-id="708e6-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="708e6-125">Następne powtórzenia tego samego pomiaru bez wykonywania żadnych pośrednich interwencji dają taki sam wynik binarny.</span><span class="sxs-lookup"><span data-stu-id="708e6-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="708e6-126">Wiele kubitów może być [**splątanych**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="708e6-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="708e6-127">Gdy mierzymy jeden ze splątanych kubitów, powoduje to również aktualizację naszej wiedzy o stanie pozostałych kubitów.</span><span class="sxs-lookup"><span data-stu-id="708e6-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="708e6-128">Teraz jesteśmy gotowi do zademonstrowania Q# tego zachowania.</span><span class="sxs-lookup"><span data-stu-id="708e6-128">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="708e6-129">Rozpoczniesz od najprostszego możliwego programu i rozbudujesz go w celu zademonstrowania zjawisk superpozycji kwantowej i splątania kwantowego.</span><span class="sxs-lookup"><span data-stu-id="708e6-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="708e6-130">Tworzenie Q# projektu</span><span class="sxs-lookup"><span data-stu-id="708e6-130">Creating a Q# project</span></span>

<span data-ttu-id="708e6-131">Pierwszą czynnością, którą należy wykonać, jest utworzenie nowego Q# projektu.</span><span class="sxs-lookup"><span data-stu-id="708e6-131">The first thing we have to do is to create a new Q# project.</span></span> <span data-ttu-id="708e6-132">W tym samouczku zamierzamy używać środowiska na podstawie [ Q# aplikacji z vs Code](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="708e6-132">In this tutorial we are going to use the environment based on [Q# applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="708e6-133">Aby utworzyć nowy projekt, w VS Code:</span><span class="sxs-lookup"><span data-stu-id="708e6-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="708e6-134">Kliknij pozycję **View** -> **Command Palette** (Widok -> Paleta poleceń), a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).</span><span class="sxs-lookup"><span data-stu-id="708e6-134">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="708e6-135">Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).</span><span class="sxs-lookup"><span data-stu-id="708e6-135">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="708e6-136">Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Create project** (Utwórz projekt).</span><span class="sxs-lookup"><span data-stu-id="708e6-136">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="708e6-137">Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="708e6-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="708e6-138">W takim przypadku nazywamy projektem `Bell` .</span><span class="sxs-lookup"><span data-stu-id="708e6-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="708e6-139">Spowoduje to wygenerowanie dwóch plików: `Bell.csproj` , pliku projektu i `Program.qs` szablonu Q# aplikacji, która zostanie użyta do zapisania naszej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="708e6-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a Q# application that we will use to write our application.</span></span> <span data-ttu-id="708e6-140">Zawartość `Program.qs` powinna być:</span><span class="sxs-lookup"><span data-stu-id="708e6-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="708e6-141">Napisz aplikację Q \#</span><span class="sxs-lookup"><span data-stu-id="708e6-141">Write the Q\# application</span></span>
 
<span data-ttu-id="708e6-142">Naszym celem jest przygotowanie dwóch qubits w konkretnym stanie Quantum, pokazując, jak pracować na qubits z programem w Q# celu zmiany ich stanu i zademonstrować efekty nakładania się i Entanglement.</span><span class="sxs-lookup"><span data-stu-id="708e6-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="708e6-143">Utworzymy ten element, aby wprowadzić qubit Stany, operacje i pomiary.</span><span class="sxs-lookup"><span data-stu-id="708e6-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="708e6-144">Inicjowanie qubit przy użyciu miary</span><span class="sxs-lookup"><span data-stu-id="708e6-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="708e6-145">W pierwszym poniższym kodzie pokazano, jak korzystać z qubits w programie Q# .</span><span class="sxs-lookup"><span data-stu-id="708e6-145">In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="708e6-146">Wprowadzimy dwie operacje [`M`](xref:microsoft.quantum.intrinsic.m) i [`X`](xref:microsoft.quantum.intrinsic.x) przekształciją stan qubit.</span><span class="sxs-lookup"><span data-stu-id="708e6-146">We’ll introduce two operations, [`M`](xref:microsoft.quantum.intrinsic.m) and [`X`](xref:microsoft.quantum.intrinsic.x) that transform the state of a qubit.</span></span> <span data-ttu-id="708e6-147">W tym fragmencie kodu jest definiowana operacja `SetQubitState`, która przyjmuje parametr w postaci kubitu i kolejny parametr `desired`, reprezentujący stan, w który należy wprowadzić kubit.</span><span class="sxs-lookup"><span data-stu-id="708e6-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="708e6-148">Operacja `SetQubitState` wykonuje pomiar kubitu za pomocą operacji `M`.</span><span class="sxs-lookup"><span data-stu-id="708e6-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="708e6-149">W programie Q# pomiar qubit zawsze zwraca albo `Zero` `One` .</span><span class="sxs-lookup"><span data-stu-id="708e6-149">In Q#, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="708e6-150">Jeśli pomiar zwraca wartość, która nie jest równa żądanej wartości, `SetQubitState` "Przerzuć" qubit, czyli wykonuje `X` operację, która zmienia stan qubit na nowy stan, w którym prawdopodobieństwa zwracająca `Zero` wynik pomiaru i `One` jest odwrócona.</span><span class="sxs-lookup"><span data-stu-id="708e6-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="708e6-151">W ten sposób `SetQubitState` zawsze umieszcza docelowy qubit w żądanym stanie.</span><span class="sxs-lookup"><span data-stu-id="708e6-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="708e6-152">Zastąp zawartość `Program.qs` następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="708e6-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="708e6-153">Można teraz wywołać tę operację, aby ustawić dla kubitu stan klasyczny, powodujący zwracanie wartości `Zero` przez 100% czasu lub zwracanie wartości `One` przez 100% czasu.</span><span class="sxs-lookup"><span data-stu-id="708e6-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="708e6-154">Wartości `Zero` i `One` są stałymi, które reprezentują dwa możliwe wyniki pomiaru kubitu.</span><span class="sxs-lookup"><span data-stu-id="708e6-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="708e6-155">Operacja `SetQubitState` mierzy kubit.</span><span class="sxs-lookup"><span data-stu-id="708e6-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="708e6-156">Jeśli kubit jest w żądanym stanie, operacja `SetQubitState` pozostawia go bez zmian; w przeciwnym razie zmieniamy stan kubitu na żądany, wykonując operację `X`.</span><span class="sxs-lookup"><span data-stu-id="708e6-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="708e6-157">Informacje o Q# operacjach</span><span class="sxs-lookup"><span data-stu-id="708e6-157">About Q# operations</span></span>

<span data-ttu-id="708e6-158">Q#Operacja jest podprocedurą Quantum.</span><span class="sxs-lookup"><span data-stu-id="708e6-158">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="708e6-159">Oznacza to, że jest to wywoływana procedura, która zawiera wywołania innych operacji Quantum.</span><span class="sxs-lookup"><span data-stu-id="708e6-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="708e6-160">Argumenty operacji są przekazywane za pomocą krotki (w nawiasach).</span><span class="sxs-lookup"><span data-stu-id="708e6-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="708e6-161">Zwracany typ operacji jest określony po dwukropku.</span><span class="sxs-lookup"><span data-stu-id="708e6-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="708e6-162">W tym przypadku operacja `SetQubitState` nie zwraca wartości, więc jest oznaczona jako zwracająca wartość `Unit`.</span><span class="sxs-lookup"><span data-stu-id="708e6-162">In this case, the `SetQubitState` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="708e6-163">Jest to Q# odpowiednik w języku `unit` F #, który jest w przybliżeniu analogiczny do `void` języka C#, i pustej krotki ( `Tuple[()]` ) w Python.</span><span class="sxs-lookup"><span data-stu-id="708e6-163">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="708e6-164">W pierwszej operacji użyto dwóch operacji Quantum Q# :</span><span class="sxs-lookup"><span data-stu-id="708e6-164">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="708e6-165">[`M`](xref:microsoft.quantum.intrinsic.m)Operacja, która mierzy stan qubit</span><span class="sxs-lookup"><span data-stu-id="708e6-165">The [`M`](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="708e6-166">[`X`](xref:microsoft.quantum.intrinsic.x)Operacja, która przerzuca stan qubit</span><span class="sxs-lookup"><span data-stu-id="708e6-166">The [`X`](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="708e6-167">Operacja kwantowa przekształca stan kubitu.</span><span class="sxs-lookup"><span data-stu-id="708e6-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="708e6-168">Czasami mówi się o bramkach kwantowych zamiast operacji, analogicznie do klasycznych bramek logicznych.</span><span class="sxs-lookup"><span data-stu-id="708e6-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="708e6-169">Bierze się to z wczesnej epoki obliczeń kwantowych, gdy algorytmy stanowiły tylko konstrukcje teoretyczne i były wizualizowane jako diagramy, podobnie do diagramów obwodów w obliczeniach klasycznych.</span><span class="sxs-lookup"><span data-stu-id="708e6-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="708e6-170">Obliczanie wyników pomiaru</span><span class="sxs-lookup"><span data-stu-id="708e6-170">Counting measurement outcomes</span></span>

<span data-ttu-id="708e6-171">Aby zademonstrować efekt operacji `SetQubitState`, dodawana jest następnie operacja `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="708e6-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="708e6-172">Ta operacja przyjmuje jako dane wejściowe wartość `Zero` lub `One` i wywołuje operację `SetQubitState` pewną liczbę razy z tymi danymi wejściowymi, a także oblicza, ile razy została zwrócona wartość `Zero` z pomiaru kubitu i ile razy została zwrócona wartość `One`.</span><span class="sxs-lookup"><span data-stu-id="708e6-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="708e6-173">Oczywiście w tej pierwszej symulacji operacji `TestBellState` oczekujemy, że dane wyjściowe będą wskazywać, iż wszystkie pomiary kubitu z ustawionym parametrem wejściowym `Zero` będą zwracać wartość `Zero`, a wszystkie pomiary kubitu z ustawionym parametrem wejściowym `One` będą zwracać wartość `One`.</span><span class="sxs-lookup"><span data-stu-id="708e6-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="708e6-174">Dodatkowo dodamy kod do `TestBellState` przedstawienia do przedłożenia i Entanglement.</span><span class="sxs-lookup"><span data-stu-id="708e6-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="708e6-175">Dodaj następującą operację do pliku `Program.qs` wewnątrz przestrzeni nazw po operacji `SetQubitState`:</span><span class="sxs-lookup"><span data-stu-id="708e6-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="708e6-176">Należy pamiętać, że dodaliśmy wiersz przed przystąpieniem `return` do drukowania komunikatu wyjaśniającego w konsoli programu za pomocą funkcji ( `Message` ) [Microsoft. Quantum. wewnętrzna. Message]</span><span class="sxs-lookup"><span data-stu-id="708e6-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="708e6-177">Ta operacja (`TestBellState`) wykona `count` iteracji pętli, ustawi określoną wartość `initial` dla kubitu, a następnie zmierzy (`M`) wynik.</span><span class="sxs-lookup"><span data-stu-id="708e6-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="708e6-178">Zbierze ona dane statystyczne dotyczące zmierzonej liczby zer i jedynek oraz zwróci je do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="708e6-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="708e6-179">Wykona także jedną inną wymaganą operację.</span><span class="sxs-lookup"><span data-stu-id="708e6-179">It performs one other necessary operation.</span></span> <span data-ttu-id="708e6-180">Zresetuje kubit do znanego stanu (`Zero`) przed jego zwróceniem, co umożliwi innym przydzielenie tego kubitu w znanym stanie.</span><span class="sxs-lookup"><span data-stu-id="708e6-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="708e6-181">Jest to wymagane przez instrukcję `using`.</span><span class="sxs-lookup"><span data-stu-id="708e6-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="708e6-182">Informacje o zmiennych w Q\#</span><span class="sxs-lookup"><span data-stu-id="708e6-182">About variables in Q\#</span></span>

<span data-ttu-id="708e6-183">Domyślnie zmienne w Q# są niezmienne; ich wartości nie można zmienić po ich powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="708e6-183">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="708e6-184">Słowo kluczowe `let` jest używane do wskazania powiązania zmiennej niezmienialnej.</span><span class="sxs-lookup"><span data-stu-id="708e6-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="708e6-185">Argumenty operacji są zawsze niezmienialne.</span><span class="sxs-lookup"><span data-stu-id="708e6-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="708e6-186">Jeśli potrzebujesz zmiennej, której wartość można zmienić, takiej jak `numOnes` w przykładzie, możesz zadeklarować zmienną za pomocą słowa kluczowego `mutable`.</span><span class="sxs-lookup"><span data-stu-id="708e6-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="708e6-187">Wartość zmiennej modyfikowalnej zmienia się przy użyciu instrukcji `setQubitState`.</span><span class="sxs-lookup"><span data-stu-id="708e6-187">A mutable variable's value may be changed using a `setQubitState` statement.</span></span>

<span data-ttu-id="708e6-188">W obu przypadkach typ zmiennej jest wnioskowany przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="708e6-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="708e6-189">Q# nie wymaga żadnych adnotacji typu dla zmiennych.</span><span class="sxs-lookup"><span data-stu-id="708e6-189">Q# doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="708e6-190">`using`Instrukcje w temacie Q\#</span><span class="sxs-lookup"><span data-stu-id="708e6-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="708e6-191">`using`Instrukcja jest również specjalna dla Q# .</span><span class="sxs-lookup"><span data-stu-id="708e6-191">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="708e6-192">Służy do przydzielania kubitów do użycia w bloku kodu.</span><span class="sxs-lookup"><span data-stu-id="708e6-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="708e6-193">W programie Q# wszystkie qubits są przydzielane i wydawane, a nie stałymi zasobami w całym okresie istnienia złożonego algorytmu.</span><span class="sxs-lookup"><span data-stu-id="708e6-193">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="708e6-194">Instrukcja `using` przydziela zestaw kubitów na początku bloku i zwalnia te kubity na jego końcu.</span><span class="sxs-lookup"><span data-stu-id="708e6-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="708e6-195">Uruchamianie kodu z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="708e6-195">Run the code from the command prompt</span></span>

<span data-ttu-id="708e6-196">Aby uruchomić kod, musimy określić kompilator, *który* jest wywoływany do uruchomienia, gdy zostanie podane `dotnet run` polecenie.</span><span class="sxs-lookup"><span data-stu-id="708e6-196">In order to run the code we need to specify the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="708e6-197">Jest to wykonywane z prostą zmianą w Q# pliku, dodając wiersz `@EntryPoint()` bezpośrednio poprzedzający możliwy do `TestBellState` przeprowadzenia: operację w tym przypadku.</span><span class="sxs-lookup"><span data-stu-id="708e6-197">This is done with a simple change in the Q# file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="708e6-198">Pełny kod powinien:</span><span class="sxs-lookup"><span data-stu-id="708e6-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="708e6-199">Aby uruchomić program, musimy określić `count` argumenty i `initial` z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="708e6-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="708e6-200">Wybierzmy na przykład `count = 1000` i `initial = One` .</span><span class="sxs-lookup"><span data-stu-id="708e6-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="708e6-201">Wprowadź następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="708e6-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="708e6-202">I należy obserwować następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="708e6-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="708e6-203">Jeśli spróbujesz `initial = Zero` :</span><span class="sxs-lookup"><span data-stu-id="708e6-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="708e6-204">Przygotowanie superpozycji</span><span class="sxs-lookup"><span data-stu-id="708e6-204">Prepare superposition</span></span>

<span data-ttu-id="708e6-205">Teraz przyjrzyjmy się sposobom, w jaki Q# wyrażamy, jak można dołączać qubits.</span><span class="sxs-lookup"><span data-stu-id="708e6-205">Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="708e6-206">Przypomnijmy, że kubit może być w stanie superpozycji wartości 0 i 1.</span><span class="sxs-lookup"><span data-stu-id="708e6-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="708e6-207">Użyjemy operacji `Hadamard`, aby go uzyskać.</span><span class="sxs-lookup"><span data-stu-id="708e6-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="708e6-208">Jeśli kubit znajduje się w dowolnym ze stanów klasycznych (gdy pomiar zwraca zawsze wartość `Zero` lub zawsze wartość `One`), operacja `Hadamard` lub `H` wprowadzi kubit w stan, w którym pomiar kubitu będzie zwracać wartość `Zero` przez 50% czasu i zwracać wartość `One` przez 50% czasu.</span><span class="sxs-lookup"><span data-stu-id="708e6-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="708e6-209">Koncepcyjnie kubit można uważać za będący w połowie między wartościami `Zero` i `One`.</span><span class="sxs-lookup"><span data-stu-id="708e6-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="708e6-210">Gdy teraz zasymulujemy operację `TestBellState`, zwracane wyniki będą zawierać w przybliżeniu równą liczbę wartości `Zero` i `One` po pomiarze.</span><span class="sxs-lookup"><span data-stu-id="708e6-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="708e6-211">`X` Przerzucanie stanu qubit</span><span class="sxs-lookup"><span data-stu-id="708e6-211">`X` flips qubit state</span></span>

<span data-ttu-id="708e6-212">Najpierw spróbujemy przerzucić kubit (jeśli kubit jest w stanie `Zero`, przerzucimy go do stanu `One` i na odwrót).</span><span class="sxs-lookup"><span data-stu-id="708e6-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="708e6-213">Wykonuje się to za pomocą operacji `X` przed wykonaniem pomiaru w operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="708e6-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="708e6-214">Teraz wyniki są wycofane:</span><span class="sxs-lookup"><span data-stu-id="708e6-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="708e6-215">Teraz przyjrzyjmy się właściwościom Quantum klasy qubits.</span><span class="sxs-lookup"><span data-stu-id="708e6-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="708e6-216">`H` przygotowuje nałożenie</span><span class="sxs-lookup"><span data-stu-id="708e6-216">`H` prepares superposition</span></span>

<span data-ttu-id="708e6-217">Wszystko, co należy zrobić, to zastąpić operację `X` w poprzednim uruchomieniu operacją Hadamarda `H`.</span><span class="sxs-lookup"><span data-stu-id="708e6-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="708e6-218">Zamiast przerzucać kubit całkowicie z wartości 0 do wartości 1, przerzucimy go tylko w połowie.</span><span class="sxs-lookup"><span data-stu-id="708e6-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="708e6-219">Zastąpione wiersze w operacji `TestBellState` teraz wyglądają następująco:</span><span class="sxs-lookup"><span data-stu-id="708e6-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="708e6-220">Nowe wyniki są bardziej interesujące:</span><span class="sxs-lookup"><span data-stu-id="708e6-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="708e6-221">Przy każdym wykonaniu pomiaru żądamy wartości klasycznej, lecz kubit jest w stanie przejściowym między wartościami 0 i 1, więc otrzymamy (statystycznie) wartość 0 w połowie przypadków i wartość 1 w pozostałych przypadkach.</span><span class="sxs-lookup"><span data-stu-id="708e6-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="708e6-222">Jest to zjawisko **superpozycji**, które daje nam po raz pierwszy wgląd w rzeczywisty stan kwantowy.</span><span class="sxs-lookup"><span data-stu-id="708e6-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="708e6-223">Przygotowanie splątania</span><span class="sxs-lookup"><span data-stu-id="708e6-223">Prepare entanglement</span></span>

<span data-ttu-id="708e6-224">Teraz przyjrzyjmy się sposobom, w jaki Q# wyrażamy możliwości entangle qubits.</span><span class="sxs-lookup"><span data-stu-id="708e6-224">Now let’s look at how Q# expresses ways to entangle qubits.</span></span>
<span data-ttu-id="708e6-225">Najpierw ustawiamy pierwszy kubit w stanie początkowym, a następnie wprowadzamy go w stan superpozycji za pomocą operacji `H`.</span><span class="sxs-lookup"><span data-stu-id="708e6-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="708e6-226">Następnie przed pomiarem pierwszego qubit używamy nowej operacji ( `CNOT` ), która oznacza, że nie jest to kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="708e6-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-NOT.</span></span>  <span data-ttu-id="708e6-227">Wynikiem wykonania tej operacji na dwóch kubitach jest przerzucenie drugiego kubitu, jeśli pierwszy kubit ma wartość `One`.</span><span class="sxs-lookup"><span data-stu-id="708e6-227">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="708e6-228">Teraz oba kubity są splątane.</span><span class="sxs-lookup"><span data-stu-id="708e6-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="708e6-229">Nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości `Zero` i `One` po pomiarze), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu.</span><span class="sxs-lookup"><span data-stu-id="708e6-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="708e6-230">Bramka `CNOT` splątała dwa kubity — cokolwiek dzieje się z jednym z nich, to samo dzieje się z drugim.</span><span class="sxs-lookup"><span data-stu-id="708e6-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="708e6-231">W przypadku odwrócenia pomiarów (drugi kubit przed pierwszym) będzie dziać się to samo.</span><span class="sxs-lookup"><span data-stu-id="708e6-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="708e6-232">Pierwsza miara będzie losowa, a druga zablokowana na wartości pierwszej.</span><span class="sxs-lookup"><span data-stu-id="708e6-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="708e6-233">Najpierw należy przydzielić dwie qubits zamiast jednego w `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="708e6-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="708e6-234">Pozwoli to dodać nową operację (`CNOT`) przed wykonaniem pomiaru (`M`) w operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="708e6-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="708e6-235">Dodaliśmy kolejną operację `SetQubitState`, aby zainicjować pierwszy kubit w celu zapewnienia, że jest zawsze w stanie `Zero` podczas uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="708e6-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="708e6-236">Musimy też zresetować drugi kubit przed jego zwolnieniem.</span><span class="sxs-lookup"><span data-stu-id="708e6-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="708e6-237">Pełna procedura wygląda teraz następująco:</span><span class="sxs-lookup"><span data-stu-id="708e6-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="708e6-238">Jeśli ją uruchomimy, uzyskamy dokładnie taki sam wynik 50%-50% jak poprzednio.</span><span class="sxs-lookup"><span data-stu-id="708e6-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="708e6-239">Jednak teraz interesuje nas, jak drugi kubit reaguje na pomiar pierwszego.</span><span class="sxs-lookup"><span data-stu-id="708e6-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="708e6-240">Dodamy tę statystykę do nowej wersji operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="708e6-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="708e6-241">Nowa wartość zwracana (`agree`) śledzi przypadki, gdy pomiar pierwszego kubitu jest zgodny z pomiarem drugiego kubitu.</span><span class="sxs-lookup"><span data-stu-id="708e6-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="708e6-242">Uruchamianie kodu, który uzyskamy:</span><span class="sxs-lookup"><span data-stu-id="708e6-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="708e6-243">Jak podano w omówieniu, nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości 0 i 1), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu, ponieważ są one splątane!</span><span class="sxs-lookup"><span data-stu-id="708e6-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="708e6-244">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="708e6-244">Next steps</span></span>

<span data-ttu-id="708e6-245">W [poszukiwanym](xref:microsoft.quantum.quickstarts.search) samouczku Grover przedstawiono sposób kompilowania i uruchamiania wyszukiwania Grover, jednego z najpopularniejszych algorytmów przetwarzania Quantum i oferowania przykładowego Q# programu, który może służyć do rozwiązywania rzeczywistych problemów z przetwarzaniem Quantum.</span><span class="sxs-lookup"><span data-stu-id="708e6-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="708e6-246">[Wprowadzenie do zestawu Quantum Development Kit](xref:microsoft.quantum.welcome) zaleca więcej sposobów uczenia się Q# i programowania Quantum.</span><span class="sxs-lookup"><span data-stu-id="708e6-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
