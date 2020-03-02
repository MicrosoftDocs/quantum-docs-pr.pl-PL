---
title: Podstawy obliczeń kwantowych w języku Q#
description: Dowiedz się, jak napisać program kwantowy w języku Q#. Opracowywanie aplikacji stanu Bella za pomocą zestawu QDK (Quantum Development Kit)
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 8d3b2d7c8da39a961f4eedcc5989ad3a1e134ade
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906733"
---
# <a name="quantum-basics-with-q"></a><span data-ttu-id="405d9-104">Podstawy obliczeń kwantowych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-104">Quantum basics with Q#</span></span>

<span data-ttu-id="405d9-105">W tym przewodniku Szybki start pokazano, jak napisać program języka Q#, który manipuluje kubitami, mierzy je oraz przedstawia efekty superpozycji i splątania.</span><span class="sxs-lookup"><span data-stu-id="405d9-105">In this Quickstart, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>  <span data-ttu-id="405d9-106">Przewodnik obejmuje instalowanie zestawu QDK, tworzenie programu i uruchamianie go na symulatorze kwantowym.</span><span class="sxs-lookup"><span data-stu-id="405d9-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="405d9-107">Napiszesz aplikację o nazwie Bell, aby zademonstrować splątanie kwantowe.</span><span class="sxs-lookup"><span data-stu-id="405d9-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>  <span data-ttu-id="405d9-108">Nazwisko Bell odnosi się do stanów Bella — specyficznych stanów kwantowych dwóch kubitów, które są używane do reprezentowania najprostszych przykładów superpozycji i splątania kwantowego.</span><span class="sxs-lookup"><span data-stu-id="405d9-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span> 

## <a name="pre-requisites"></a><span data-ttu-id="405d9-109">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="405d9-109">Pre-requisites</span></span>

<span data-ttu-id="405d9-110">Gdy wszystko będzie gotowe do rozpoczęcia kodowania, wykonaj następujące kroki przed kontynuowaniem:</span><span class="sxs-lookup"><span data-stu-id="405d9-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="405d9-111">[Zainstaluj](xref:microsoft.quantum.install) zestaw Quantum Development Kit przy użyciu preferowanego języka i środowiska programistycznego.</span><span class="sxs-lookup"><span data-stu-id="405d9-111">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment</span></span>
* <span data-ttu-id="405d9-112">Jeśli masz już zainstalowany zestaw QDK, upewnij się, że [zaktualizowano](xref:microsoft.quantum.update) go do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="405d9-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="405d9-113">Możesz też przeczytać opis, nie instalując zestawu QDK, przeglądając omówienia języka programowania Q# i pierwsze koncepcje obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="405d9-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="405d9-114">Demonstrowanie zachowania kubitów przy użyciu języka Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="405d9-115">Przypomnijmy prostą [definicję kubitu](xref:microsoft.quantum.overview.what#the-qubit).</span><span class="sxs-lookup"><span data-stu-id="405d9-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.what#the-qubit).</span></span>  <span data-ttu-id="405d9-116">Bity klasyczne przechowują jedną wartość binarną, taką jak 0 lub 1, natomiast kubit może być w stanie **superpozycji** wartości 0 i 1 równocześnie.</span><span class="sxs-lookup"><span data-stu-id="405d9-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a qubit can be in a **superposition** of 0 and 1 simultaneously.</span></span>  <span data-ttu-id="405d9-117">Koncepcyjnie kubit można uważać za kierunek w przestrzeni (nazywany też wektorem).</span><span class="sxs-lookup"><span data-stu-id="405d9-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="405d9-118">Kubit może mieć dowolny z możliwych kierunków.</span><span class="sxs-lookup"><span data-stu-id="405d9-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="405d9-119">Dwa **stany klasyczne** są dwoma określonymi kierunkami — reprezentującymi stuprocentową szansę zmierzenia wartości 0 i stuprocentową szansę zmierzenia wartości 1.</span><span class="sxs-lookup"><span data-stu-id="405d9-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="405d9-120">Tę reprezentację można też bardziej formalnie zwizualizować za pomocą [sfery Blocha](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="405d9-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>


<span data-ttu-id="405d9-121">Pomiar pozwala uzyskać wynik binarny i zmienia stan kubitu.</span><span class="sxs-lookup"><span data-stu-id="405d9-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="405d9-122">Wynikiem pomiaru jest wartość binarna 0 lub 1.</span><span class="sxs-lookup"><span data-stu-id="405d9-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="405d9-123">Kubit przechodzi z superpozycji (dowolny kierunek) do jednego ze stanów klasycznych.</span><span class="sxs-lookup"><span data-stu-id="405d9-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="405d9-124">Następne powtórzenia tego samego pomiaru bez wykonywania żadnych pośrednich interwencji dają taki sam wynik binarny.</span><span class="sxs-lookup"><span data-stu-id="405d9-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="405d9-125">Wiele kubitów może być **splątanych**.</span><span class="sxs-lookup"><span data-stu-id="405d9-125">Multiple qubits can be **entangled**.</span></span> <span data-ttu-id="405d9-126">Gdy mierzymy jeden ze splątanych kubitów, powoduje to również aktualizację naszej wiedzy o stanie pozostałych kubitów.</span><span class="sxs-lookup"><span data-stu-id="405d9-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="405d9-127">Teraz wszystko jest gotowe do zademonstrowania, jak wyrazić to zachowanie w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="405d9-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="405d9-128">Rozpoczniesz od najprostszego możliwego programu i rozbudujesz go w celu zademonstrowania zjawisk superpozycji kwantowej i splątania kwantowego.</span><span class="sxs-lookup"><span data-stu-id="405d9-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="405d9-129">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="405d9-129">Setup</span></span>

<span data-ttu-id="405d9-130">Aplikacje opracowane za pomocą zestawu Quantum Development Kit firmy Microsoft składają się z dwóch części:</span><span class="sxs-lookup"><span data-stu-id="405d9-130">Applications developed with Microsoft's Quantum Development Kit consist of two parts:</span></span>

1. <span data-ttu-id="405d9-131">Co najmniej jednego algorytmu kwantowego zaimplementowanego przy użyciu języka programowania kwantowego Q#.</span><span class="sxs-lookup"><span data-stu-id="405d9-131">One or more quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="405d9-132">Programu hosta zaimplementowanego w języku programowania takim jak Python lub C#, który służy jako główny punkt wejścia i wywołuje operacje języka Q# w celu wykonania algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="405d9-132">A host program, implemented in a programming language like Python or C# that serves as the main entry point and invokes Q# operations to execute a quantum algorithm.</span></span>

#### <a name="python"></a>[<span data-ttu-id="405d9-133">Python</span><span class="sxs-lookup"><span data-stu-id="405d9-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="405d9-134">Wybieranie lokalizacji dla aplikacji</span><span class="sxs-lookup"><span data-stu-id="405d9-134">Choose a location for your application</span></span>

1. <span data-ttu-id="405d9-135">Utwórz plik o nazwie `Bell.qs`.</span><span class="sxs-lookup"><span data-stu-id="405d9-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="405d9-136">Ten plik będzie zawierać kod Q#.</span><span class="sxs-lookup"><span data-stu-id="405d9-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="405d9-137">Utwórz plik o nazwie `host.py`.</span><span class="sxs-lookup"><span data-stu-id="405d9-137">Create a file called `host.py`.</span></span> <span data-ttu-id="405d9-138">Ten plik będzie zawierać kod hosta w języku Python.</span><span class="sxs-lookup"><span data-stu-id="405d9-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a><span data-ttu-id="405d9-139">[Wiersz polecenia języka C#](#tab/tabid-csharp).</span><span class="sxs-lookup"><span data-stu-id="405d9-139">[C# Command Line](#tab/tabid-csharp)</span></span>

1. <span data-ttu-id="405d9-140">Utwórz nowy projekt języka Q#:</span><span class="sxs-lookup"><span data-stu-id="405d9-140">Create a new Q# project:</span></span>

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="405d9-141">Powinien być widoczny plik `.csproj`, plik kodu Q# o nazwie `Operations.qs` i plik programu hosta o nazwie `Driver.cs`</span><span class="sxs-lookup"><span data-stu-id="405d9-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="405d9-142">Zmiana nazwy pliku kodu Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-142">Rename the Q# file</span></span>

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="405d9-143">Program Visual Studio</span><span class="sxs-lookup"><span data-stu-id="405d9-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="405d9-144">Tworzenie nowego projektu</span><span class="sxs-lookup"><span data-stu-id="405d9-144">Create a new project</span></span>

   * <span data-ttu-id="405d9-145">Otwórz program Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="405d9-145">Open Visual Studio</span></span>
   * <span data-ttu-id="405d9-146">Przejdź do menu **Plik**, a następnie wybierz pozycję **Nowy** -> **Projekt...** .</span><span class="sxs-lookup"><span data-stu-id="405d9-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="405d9-147">W eksploratorze szablonów projektów wpisz `Q#` w polu wyszukiwania i wybierz szablon `Q# Application`</span><span class="sxs-lookup"><span data-stu-id="405d9-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="405d9-148">Nadaj projektowi nazwę `Bell`.</span><span class="sxs-lookup"><span data-stu-id="405d9-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="405d9-149">Zmiana nazwy pliku kodu Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-149">Rename the Q# file</span></span>

   * <span data-ttu-id="405d9-150">Przejdź do **Eksploratora rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="405d9-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="405d9-151">Kliknij prawym przyciskiem myszy plik `Operations.qs`.</span><span class="sxs-lookup"><span data-stu-id="405d9-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="405d9-152">Zmień jego nazwę na `Bell.qs`.</span><span class="sxs-lookup"><span data-stu-id="405d9-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="405d9-153">Tworzenie operacji w języku Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-153">Write a Q# operation</span></span>

<span data-ttu-id="405d9-154">Naszym celem jest przygotowanie dwóch kubitów w określonym stanie kwantowym, aby zademonstrować sposób wykonywania operacji na kubitach za pomocą języka Q# w celu zmieniania ich stanu, a także zademonstrować efekty superpozycji i splątania.</span><span class="sxs-lookup"><span data-stu-id="405d9-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="405d9-155">Zrobimy to krok po kroku, aby przedstawić stany, operacje i pomiary kubitów.</span><span class="sxs-lookup"><span data-stu-id="405d9-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="405d9-156">**Omówienie:**  W pierwszym poniższym kodzie pokazujemy, jak pracować z kubitami w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="405d9-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="405d9-157">Wprowadzimy dwie operacje (`M` i `X`), które przekształcają stan kubitu.</span><span class="sxs-lookup"><span data-stu-id="405d9-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="405d9-158">W tym fragmencie kodu jest definiowana operacja `Set`, która przyjmuje parametr w postaci kubitu i kolejny parametr `desired`, reprezentujący stan, w który należy wprowadzić kubit.</span><span class="sxs-lookup"><span data-stu-id="405d9-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="405d9-159">Operacja `Set` wykonuje pomiar kubitu za pomocą operacji `M`.</span><span class="sxs-lookup"><span data-stu-id="405d9-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="405d9-160">W języku Q# pomiar kubitu zawsze zwraca wartość `Zero` lub `One`.</span><span class="sxs-lookup"><span data-stu-id="405d9-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="405d9-161">Jeśli pomiar zwróci wartość, która nie jest równa żądanej wartości, operacja Set „przerzuci” kubit, tzn. wykona operację `X`, która zmienia stan kubitu na nowy stan, w którym prawdopodobieństwa zwrócenia wartości `Zero` i `One` są odwrócone.</span><span class="sxs-lookup"><span data-stu-id="405d9-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="405d9-162">Aby zademonstrować efekt operacji `Set`, dodawana jest następnie operacja `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="405d9-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="405d9-163">Ta operacja przyjmuje jako dane wejściowe wartość `Zero` lub `One` i wywołuje operację `Set` pewną liczbę razy z tymi danymi wejściowymi, a także oblicza, ile razy została zwrócona wartość `Zero` z pomiaru kubitu i ile razy została zwrócona wartość `One`.</span><span class="sxs-lookup"><span data-stu-id="405d9-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="405d9-164">Oczywiście w tej pierwszej symulacji operacji `TestBellState` oczekujemy, że dane wyjściowe będą wskazywać, iż wszystkie pomiary kubitu z ustawionym parametrem wejściowym `Zero` będą zwracać wartość `Zero`, a wszystkie pomiary kubitu z ustawionym parametrem wejściowym `One` będą zwracać wartość `One`.</span><span class="sxs-lookup"><span data-stu-id="405d9-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="405d9-165">Następnie dodamy kod do elementu `TestBellState` w celu zademonstrowania superpozycji i splątania.</span><span class="sxs-lookup"><span data-stu-id="405d9-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="405d9-166">Kod operacji języka Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-166">Q# operation code</span></span>

1. <span data-ttu-id="405d9-167">Zastąp zawartość pliku Bell.qs następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="405d9-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="405d9-168">Można teraz wywołać tę operację, aby ustawić dla kubitu stan klasyczny, powodujący zwracanie wartości `Zero` przez 100% czasu lub zwracanie wartości `One` przez 100% czasu.</span><span class="sxs-lookup"><span data-stu-id="405d9-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="405d9-169">Wartości `Zero` i `One` są stałymi, które reprezentują dwa możliwe wyniki pomiaru kubitu.</span><span class="sxs-lookup"><span data-stu-id="405d9-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="405d9-170">Operacja `Set` mierzy kubit.</span><span class="sxs-lookup"><span data-stu-id="405d9-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="405d9-171">Jeśli kubit jest w żądanym stanie, operacja `Set` pozostawia go bez zmian; w przeciwnym razie zmieniamy stan kubitu na żądany, wykonując operację `X`.</span><span class="sxs-lookup"><span data-stu-id="405d9-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="405d9-172">Informacje o operacjach języka Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-172">About Q# operations</span></span>

<span data-ttu-id="405d9-173">Operacja języka Q# jest podprocedurą kwantową.</span><span class="sxs-lookup"><span data-stu-id="405d9-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="405d9-174">Oznacza to, że jest ona procedurą zawierającą operacje kwantowe.</span><span class="sxs-lookup"><span data-stu-id="405d9-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="405d9-175">Argumenty operacji są przekazywane za pomocą krotki (w nawiasach).</span><span class="sxs-lookup"><span data-stu-id="405d9-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="405d9-176">Zwracany typ operacji jest określony po dwukropku.</span><span class="sxs-lookup"><span data-stu-id="405d9-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="405d9-177">W tym przypadku operacja `Set` nie zwraca wartości, więc jest oznaczona jako zwracająca wartość `Unit`.</span><span class="sxs-lookup"><span data-stu-id="405d9-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="405d9-178">W języku Q# jest to odpowiednik wartości `unit` języka F#, która jest w przybliżeniu analogiczna do wartości `void` w języku C# i pustej krotki (`Tuple[()]`) w języku Python.</span><span class="sxs-lookup"><span data-stu-id="405d9-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="405d9-179">W pierwszej operacji języka Q# użyto dwóch operacji kwantowych:</span><span class="sxs-lookup"><span data-stu-id="405d9-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="405d9-180">Operacja [M](xref:microsoft.quantum.intrinsic.m), która mierzy stan kubitu</span><span class="sxs-lookup"><span data-stu-id="405d9-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="405d9-181">Operacja [X](xref:microsoft.quantum.intrinsic.x), która przerzuca stan kubitu</span><span class="sxs-lookup"><span data-stu-id="405d9-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="405d9-182">Operacja kwantowa przekształca stan kubitu.</span><span class="sxs-lookup"><span data-stu-id="405d9-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="405d9-183">Czasami mówi się o bramkach kwantowych zamiast operacji, analogicznie do klasycznych bramek logicznych.</span><span class="sxs-lookup"><span data-stu-id="405d9-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="405d9-184">Bierze się to z wczesnej epoki obliczeń kwantowych, gdy algorytmy stanowiły tylko konstrukcje teoretyczne i były wizualizowane jako diagramy, podobnie do diagramów obwodów w obliczeniach klasycznych.</span><span class="sxs-lookup"><span data-stu-id="405d9-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="405d9-185">Dodawanie kodu testowego Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-185">Add Q# test code</span></span>

1. <span data-ttu-id="405d9-186">Dodaj następującą operację do pliku `Bell.qs` wewnątrz przestrzeni nazw po operacji `Set`:</span><span class="sxs-lookup"><span data-stu-id="405d9-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="405d9-187">Ta operacja (`TestBellState`) wykona `count` iteracji pętli, ustawi określoną wartość `initial` dla kubitu, a następnie zmierzy (`M`) wynik.</span><span class="sxs-lookup"><span data-stu-id="405d9-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="405d9-188">Zbierze ona dane statystyczne dotyczące zmierzonej liczby zer i jedynek oraz zwróci je do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="405d9-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="405d9-189">Wykona także jedną inną wymaganą operację.</span><span class="sxs-lookup"><span data-stu-id="405d9-189">It performs one other necessary operation.</span></span> <span data-ttu-id="405d9-190">Zresetuje kubit do znanego stanu (`Zero`) przed jego zwróceniem, co umożliwi innym przydzielenie tego kubitu w znanym stanie.</span><span class="sxs-lookup"><span data-stu-id="405d9-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="405d9-191">Jest to wymagane przez instrukcję `using`.</span><span class="sxs-lookup"><span data-stu-id="405d9-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="405d9-192">Informacje o zmiennych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-192">About variables in Q#</span></span>

<span data-ttu-id="405d9-193">Domyślnie zmienne w języku Q# są niezmienialne — ich wartości nie można zmienić po powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="405d9-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="405d9-194">Słowo kluczowe `let` jest używane do wskazania powiązania zmiennej niezmienialnej.</span><span class="sxs-lookup"><span data-stu-id="405d9-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="405d9-195">Argumenty operacji są zawsze niezmienialne.</span><span class="sxs-lookup"><span data-stu-id="405d9-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="405d9-196">Jeśli potrzebujesz zmiennej, której wartość można zmienić, takiej jak `numOnes` w przykładzie, możesz zadeklarować zmienną za pomocą słowa kluczowego `mutable`.</span><span class="sxs-lookup"><span data-stu-id="405d9-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="405d9-197">Wartość zmiennej modyfikowalnej zmienia się przy użyciu instrukcji `set`.</span><span class="sxs-lookup"><span data-stu-id="405d9-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="405d9-198">W obu przypadkach typ zmiennej jest wnioskowany przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="405d9-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="405d9-199">Język Q# nie wymaga żadnych adnotacji typu dla zmiennych.</span><span class="sxs-lookup"><span data-stu-id="405d9-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="405d9-200">Informacje o instrukcjach `using` w języku Q#</span><span class="sxs-lookup"><span data-stu-id="405d9-200">About `using` statements in Q#</span></span>

<span data-ttu-id="405d9-201">Instrukcja `using` jest również szczególna dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="405d9-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="405d9-202">Służy do przydzielania kubitów do użycia w bloku kodu.</span><span class="sxs-lookup"><span data-stu-id="405d9-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="405d9-203">W języku Q# wszystkie kubity są dynamicznie przydzielane i zwalniane — nie są stałymi zasobami w całym okresie istnienia złożonego algorytmu.</span><span class="sxs-lookup"><span data-stu-id="405d9-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="405d9-204">Instrukcja `using` przydziela zestaw kubitów na początku bloku i zwalnia te kubity na jego końcu.</span><span class="sxs-lookup"><span data-stu-id="405d9-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="405d9-205">Tworzenie kodu aplikacji hosta</span><span class="sxs-lookup"><span data-stu-id="405d9-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="405d9-206">Python</span><span class="sxs-lookup"><span data-stu-id="405d9-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="405d9-207">Otwórz plik `host.py` i dodaj następujący kod:</span><span class="sxs-lookup"><span data-stu-id="405d9-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[<span data-ttu-id="405d9-208">C#</span><span class="sxs-lookup"><span data-stu-id="405d9-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="405d9-209">Zastąp zawartość pliku `Driver.cs` następującym kodem:</span><span class="sxs-lookup"><span data-stu-id="405d9-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="405d9-210">Informacje o kodzie aplikacji hosta</span><span class="sxs-lookup"><span data-stu-id="405d9-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="405d9-211">Python</span><span class="sxs-lookup"><span data-stu-id="405d9-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="405d9-212">Aplikacja hosta w języka Python ma trzy części:</span><span class="sxs-lookup"><span data-stu-id="405d9-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="405d9-213">Oblicza wszystkie argumenty wymagane dla algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="405d9-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="405d9-214">W przykładzie zmienna `count` ma stałą wartość 1000, a zmienna `initial` to wartość początkowa kubitu.</span><span class="sxs-lookup"><span data-stu-id="405d9-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="405d9-215">Uruchamia algorytm kwantowy, wywołując metodę `simulate()` zaimportowanej operacji języka Q#.</span><span class="sxs-lookup"><span data-stu-id="405d9-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="405d9-216">Przetwarza wynik operacji.</span><span class="sxs-lookup"><span data-stu-id="405d9-216">Process the result of the operation.</span></span> <span data-ttu-id="405d9-217">W przykładzie zmienna `res` otrzymuje wynik operacji.</span><span class="sxs-lookup"><span data-stu-id="405d9-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="405d9-218">Tutaj wynik jest krotką liczby zer (`num_zeros`) i liczby jedynek (`num_ones`) zmierzonych przez symulator.</span><span class="sxs-lookup"><span data-stu-id="405d9-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="405d9-219">Rozdzielamy krotkę, aby uzyskać dwa pola, i drukujemy wyniki.</span><span class="sxs-lookup"><span data-stu-id="405d9-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="405d9-220">C#</span><span class="sxs-lookup"><span data-stu-id="405d9-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="405d9-221">Aplikacja hosta w języku C# ma cztery części:</span><span class="sxs-lookup"><span data-stu-id="405d9-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="405d9-222">Konstruuje symulator kwantowy.</span><span class="sxs-lookup"><span data-stu-id="405d9-222">Construct a quantum simulator.</span></span> <span data-ttu-id="405d9-223">W przykładzie element `qsim` jest symulatorem.</span><span class="sxs-lookup"><span data-stu-id="405d9-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="405d9-224">Oblicza wszystkie argumenty wymagane dla algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="405d9-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="405d9-225">W przykładzie zmienna `count` ma stałą wartość 1000, a zmienna `initial` to wartość początkowa kubitu.</span><span class="sxs-lookup"><span data-stu-id="405d9-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="405d9-226">Uruchamia algorytm kwantowy.</span><span class="sxs-lookup"><span data-stu-id="405d9-226">Run the quantum algorithm.</span></span> <span data-ttu-id="405d9-227">Każda operacja języka Q# generuje klasę języka C# o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="405d9-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="405d9-228">Ta klasa ma metodę `Run`, która **asynchronicznie** wykonuje operację.</span><span class="sxs-lookup"><span data-stu-id="405d9-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="405d9-229">Wykonanie jest asynchroniczne, ponieważ wykonanie na rzeczywistym sprzęcie będzie asynchroniczne.</span><span class="sxs-lookup"><span data-stu-id="405d9-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="405d9-230">Ponieważ metoda `Run` jest asynchroniczna, pobieramy właściwość `Result`. To blokuje wykonywanie do momentu zakończenia zadania i powoduje synchronicznie zwrócenie wyniku.</span><span class="sxs-lookup"><span data-stu-id="405d9-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="405d9-231">Przetwarza wynik operacji.</span><span class="sxs-lookup"><span data-stu-id="405d9-231">Process the result of the operation.</span></span> <span data-ttu-id="405d9-232">W przykładzie zmienna `res` otrzymuje wynik operacji.</span><span class="sxs-lookup"><span data-stu-id="405d9-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="405d9-233">Tutaj wynik jest krotką liczby zer (`numZeros`) i liczby jedynek (`numOnes`) zmierzonych przez symulator.</span><span class="sxs-lookup"><span data-stu-id="405d9-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="405d9-234">Jest on zwracany jako element ValueTuple w języku C#.</span><span class="sxs-lookup"><span data-stu-id="405d9-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="405d9-235">Rozdzielamy krotkę, aby uzyskać dwa pola, drukujemy wyniki i czekamy na naciśnięcie klawisza.</span><span class="sxs-lookup"><span data-stu-id="405d9-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="405d9-236">Kompilowanie i uruchamianie</span><span class="sxs-lookup"><span data-stu-id="405d9-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="405d9-237">Python</span><span class="sxs-lookup"><span data-stu-id="405d9-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="405d9-238">Uruchom następujące polecenie w terminalu:</span><span class="sxs-lookup"><span data-stu-id="405d9-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="405d9-239">To polecenie uruchamia aplikację hosta, która symuluje operację języka Q#.</span><span class="sxs-lookup"><span data-stu-id="405d9-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="405d9-240">Wyniki powinny być następujące:</span><span class="sxs-lookup"><span data-stu-id="405d9-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="405d9-241">Wiersz polecenia/program Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="405d9-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="405d9-242">Uruchom następujące polecenie w terminalu:</span><span class="sxs-lookup"><span data-stu-id="405d9-242">Run the following at your terminal:</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="405d9-243">To polecenie spowoduje automatyczne pobranie wszystkich wymaganych pakietów, skompilowanie aplikacji, a następnie uruchomienie jej w wierszu polecenia.</span><span class="sxs-lookup"><span data-stu-id="405d9-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="405d9-244">Alternatywnie naciśnij klawisz **F1**, aby otworzyć paletę poleceń, i wybierz polecenie **Debuguj: Uruchom bez debugowania**.</span><span class="sxs-lookup"><span data-stu-id="405d9-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="405d9-245">Może zostać wyświetlony monit o utworzenie nowego pliku ``launch.json`` opisującego sposób uruchamiania programu.</span><span class="sxs-lookup"><span data-stu-id="405d9-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="405d9-246">Domyślny plik ``launch.json`` powinien wystarczyć dla większości aplikacji.</span><span class="sxs-lookup"><span data-stu-id="405d9-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="405d9-247">Wyniki powinny być następujące:</span><span class="sxs-lookup"><span data-stu-id="405d9-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="405d9-248">Program Visual Studio</span><span class="sxs-lookup"><span data-stu-id="405d9-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="405d9-249">Po prostu naciśnij klawisz `F5`, a program powinien zostać skompilowany i uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="405d9-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="405d9-250">Wyniki powinny być następujące:</span><span class="sxs-lookup"><span data-stu-id="405d9-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="405d9-251">Program zostanie zakończony po naciśnięciu klawisza.</span><span class="sxs-lookup"><span data-stu-id="405d9-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="405d9-252">Przygotowanie superpozycji</span><span class="sxs-lookup"><span data-stu-id="405d9-252">Prepare superposition</span></span>

<span data-ttu-id="405d9-253">**Przegląd** Teraz przyjrzyjmy się, jak w języku Q# można wyrazić wprowadzanie kubitów w stan superpozycji.</span><span class="sxs-lookup"><span data-stu-id="405d9-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="405d9-254">Przypomnijmy, że kubit może być w stanie superpozycji wartości 0 i 1.</span><span class="sxs-lookup"><span data-stu-id="405d9-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="405d9-255">Użyjemy operacji `Hadamard`, aby go uzyskać.</span><span class="sxs-lookup"><span data-stu-id="405d9-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="405d9-256">Jeśli kubit znajduje się w dowolnym ze stanów klasycznych (gdy pomiar zwraca zawsze wartość `Zero` lub zawsze wartość `One`), operacja `Hadamard` lub `H` wprowadzi kubit w stan, w którym pomiar kubitu będzie zwracać wartość `Zero` przez 50% czasu i zwracać wartość `One` przez 50% czasu.</span><span class="sxs-lookup"><span data-stu-id="405d9-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="405d9-257">Koncepcyjnie kubit można uważać za będący w połowie między wartościami `Zero` i `One`.</span><span class="sxs-lookup"><span data-stu-id="405d9-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="405d9-258">Gdy teraz zasymulujemy operację `TestBellState`, zwracane wyniki będą zawierać w przybliżeniu równą liczbę wartości `Zero` i `One` po pomiarze.</span><span class="sxs-lookup"><span data-stu-id="405d9-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="405d9-259">Najpierw spróbujemy przerzucić kubit (jeśli kubit jest w stanie `Zero`, przerzucimy go do stanu `One` i na odwrót).</span><span class="sxs-lookup"><span data-stu-id="405d9-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="405d9-260">Wykonuje się to za pomocą operacji `X` przed wykonaniem pomiaru w operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="405d9-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="405d9-261">Teraz wyniki (po naciśnięciu klawisza `F5`) są odwrócone:</span><span class="sxs-lookup"><span data-stu-id="405d9-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="405d9-262">Jednak wszystko, co zobaczyliśmy dotychczas, jest „klasyczne”.</span><span class="sxs-lookup"><span data-stu-id="405d9-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="405d9-263">Uzyskajmy wynik kwantowy.</span><span class="sxs-lookup"><span data-stu-id="405d9-263">Let's get a quantum result.</span></span> <span data-ttu-id="405d9-264">Wszystko, co należy zrobić, to zastąpić operację `X` w poprzednim uruchomieniu operacją Hadamarda `H`.</span><span class="sxs-lookup"><span data-stu-id="405d9-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="405d9-265">Zamiast przerzucać kubit całkowicie z wartości 0 do wartości 1, przerzucimy go tylko w połowie.</span><span class="sxs-lookup"><span data-stu-id="405d9-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="405d9-266">Zastąpione wiersze w operacji `TestBellState` teraz wyglądają następująco:</span><span class="sxs-lookup"><span data-stu-id="405d9-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="405d9-267">Nowe wyniki są bardziej interesujące:</span><span class="sxs-lookup"><span data-stu-id="405d9-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="405d9-268">Przy każdym wykonaniu pomiaru żądamy wartości klasycznej, lecz kubit jest w stanie przejściowym między wartościami 0 i 1, więc otrzymamy (statystycznie) wartość 0 w połowie przypadków i wartość 1 w pozostałych przypadkach.</span><span class="sxs-lookup"><span data-stu-id="405d9-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="405d9-269">Jest to zjawisko __superpozycji__, które daje nam po raz pierwszy wgląd w rzeczywisty stan kwantowy.</span><span class="sxs-lookup"><span data-stu-id="405d9-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="405d9-270">Przygotowanie splątania</span><span class="sxs-lookup"><span data-stu-id="405d9-270">Prepare entanglement</span></span>

<span data-ttu-id="405d9-271">**Omówienie:**  Teraz zobaczmy, jak można wyrażać splątanie w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="405d9-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="405d9-272">Najpierw ustawiamy pierwszy kubit w stanie początkowym, a następnie wprowadzamy go w stan superpozycji za pomocą operacji `H`.</span><span class="sxs-lookup"><span data-stu-id="405d9-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="405d9-273">Następnie, przed pomiarem pierwszego kubitu, używamy nowej operacji (`CNOT`), czyli Controlled-Not.</span><span class="sxs-lookup"><span data-stu-id="405d9-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="405d9-274">Wynikiem wykonania tej operacji na dwóch kubitach jest przerzucenie drugiego kubitu, jeśli pierwszy kubit ma wartość `One`.</span><span class="sxs-lookup"><span data-stu-id="405d9-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="405d9-275">Teraz oba kubity są splątane.</span><span class="sxs-lookup"><span data-stu-id="405d9-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="405d9-276">Nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości `Zero` i `One` po pomiarze), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu.</span><span class="sxs-lookup"><span data-stu-id="405d9-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="405d9-277">Bramka `CNOT` splątała dwa kubity — cokolwiek dzieje się z jednym z nich, to samo dzieje się z drugim.</span><span class="sxs-lookup"><span data-stu-id="405d9-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="405d9-278">W przypadku odwrócenia pomiarów (drugi kubit przed pierwszym) będzie dziać się to samo.</span><span class="sxs-lookup"><span data-stu-id="405d9-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="405d9-279">Pierwsza miara będzie losowa, a druga zablokowana na wartości pierwszej.</span><span class="sxs-lookup"><span data-stu-id="405d9-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="405d9-280">Pierwsza rzecz do zrobienia to przydzielenie 2 kubitów zamiast jednego w operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="405d9-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="405d9-281">Pozwoli to dodać nową operację (`CNOT`) przed wykonaniem pomiaru (`M`) w operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="405d9-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="405d9-282">Dodaliśmy kolejną operację `Set`, aby zainicjować pierwszy kubit w celu zapewnienia, że jest zawsze w stanie `Zero` podczas uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="405d9-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="405d9-283">Musimy też zresetować drugi kubit przed jego zwolnieniem.</span><span class="sxs-lookup"><span data-stu-id="405d9-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="405d9-284">Pełna procedura wygląda teraz następująco:</span><span class="sxs-lookup"><span data-stu-id="405d9-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="405d9-285">Jeśli ją uruchomimy, uzyskamy dokładnie taki sam wynik 50%-50% jak poprzednio.</span><span class="sxs-lookup"><span data-stu-id="405d9-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="405d9-286">Jednak teraz interesuje nas, jak drugi kubit reaguje na pomiar pierwszego.</span><span class="sxs-lookup"><span data-stu-id="405d9-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="405d9-287">Dodamy tę statystykę do nowej wersji operacji `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="405d9-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

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
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="405d9-288">Nowa wartość zwracana (`agree`) śledzi przypadki, gdy pomiar pierwszego kubitu jest zgodny z pomiarem drugiego kubitu.</span><span class="sxs-lookup"><span data-stu-id="405d9-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="405d9-289">Należy także odpowiednio zaktualizować aplikację hosta:</span><span class="sxs-lookup"><span data-stu-id="405d9-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="405d9-290">Python</span><span class="sxs-lookup"><span data-stu-id="405d9-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[<span data-ttu-id="405d9-291">C#</span><span class="sxs-lookup"><span data-stu-id="405d9-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="405d9-292">Teraz po uruchomieniu otrzymujemy coś zdumiewającego:</span><span class="sxs-lookup"><span data-stu-id="405d9-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="405d9-293">Jak podano w omówieniu, nasze dane statystyczne dotyczące pierwszego kubitu nie uległy zmianie (szansa 50%-50% dla wartości 0 i 1), ale teraz pomiar drugiego kubitu jest __zawsze__ taki sam jak pierwszego kubitu, ponieważ są one splątane!</span><span class="sxs-lookup"><span data-stu-id="405d9-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="405d9-294">Gratulacje, udało Ci się napisać swój pierwszy program kwantowy!</span><span class="sxs-lookup"><span data-stu-id="405d9-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="whats-next"></a><span data-ttu-id="405d9-295">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="405d9-295">What's next?</span></span>

<span data-ttu-id="405d9-296">W przewodniku Szybki start [Wyszukiwanie Grovera](xref:microsoft.quantum.quickstarts.search) przedstawiono tworzenie i uruchamianie wyszukiwania Grovera — jednego z najpopularniejszych algorytmów obliczeń kwantowych — oraz podano ciekawy przykład programu języka Q#, którego można użyć do rozwiązywania rzeczywistych problemów obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="405d9-296">The QuickStart [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="405d9-297">Artykuł [Wprowadzenie do zestawu Quantum Development Kit](xref:microsoft.quantum.welcome) zawiera więcej zalecanych sposobów uczenia się języka Q# i programowania kwantowego.</span><span class="sxs-lookup"><span data-stu-id="405d9-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>

