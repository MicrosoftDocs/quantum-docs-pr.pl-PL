---
title: Eksplorowanie splątania przy użyciu języka Q#
description: Dowiedz się, jak napisać program kwantowy w języku Q#. Opracowywanie aplikacji stanu Bella za pomocą zestawu QDK (Quantum Development Kit)
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 16c93b3dd17363c06602529cb34e8fc84aadc7a8
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415426"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="5c317-104">Samouczek: Eksplorowanie splątania przy użyciu języka Q\#</span><span class="sxs-lookup"><span data-stu-id="5c317-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="5c317-105">W tym samouczku pokazano, jak napisać program języka Q#, który manipuluje kubitami, mierzy je oraz przedstawia efekty superpozycji i splątania.</span><span class="sxs-lookup"><span data-stu-id="5c317-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="5c317-106">Napiszesz aplikację o nazwie Bell, aby zademonstrować splątanie kwantowe.</span><span class="sxs-lookup"><span data-stu-id="5c317-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="5c317-107">Nazwisko Bell odnosi się do stanów Bella — specyficznych stanów kwantowych dwóch kubitów, które są używane do reprezentowania najprostszych przykładów superpozycji i splątania kwantowego.</span><span class="sxs-lookup"><span data-stu-id="5c317-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="5c317-108">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="5c317-108">Pre-requisites</span></span>

<span data-ttu-id="5c317-109">Gdy wszystko będzie gotowe do rozpoczęcia kodowania, wykonaj następujące kroki przed kontynuowaniem:</span><span class="sxs-lookup"><span data-stu-id="5c317-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="5c317-110">[Zainstaluj](xref:microsoft.quantum.install) zestaw Quantum Development Kit przy użyciu preferowanego języka i środowiska programistycznego.</span><span class="sxs-lookup"><span data-stu-id="5c317-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="5c317-111">Jeśli masz już zainstalowany zestaw QDK, upewnij się, że [zaktualizowano](xref:microsoft.quantum.update) go do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="5c317-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="5c317-112">Możesz również wykonać czynności opisane w opisie, nie instalując QDK, przeglądając omówienia języka programowania Q # i pierwsze koncepcje przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="5c317-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="5c317-113">Z tego samouczka dowiesz się, jak wykonywać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="5c317-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5c317-114">Tworzenie i łączenie operacji w p\#</span><span class="sxs-lookup"><span data-stu-id="5c317-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="5c317-115">Twórz operacje w celu umieszczenia qubits w położeniu, entangle i mierzenia ich.</span><span class="sxs-lookup"><span data-stu-id="5c317-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="5c317-116">Zademonstrowanie Entanglement Quantum przy użyciu programu Q # uruchamianego w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="5c317-116">Demonstrate quantum entanglement with a Q# program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="5c317-117">Prezentowanie zachowania qubit z QDK</span><span class="sxs-lookup"><span data-stu-id="5c317-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="5c317-118">Bity klasyczne przechowują jedną wartość binarną, taką jak 0 lub 1, natomiast [kubit](xref:microsoft.quantum.glossary#qubit) może być w stanie **superpozycji** wartości 0 i 1.</span><span class="sxs-lookup"><span data-stu-id="5c317-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="5c317-119">Koncepcyjnie, stan qubit można traktować jako kierunek w przestrzeni abstrakcyjnej (znanej również jako wektor).</span><span class="sxs-lookup"><span data-stu-id="5c317-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="5c317-120">Stan qubit może być w dowolnym z możliwych instrukcji.</span><span class="sxs-lookup"><span data-stu-id="5c317-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="5c317-121">Dwa **stany klasyczne** są dwoma określonymi kierunkami — reprezentującymi stuprocentową szansę zmierzenia wartości 0 i stuprocentową szansę zmierzenia wartości 1.</span><span class="sxs-lookup"><span data-stu-id="5c317-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="5c317-122">Pomiar pozwala uzyskać wynik binarny i zmienia stan kubitu.</span><span class="sxs-lookup"><span data-stu-id="5c317-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="5c317-123">Pomiar tworzy wartość binarną, 0 lub 1.</span><span class="sxs-lookup"><span data-stu-id="5c317-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="5c317-124">Kubit przechodzi z superpozycji (dowolny kierunek) do jednego ze stanów klasycznych.</span><span class="sxs-lookup"><span data-stu-id="5c317-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="5c317-125">Następne powtórzenia tego samego pomiaru bez wykonywania żadnych pośrednich interwencji dają taki sam wynik binarny.</span><span class="sxs-lookup"><span data-stu-id="5c317-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="5c317-126">Wiele kubitów może być [**splątanych**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="5c317-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="5c317-127">Gdy mierzymy jeden ze splątanych kubitów, powoduje to również aktualizację naszej wiedzy o stanie pozostałych kubitów.</span><span class="sxs-lookup"><span data-stu-id="5c317-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="5c317-128">Teraz wszystko jest gotowe do zademonstrowania, jak wyrazić to zachowanie w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="5c317-128">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="5c317-129">Rozpoczniesz od najprostszego możliwego programu i rozbudujesz go w celu zademonstrowania zjawisk superpozycji kwantowej i splątania kwantowego.</span><span class="sxs-lookup"><span data-stu-id="5c317-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-q-project"></a><span data-ttu-id="5c317-130">Tworzenie projektu Q #</span><span class="sxs-lookup"><span data-stu-id="5c317-130">Creating a Q# project</span></span>

<span data-ttu-id="5c317-131">Pierwszą czynnością, którą należy wykonać, jest utworzenie nowego projektu Q #.</span><span class="sxs-lookup"><span data-stu-id="5c317-131">The first thing we have to do is to create a new Q# project.</span></span> <span data-ttu-id="5c317-132">W tym samouczku zamierzamy używać środowiska na podstawie [aplikacji wiersza polecenia z vs Code](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="5c317-132">In this tutorial we are going to use the environment based on [command line applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="5c317-133">Aby utworzyć nowy projekt, w VS Code:</span><span class="sxs-lookup"><span data-stu-id="5c317-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="5c317-134">Kliknij pozycję **View** -> **Command Palette**, a następnie wybierz polecenie **Q#: Create New Project** (Q#: utwórz nowy projekt).</span><span class="sxs-lookup"><span data-stu-id="5c317-134">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="5c317-135">Kliknij pozycję **Standalone console application** (Autonomiczna aplikacja konsolowa).</span><span class="sxs-lookup"><span data-stu-id="5c317-135">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="5c317-136">Przejdź do lokalizacji, w której chcesz zapisać projekt, a następnie kliknij pozycję **Create project** (Utwórz projekt).</span><span class="sxs-lookup"><span data-stu-id="5c317-136">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="5c317-137">Po pomyślnym utworzeniu projektu kliknij pozycję **Open new project...** (Otwórz nowy projekt) w prawym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="5c317-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="5c317-138">W takim przypadku nazywamy projektem `Bell` .</span><span class="sxs-lookup"><span data-stu-id="5c317-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="5c317-139">Spowoduje to wygenerowanie dwóch plików: `Bell.csproj` , pliku projektu i `Program.qs` szablonu aplikacji Q #, która zostanie użyta do zapisania naszej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5c317-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a Q# application that we will use to write our application.</span></span> <span data-ttu-id="5c317-140">Zawartość `Program.qs` powinna być:</span><span class="sxs-lookup"><span data-stu-id="5c317-140">The content of `Program.qs` should be:</span></span>

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

## <a name="write-the-q-application"></a><span data-ttu-id="5c317-141">Napisz aplikację Q \#</span><span class="sxs-lookup"><span data-stu-id="5c317-141">Write the Q\# application</span></span>
 
<span data-ttu-id="5c317-142">Naszym celem jest przygotowanie dwóch kubitów w określonym stanie kwantowym, aby zademonstrować sposób wykonywania operacji na kubitach za pomocą języka Q# w celu zmieniania ich stanu, a także zademonstrować efekty superpozycji i splątania.</span><span class="sxs-lookup"><span data-stu-id="5c317-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="5c317-143">Utworzymy ten element, aby wprowadzić qubit Stany, operacje i pomiary.</span><span class="sxs-lookup"><span data-stu-id="5c317-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="5c317-144">Inicjowanie qubit przy użyciu miary</span><span class="sxs-lookup"><span data-stu-id="5c317-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="5c317-145">W pierwszym poniższym kodzie pokazujemy, jak pracować z kubitami w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="5c317-145">In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="5c317-146">Wprowadzimy dwie operacje [`M`](xref:microsoft.quantum.intrinsic.m) i [`X`](xref:microsoft.quantum.intrinsic.x) przekształciją stan qubit.</span><span class="sxs-lookup"><span data-stu-id="5c317-146">We’ll introduce two operations, [`M`](xref:microsoft.quantum.intrinsic.m) and [`X`](xref:microsoft.quantum.intrinsic.x) that transform the state of a qubit.</span></span> <span data-ttu-id="5c317-147">W tym fragmencie kodu jest definiowana operacja `SetQubitState`, która przyjmuje parametr w postaci kubitu i kolejny parametr `desired`, reprezentujący stan, w który należy wprowadzić kubit.</span><span class="sxs-lookup"><span data-stu-id="5c317-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="5c317-148">Operacja `SetQubitState` wykonuje pomiar kubitu za pomocą operacji `M`.</span><span class="sxs-lookup"><span data-stu-id="5c317-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="5c317-149">W polu Q # pomiar qubit zawsze zwraca wartość `Zero` lub `One` .</span><span class="sxs-lookup"><span data-stu-id="5c317-149">In Q#, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="5c317-150">Jeśli pomiar zwraca wartość, która nie jest równa żądanej wartości, `SetQubitState` "Przerzuć" qubit, czyli wykonuje `X` operację, która zmienia stan qubit na nowy stan, w którym prawdopodobieństwa zwracająca `Zero` wynik pomiaru i `One` jest odwrócona.</span><span class="sxs-lookup"><span data-stu-id="5c317-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="5c317-151">W ten sposób `SetQubitState` zawsze umieszcza docelowy qubit w żądanym stanie.</span><span class="sxs-lookup"><span data-stu-id="5c317-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="5c317-152">Zastąp zawartość `Program.qs` następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="5c317-152">Replace the contents of `Program.qs` with the following code:</span></span>


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

<span data-ttu-id="5c317-153">Można teraz wywołać tę operację, aby ustawić dla kubitu stan klasyczny, powodujący zwracanie wartości `Zero` przez 100% czasu lub zwracanie wartości `One` przez 100% czasu.</span><span class="sxs-lookup"><span data-stu-id="5c317-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="5c317-154">Wartości `Zero` i `One` są stałymi, które reprezentują dwa możliwe wyniki pomiaru kubitu.</span><span class="sxs-lookup"><span data-stu-id="5c317-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="5c317-155">Operacja `SetQubitState` mierzy kubit.</span><span class="sxs-lookup"><span data-stu-id="5c317-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="5c317-156">Jeśli kubit jest w żądanym stanie, operacja `SetQubitState` pozostawia go bez zmian; w przeciwnym razie zmieniamy stan kubitu na żądany, wykonując operację `X`.</span><span class="sxs-lookup"><span data-stu-id="5c317-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-q-operations"></a><span data-ttu-id="5c317-157">Informacje o operacjach języka Q#</span><span class="sxs-lookup"><span data-stu-id="5c317-157">About Q# operations</span></span>

<span data-ttu-id="5c317-158">Operacja języka Q# jest podprocedurą kwantową.</span><span class="sxs-lookup"><span data-stu-id="5c317-158">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="5c317-159">Oznacza to, że jest to wywoływana procedura, która zawiera wywołania innych operacji Quantum.</span><span class="sxs-lookup"><span data-stu-id="5c317-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="5c317-160">Argumenty operacji są przekazywane za pomocą krotki (w nawiasach).</span><span class="sxs-lookup"><span data-stu-id="5c317-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="5c317-161">Zwracany typ operacji jest określony po dwukropku.</span><span class="sxs-lookup"><span data-stu-id="5c317-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="5c317-162">W tym przypadku operacja `SetQubitState` nie zwraca wartości, więc jest oznaczona jako zwracająca wartość `Unit`.</span><span class="sxs-lookup"><span data-stu-id="5c317-162">In this case, the `SetQubitState` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="5c317-163">W języku Q# jest to odpowiednik wartości `unit` języka F#, która jest w przybliżeniu analogiczna do wartości `void` w języku C# i pustej krotki (`Tuple[()]`) w języku Python.</span><span class="sxs-lookup"><span data-stu-id="5c317-163">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="5c317-164">W pierwszej operacji języka Q# użyto dwóch operacji kwantowych:</span><span class="sxs-lookup"><span data-stu-id="5c317-164">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="5c317-165">[`M`](xref:microsoft.quantum.intrinsic.m)Operacja, która mierzy stan qubit</span><span class="sxs-lookup"><span data-stu-id="5c317-165">The [`M`](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="5c317-166">[`X`](xref:microsoft.quantum.intrinsic.x)Operacja, która przerzuca stan qubit</span><span class="sxs-lookup"><span data-stu-id="5c317-166">The [`X`](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="5c317-167">Operacja kwantowa przekształca stan kubitu.</span><span class="sxs-lookup"><span data-stu-id="5c317-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="5c317-168">Czasami mówi się o bramkach kwantowych zamiast operacji, analogicznie do klasycznych bramek logicznych.</span><span class="sxs-lookup"><span data-stu-id="5c317-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="5c317-169">Bierze się to z wczesnej epoki obliczeń kwantowych, gdy algorytmy stanowiły tylko konstrukcje teoretyczne i były wizualizowane jako diagramy, podobnie do diagramów obwodów w obliczeniach klasycznych.</span><span class="sxs-lookup"><span data-stu-id="5c317-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="5c317-170">Obliczanie wyników pomiaru</span><span class="sxs-lookup"><span data-stu-id="5c317-170">Counting measurement outcomes</span></span>

<span data-ttu-id="5c317-171">Aby zademonstrować efekt operacji `SetQubitState`, dodawana jest następnie operacja `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="5c317-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="5c317-172">Ta operacja przyjmuje jako dane wejściowe wartość `Zero` lub `One` i wywołuje operację `SetQubitState` pewną liczbę razy z tymi danymi wejściowymi, a także oblicza, ile razy została zwrócona wartość `Zero` z pomiaru kubitu i ile razy została zwrócona wartość `One`.</span><span class="sxs-lookup"><span data-stu-id="5c317-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="5c317-173">Oczywiście w tej pierwszej symulacji operacji `TestBellState` oczekujemy, że dane wyjściowe będą wskazywać, iż wszystkie pomiary kubitu z ustawionym parametrem wejściowym `Zero` będą zwracać wartość `Zero`, a wszystkie pomiary kubitu z ustawionym parametrem wejściowym `One` będą zwracać wartość `One`.</span><span class="sxs-lookup"><span data-stu-id="5c317-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="5c317-174">Dodatkowo dodamy kod do `TestBellState` przedstawienia do przedłożenia i Entanglement.</span><span class="sxs-lookup"><span data-stu-id="5c317-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="5c317-175">Dodaj następującą operację do pliku `Bell.qs` wewnątrz przestrzeni nazw po operacji `SetQubitState`:</span><span class="sxs-lookup"><span data-stu-id="5c317-175">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

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
<span data-ttu-id="5c317-176">Należy pamiętać, że dodaliśmy wiersz przed przystąpieniem `return` do drukowania komunikatu wyjaśniającego w konsoli programu za pomocą funkcji ( `Message` ) [Microsoft. Quantum. wewnętrzna. Message]</span><span class="sxs-lookup"><span data-stu-id="5c317-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="5c317-177">Ta operacja (`TestBellState`) wykona `count` iteracji pętli, ustawi określoną wartość `initial` dla kubitu, a następnie zmierzy (`M`) wynik.</span><span class="sxs-lookup"><span data-stu-id="5c317-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="5c317-178">Zbierze ona dane statystyczne dotyczące zmierzonej liczby zer i jedynek oraz zwróci je do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="5c317-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="5c317-179">Wykona także jedną inną wymaganą operację.</span><span class="sxs-lookup"><span data-stu-id="5c317-179">It performs one other necessary operation.</span></span> <span data-ttu-id="5c317-180">Zresetuje kubit do znanego stanu (`Zero`) przed jego zwróceniem, co umożliwi innym przydzielenie tego kubitu w znanym stanie.</span><span class="sxs-lookup"><span data-stu-id="5c317-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="5c317-181">Jest to wymagane przez instrukcję `using`.</span><span class="sxs-lookup"><span data-stu-id="5c317-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="5c317-182">Informacje o zmiennych w Q\#</span><span class="sxs-lookup"><span data-stu-id="5c317-182">About variables in Q\#</span></span>

<span data-ttu-id="5c317-183">Domyślnie zmienne w języku Q# są niezmienialne — ich wartości nie można zmienić po powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="5c317-183">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="5c317-184">Słowo kluczowe `let` jest używane do wskazania powiązania zmiennej niezmienialnej.</span><span class="sxs-lookup"><span data-stu-id="5c317-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="5c317-185">Argumenty operacji są zawsze niezmienialne.</span><span class="sxs-lookup"><span data-stu-id="5c317-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="5c317-186">Jeśli potrzebujesz zmiennej, której wartość można zmienić, takiej jak `numOnes` w przykładzie, możesz zadeklarować zmienną za pomocą słowa kluczowego `mutable`.</span><span class="sxs-lookup"><span data-stu-id="5c317-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="5c317-187">Wartość zmiennej modyfikowalnej zmienia się przy użyciu instrukcji `setQubitState`.</span><span class="sxs-lookup"><span data-stu-id="5c317-187">A mutable variable's value may be changed using a `setQubitState` statement.</span></span>

<span data-ttu-id="5c317-188">W obu przypadkach typ zmiennej jest wnioskowany przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="5c317-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="5c317-189">Język Q# nie wymaga żadnych adnotacji typu dla zmiennych.</span><span class="sxs-lookup"><span data-stu-id="5c317-189">Q# doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="5c317-190">`using`Instrukcje w temacie Q\#</span><span class="sxs-lookup"><span data-stu-id="5c317-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="5c317-191">Instrukcja `using` jest również szczególna dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="5c317-191">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="5c317-192">Służy do przydzielania kubitów do użycia w bloku kodu.</span><span class="sxs-lookup"><span data-stu-id="5c317-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="5c317-193">W języku Q# wszystkie kubity są dynamicznie przydzielane i zwalniane — nie są stałymi zasobami w całym okresie istnienia złożonego algorytmu.</span><span class="sxs-lookup"><span data-stu-id="5c317-193">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="5c317-194">Instrukcja `using` przydziela zestaw kubitów na początku bloku i zwalnia te kubity na jego końcu.</span><span class="sxs-lookup"><span data-stu-id="5c317-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="execute-the-code-from-the-command-line"></a><span data-ttu-id="5c317-195">Wykonywanie kodu z wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="5c317-195">Execute the code from the command line</span></span>

<span data-ttu-id="5c317-196">Aby uruchomić kod, musimy określić kompilator, *który* jest wywoływany do uruchomienia, gdy zostanie podane `dotnet run` polecenie.</span><span class="sxs-lookup"><span data-stu-id="5c317-196">In order to run the code we need to specify the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="5c317-197">Jest to wykonywane z prostą zmianą w pliku Q #, dodając wiersz `@EntryPoint()` bezpośrednio poprzedzający możliwy do `TestBellState` przeprowadzenia: operację w tym przypadku.</span><span class="sxs-lookup"><span data-stu-id="5c317-197">This is done with a simple change in the Q# file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="5c317-198">Pełny kod powinien:</span><span class="sxs-lookup"><span data-stu-id="5c317-198">The full code should be:</span></span>

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

<span data-ttu-id="5c317-199">Aby uruchomić program, musimy określić `count` argumenty i `initial` z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="5c317-199">To run the program we need to specify `count` and `initial` arguments from the command line.</span></span> <span data-ttu-id="5c317-200">Wybierzmy na przykład `count = 1000` i `initial = One` .</span><span class="sxs-lookup"><span data-stu-id="5c317-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="5c317-201">Wprowadź następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="5c317-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="5c317-202">I należy obserwować następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="5c317-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="5c317-203">Jeśli spróbujesz `initial = Zero` :</span><span class="sxs-lookup"><span data-stu-id="5c317-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="5c317-204">Przygotowanie superpozycji</span><span class="sxs-lookup"><span data-stu-id="5c317-204">Prepare superposition</span></span>

<span data-ttu-id="5c317-205">Teraz przyjrzyjmy się sposobom, w jaki Q # Express ma na celu umieszczanie qubits w położeniu.</span><span class="sxs-lookup"><span data-stu-id="5c317-205">Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="5c317-206">Przypomnijmy, że kubit może być w stanie superpozycji wartości 0 i 1.</span><span class="sxs-lookup"><span data-stu-id="5c317-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="5c317-207">Użyjemy operacji `Hadamard`, aby go uzyskać.</span><span class="sxs-lookup"><span data-stu-id="5c317-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="5c317-208">Jeśli kubit znajduje się w dowolnym ze stanów klasycznych (gdy pomiar zwraca zawsze wartość `Zero` lub zawsze wartość `One`), operacja `Hadamard` lub `H` wprowadzi kubit w stan, w którym pomiar kubitu będzie zwracać wartość `Zero` przez 50% czasu i zwracać wartość `One` przez 50% czasu.</span><span class="sxs-lookup"><span data-stu-id="5c317-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="5c317-209">Koncepcyjnie kubit można uważać za będący w połowie między wartościami `Zero` i `One`.</span><span class="sxs-lookup"><span data-stu-id="5c317-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="5c317-210">Gdy teraz zasymulujemy operację `TestBellState`, zwracane wyniki będą zawierać w przybliżeniu równą liczbę wartości `Zero` i `One` po pomiarze.</span><span class="sxs-lookup"><span data-stu-id="5c317-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="5c317-211">`X`Przerzucanie stanu qubit</span><span class="sxs-lookup"><span data-stu-id="5c317-211">`X` flips qubit state</span></span>

<span data-ttu-id="5c317-212">Najpierw spróbujemy przerzucić kubit (jeśli kubit jest w stanie `Zero`, przerzucimy go do stanu `One` i na odwrót).</span><span class="sxs-lookup"><span data-stu-id="5c317-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="5c317-213">Wykonuje się to za pomocą operacji `X` przed wykonaniem pomiaru w operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="5c317-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="5c317-214">Teraz wyniki są wycofane:</span><span class="sxs-lookup"><span data-stu-id="5c317-214">Now the results are reversed:</span></span>

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

<span data-ttu-id="5c317-215">Teraz przyjrzyjmy się właściwościom Quantum klasy qubits.</span><span class="sxs-lookup"><span data-stu-id="5c317-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="5c317-216">`H`przygotowuje nałożenie</span><span class="sxs-lookup"><span data-stu-id="5c317-216">`H` prepares superposition</span></span>

<span data-ttu-id="5c317-217">Wszystko, co należy zrobić, to zastąpić operację `X` w poprzednim uruchomieniu operacją Hadamarda `H`.</span><span class="sxs-lookup"><span data-stu-id="5c317-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="5c317-218">Zamiast przerzucać kubit całkowicie z wartości 0 do wartości 1, przerzucimy go tylko w połowie.</span><span class="sxs-lookup"><span data-stu-id="5c317-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="5c317-219">Zastąpione wiersze w operacji `TestBellState` teraz wyglądają następująco:</span><span class="sxs-lookup"><span data-stu-id="5c317-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="5c317-220">Nowe wyniki są bardziej interesujące:</span><span class="sxs-lookup"><span data-stu-id="5c317-220">Now the results get more interesting:</span></span>

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

<span data-ttu-id="5c317-221">Przy każdym wykonaniu pomiaru żądamy wartości klasycznej, lecz kubit jest w stanie przejściowym między wartościami 0 i 1, więc otrzymamy (statystycznie) wartość 0 w połowie przypadków i wartość 1 w pozostałych przypadkach.</span><span class="sxs-lookup"><span data-stu-id="5c317-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="5c317-222">Jest to zjawisko **superpozycji**, które daje nam po raz pierwszy wgląd w rzeczywisty stan kwantowy.</span><span class="sxs-lookup"><span data-stu-id="5c317-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="5c317-223">Przygotowanie splątania</span><span class="sxs-lookup"><span data-stu-id="5c317-223">Prepare entanglement</span></span>

<span data-ttu-id="5c317-224">Teraz zobaczmy, jak można wyrażać splątanie w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="5c317-224">Now let’s look at how Q# expresses ways to entangle qubits.</span></span>
<span data-ttu-id="5c317-225">Najpierw ustawiamy pierwszy kubit w stanie początkowym, a następnie wprowadzamy go w stan superpozycji za pomocą operacji `H`.</span><span class="sxs-lookup"><span data-stu-id="5c317-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="5c317-226">Następnie przed pomiarem pierwszego qubit używamy nowej operacji ( `CNOT` ), która oznacza, że nie jest to kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="5c317-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-NOT.</span></span>  <span data-ttu-id="5c317-227">Wynikiem wykonania tej operacji na dwóch kubitach jest przerzucenie drugiego kubitu, jeśli pierwszy kubit ma wartość `One`.</span><span class="sxs-lookup"><span data-stu-id="5c317-227">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="5c317-228">Teraz oba kubity są splątane.</span><span class="sxs-lookup"><span data-stu-id="5c317-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="5c317-229">Nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości `Zero` i `One` po pomiarze), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu.</span><span class="sxs-lookup"><span data-stu-id="5c317-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="5c317-230">Bramka `CNOT` splątała dwa kubity — cokolwiek dzieje się z jednym z nich, to samo dzieje się z drugim.</span><span class="sxs-lookup"><span data-stu-id="5c317-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="5c317-231">W przypadku odwrócenia pomiarów (drugi kubit przed pierwszym) będzie dziać się to samo.</span><span class="sxs-lookup"><span data-stu-id="5c317-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="5c317-232">Pierwsza miara będzie losowa, a druga zablokowana na wartości pierwszej.</span><span class="sxs-lookup"><span data-stu-id="5c317-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="5c317-233">Najpierw należy przydzielić dwie qubits zamiast jednego w `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="5c317-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="5c317-234">Pozwoli to dodać nową operację (`CNOT`) przed wykonaniem pomiaru (`M`) w operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="5c317-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="5c317-235">Dodaliśmy kolejną operację `SetQubitState`, aby zainicjować pierwszy kubit w celu zapewnienia, że jest zawsze w stanie `Zero` podczas uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="5c317-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="5c317-236">Musimy też zresetować drugi kubit przed jego zwolnieniem.</span><span class="sxs-lookup"><span data-stu-id="5c317-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="5c317-237">Pełna procedura wygląda teraz następująco:</span><span class="sxs-lookup"><span data-stu-id="5c317-237">The full routine now looks like this:</span></span>

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

<span data-ttu-id="5c317-238">Jeśli ją uruchomimy, uzyskamy dokładnie taki sam wynik 50%-50% jak poprzednio.</span><span class="sxs-lookup"><span data-stu-id="5c317-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="5c317-239">Jednak teraz interesuje nas, jak drugi kubit reaguje na pomiar pierwszego.</span><span class="sxs-lookup"><span data-stu-id="5c317-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="5c317-240">Dodamy tę statystykę do nowej wersji operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="5c317-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

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

<span data-ttu-id="5c317-241">Nowa wartość zwracana (`agree`) śledzi przypadki, gdy pomiar pierwszego kubitu jest zgodny z pomiarem drugiego kubitu.</span><span class="sxs-lookup"><span data-stu-id="5c317-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="5c317-242">Uruchamianie kodu, który uzyskamy:</span><span class="sxs-lookup"><span data-stu-id="5c317-242">Running the code we obtain:</span></span>

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

<span data-ttu-id="5c317-243">Jak podano w omówieniu, nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości 0 i 1), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu, ponieważ są one splątane!</span><span class="sxs-lookup"><span data-stu-id="5c317-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c317-244">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="5c317-244">Next steps</span></span>

<span data-ttu-id="5c317-245">W samouczku [Wyszukiwanie Grovera](xref:microsoft.quantum.quickstarts.search) przedstawiono tworzenie i uruchamianie wyszukiwania Grovera — jednego z najpopularniejszych algorytmów obliczeń kwantowych — oraz podano ciekawy przykład programu języka Q#, którego można użyć do rozwiązywania rzeczywistych problemów obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="5c317-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="5c317-246">Artykuł [Wprowadzenie do zestawu Quantum Development Kit](xref:microsoft.quantum.welcome) zawiera więcej zalecanych sposobów uczenia się języka Q# i programowania kwantowego.</span><span class="sxs-lookup"><span data-stu-id="5c317-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
