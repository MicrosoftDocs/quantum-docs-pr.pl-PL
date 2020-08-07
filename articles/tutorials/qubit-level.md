---
title: Zapisuj i Symuluj programy qubit na poziomieQ#
description: Samouczek krok po kroku dotyczący pisania i symulowania programu Quantum, który działa na indywidualnym poziomie qubit
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 22c79e4e01db1a0d0c291d0dcff81dbfa8df5cd3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869719"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="0cefa-103">Samouczek: pisanie i symulowanie programów qubit na poziomie w funkcji Q\#</span><span class="sxs-lookup"><span data-stu-id="0cefa-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="0cefa-104">Witamy w samouczku zestawu Quantum Development Kit na temat pisania i symulowania podstawowego programu Quantum, który działa na poszczególnych qubitsach.</span><span class="sxs-lookup"><span data-stu-id="0cefa-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="0cefa-105">Mimo że Q# został utworzony przede wszystkim jako ogólny język programowania dla programów Quantum w dużej skali, można go łatwo wykorzystać do eksplorowania niższych poziomów programów Quantum: bezpośrednie adresowanie konkretnych qubits.</span><span class="sxs-lookup"><span data-stu-id="0cefa-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="0cefa-106">Elastyczność Q# umożliwia użytkownikom podejście do systemów Quantum z dowolnego takiego poziomu abstrakcji, a w tym samouczku szczegółowe się w qubits.</span><span class="sxs-lookup"><span data-stu-id="0cefa-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="0cefa-107">W odróżnieniu od wyciągu [transformacji Fouriera Quantum](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), podprocedury, która jest całką dla wielu większych algorytmów Quantum.</span><span class="sxs-lookup"><span data-stu-id="0cefa-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="0cefa-108">Należy zauważyć, że ten widok niskiego poziomu przetwarzania informacji Quantum jest często opisany w temacie "[obwody Quantum](xref:microsoft.quantum.concepts.circuits)", które reprezentują sekwencyjne stosowanie bram do określonych qubits systemu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="0cefa-109">W ten sposób sekwencyjne i wieloqubite operacje, które z kolei stosują się, można łatwo przedstawić na "diagramie obwodu".</span><span class="sxs-lookup"><span data-stu-id="0cefa-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="0cefa-110">W naszym przypadku zdefiniujemy Q# operację przeprowadzenia pełnej transformacji Fouriera qubit Quantum, która ma następującą reprezentację jako obwód:</span><span class="sxs-lookup"><span data-stu-id="0cefa-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="0cefa-111">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="0cefa-111">Prerequisites</span></span>

* <span data-ttu-id="0cefa-112">[Zainstaluj](xref:microsoft.quantum.install) zestaw Quantum Development Kit przy użyciu preferowanego języka i środowiska programistycznego.</span><span class="sxs-lookup"><span data-stu-id="0cefa-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="0cefa-113">Jeśli masz już zainstalowany zestaw QDK, upewnij się, że [zaktualizowano](xref:microsoft.quantum.update) go do najnowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="0cefa-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="0cefa-114">Z tego samouczka dowiesz się, jak wykonywać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="0cefa-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="0cefa-115">Zdefiniuj operacje Quantum wQ#</span><span class="sxs-lookup"><span data-stu-id="0cefa-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="0cefa-116">Wywoływanie Q# operacji bezpośrednio z wiersza polecenia lub przy użyciu klasycznego programu hosta</span><span class="sxs-lookup"><span data-stu-id="0cefa-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="0cefa-117">Symuluj operację Quantum z alokacji qubit do danych wyjściowych pomiaru</span><span class="sxs-lookup"><span data-stu-id="0cefa-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="0cefa-118">Obserwuj symulowane wavefunction systemu Quantum w całej operacji</span><span class="sxs-lookup"><span data-stu-id="0cefa-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="0cefa-119">Uruchamianie programu Quantum z zestawem Quantum Development Kit firmy Microsoft zwykle składa się z dwóch części:</span><span class="sxs-lookup"><span data-stu-id="0cefa-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="0cefa-120">Sam program, który jest implementowany przy użyciu Q# języka programowania Quantum, a następnie wywoływany do uruchamiania na komputerze Quantum lub symulatorze Quantum.</span><span class="sxs-lookup"><span data-stu-id="0cefa-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="0cefa-121">Składają się one z</span><span class="sxs-lookup"><span data-stu-id="0cefa-121">These consist of</span></span> 
    - <span data-ttu-id="0cefa-122">Q#operacje: procedury podrzędne działające w rejestrach Quantum i</span><span class="sxs-lookup"><span data-stu-id="0cefa-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="0cefa-123">Q#Functions: klasyczne procedury podrzędne używane w algorytmie Quantum.</span><span class="sxs-lookup"><span data-stu-id="0cefa-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="0cefa-124">Punkt wejścia służący do wywoływania programu Quantum i określania komputera docelowego, na którym ma być uruchamiany.</span><span class="sxs-lookup"><span data-stu-id="0cefa-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="0cefa-125">Można to zrobić bezpośrednio z wiersza polecenia lub za pośrednictwem programu hosta zapisaną w klasycznym języku programowania, takim jak Python lub C#.</span><span class="sxs-lookup"><span data-stu-id="0cefa-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="0cefa-126">Ten samouczek zawiera instrukcje dla dowolnej metody, której wolisz.</span><span class="sxs-lookup"><span data-stu-id="0cefa-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="0cefa-127">Alokuj qubits i Definiuj operacje Quantum</span><span class="sxs-lookup"><span data-stu-id="0cefa-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="0cefa-128">Pierwsza część tego samouczka składa się z definiowania Q# operacji `Perform3qubitQFT` , która wykonuje transformację Quantum Fouriera na trzech qubits.</span><span class="sxs-lookup"><span data-stu-id="0cefa-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="0cefa-129">Dodatkowo będziemy używać [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) funkcji, aby obserwować symulowane wavefunction naszych trzech systemów qubit w całej operacji.</span><span class="sxs-lookup"><span data-stu-id="0cefa-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="0cefa-130">Pierwszym krokiem jest utworzenie Q# projektu i pliku.</span><span class="sxs-lookup"><span data-stu-id="0cefa-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="0cefa-131">Te kroki zależą od środowiska, którego będziesz używać do wywoływania programu, i można znaleźć szczegółowe informacje w odpowiednich [przewodnikach instalacji](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="0cefa-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="0cefa-132">Przeprowadzimy Cię przez składniki tego pliku krok po kroku, ale kod jest również dostępny jako pełny blok poniżej.</span><span class="sxs-lookup"><span data-stu-id="0cefa-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-no-locq-operations"></a><span data-ttu-id="0cefa-133">Przestrzenie nazw umożliwiające dostęp do innych Q# operacji</span><span class="sxs-lookup"><span data-stu-id="0cefa-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="0cefa-134">Wewnątrz pliku najpierw definiujemy przestrzeń nazw, do `NamespaceQFT` której będą uzyskiwać dostęp kompilator.</span><span class="sxs-lookup"><span data-stu-id="0cefa-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="0cefa-135">W przypadku naszej operacji, aby korzystać z istniejących Q# operacji, otwieramy odpowiednie `Microsoft.Quantum.<>` przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="0cefa-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="0cefa-136">Zdefiniuj operacje z argumentami i zwraca</span><span class="sxs-lookup"><span data-stu-id="0cefa-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="0cefa-137">Następnie zdefiniujemy `Perform3qubitQFT` operację:</span><span class="sxs-lookup"><span data-stu-id="0cefa-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="0cefa-138">Na razie operacja nie przyjmuje żadnych argumentów i nie zwraca żadnych---w tym przypadku napisze, że zwraca `Unit` obiekt, który jest zbliżone `void` w języku C# lub w pustej kolekcji, `Tuple[()]` w Python.</span><span class="sxs-lookup"><span data-stu-id="0cefa-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="0cefa-139">Później zmodyfikujemy ją, aby zwracała tablicę wyników pomiarów, w której punkt `Unit` zostanie zastąpiony przez `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="0cefa-140">Alokuj qubits z`using`</span><span class="sxs-lookup"><span data-stu-id="0cefa-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="0cefa-141">W naszej Q# operacji najpierw przydzielmy rejestr trzech qubits z `using` instrukcją:</span><span class="sxs-lookup"><span data-stu-id="0cefa-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="0cefa-142">W programie `using` qubits są automatycznie przypisywane w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="0cefa-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="0cefa-143">Można to sprawdzić za pomocą [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) i [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , co spowoduje wydrukowanie ciągu i bieżącego stanu systemu w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="0cefa-144">`Message(<string>)`Funkcje i `DumpMachine()` ( [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) odpowiednio) są drukowane bezpośrednio w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="0cefa-145">Podobnie jak rzeczywiste Obliczanie Quantum, nie Q# pozwala nam na bezpośredni dostęp do Stanów qubit.</span><span class="sxs-lookup"><span data-stu-id="0cefa-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="0cefa-146">Jednak jako `DumpMachine` że program Drukuje bieżący stan maszyny docelowej, może zapewnić cenne informacje dotyczące debugowania i uczenia się, gdy jest używany w połączeniu z symulatorem pełnego stanu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="0cefa-147">Stosowanie bram o pojedynczej qubit i kontrolowanej</span><span class="sxs-lookup"><span data-stu-id="0cefa-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="0cefa-148">Następnie stosujemy bramy, które składają się na samą operację.</span><span class="sxs-lookup"><span data-stu-id="0cefa-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="0cefa-149">Q#zawiera już wiele podstawowych bram Quantum jako operacje w [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) przestrzeni nazw i nie są one wyjątkiem.</span><span class="sxs-lookup"><span data-stu-id="0cefa-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="0cefa-150">W ramach Q# operacji instrukcje wywoływania wywołania będą wykonywane w kolejności sekwencyjnej.</span><span class="sxs-lookup"><span data-stu-id="0cefa-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="0cefa-151">W związku z tym pierwsza brama do zastosowania to [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) do pierwszej qubit:</span><span class="sxs-lookup"><span data-stu-id="0cefa-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="0cefa-152">Aby zastosować operację do określonego qubit z rejestru (tj. pojedynczej `Qubit` z tablicy `Qubit[]` ), używamy standardowego zapisu indeksu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="0cefa-153">Dlatego zastosowanie [`H`](xref:microsoft.quantum.intrinsic.h) do pierwszej qubit naszego rejestru `qs` przyjmuje formę:</span><span class="sxs-lookup"><span data-stu-id="0cefa-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="0cefa-154">Oprócz zastosowania `H` bramy (Hadamard) do poszczególnych qubits obwód QFT składa się głównie z kontrolowanych [`R1`](xref:microsoft.quantum.intrinsic.r1) rotacji.</span><span class="sxs-lookup"><span data-stu-id="0cefa-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="0cefa-155">`R1(θ, <qubit>)`Operacja ogólnie pozostawia składnik $ \ket {0} $ niezmienionej qubit, podczas gdy stosowana jest rotacja $e ^ {i\theta} $ do składnika $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="0cefa-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="0cefa-156">Kontrolowane operacje</span><span class="sxs-lookup"><span data-stu-id="0cefa-156">Controlled operations</span></span>

<span data-ttu-id="0cefa-157">Q#sprawia, że nie jest to bardzo proste, aby było możliwe wykonywanie operacji na jednym lub wielu qubits kontroli.</span><span class="sxs-lookup"><span data-stu-id="0cefa-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="0cefa-158">Ogólnie rzecz biorąc, należy jedynie przeddzwonić wywołanie z `Controlled` , a argumenty operacji zmieniają się w taki sposób:</span><span class="sxs-lookup"><span data-stu-id="0cefa-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="0cefa-159">`Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="0cefa-160">Należy zauważyć, że kontrolka qubits musi być określona jako tablica, nawet jeśli jest to pojedynczy qubit.</span><span class="sxs-lookup"><span data-stu-id="0cefa-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="0cefa-161">Po dojściu do programu `H` zobaczymy, że następną bramą są `R1` bramy działające na pierwszej qubit (i kontrolowane przez drugą/trzeci):</span><span class="sxs-lookup"><span data-stu-id="0cefa-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="0cefa-162">Nazywamy je</span><span class="sxs-lookup"><span data-stu-id="0cefa-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="0cefa-163">Zwróć uwagę, że używamy [`PI()`](xref:microsoft.quantum.math.pi) funkcji z [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) przestrzeni nazw, aby zdefiniować rotacje w zakresie pi radianów.</span><span class="sxs-lookup"><span data-stu-id="0cefa-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="0cefa-164">Ponadto dzieli się na `Double` (np. `2.0` ), ponieważ podział przez liczbę całkowitą `2` spowoduje zgłoszenie błędu typu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="0cefa-165">`R1(π/2)`i `R1(π/4)` są równoważne `S` `T` operacje i (również w programie `Microsoft.Quantum.Intrinsic` ).</span><span class="sxs-lookup"><span data-stu-id="0cefa-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="0cefa-166">Po zastosowaniu odpowiednich `H` operacji i kontrolowanych rotacji do drugiego i trzeciego qubits:</span><span class="sxs-lookup"><span data-stu-id="0cefa-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="0cefa-167">potrzebujemy tylko [`SWAP`](xref:microsoft.quantum.intrinsic.swap) bramy do ukończenia obwodu:</span><span class="sxs-lookup"><span data-stu-id="0cefa-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="0cefa-168">Jest to konieczne, ponieważ charakter przekształcenia Quantum Fouriera wyprowadza qubits w odwrotnej kolejności, dzięki czemu zamiany umożliwiają bezproblemowe integrację procedury podrzędnej z większymi algorytmami.</span><span class="sxs-lookup"><span data-stu-id="0cefa-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="0cefa-169">W związku z tym zakończono zapisywanie operacji na poziomie qubiti transformacji Fouriera w ramach naszej Q# operacji:</span><span class="sxs-lookup"><span data-stu-id="0cefa-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="0cefa-170">Nie możemy jednak już wywoływać tego dnia.</span><span class="sxs-lookup"><span data-stu-id="0cefa-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="0cefa-171">Nasze qubits były w stanie $ \ket {0} $ po przydzieleniu ich przez nas, podobnie jak w życie, Q# należy pozostawić rzeczy w taki sam sposób, w jaki znaleźliśmy (lub lepiej).</span><span class="sxs-lookup"><span data-stu-id="0cefa-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="0cefa-172">Cofnij przydział qubits</span><span class="sxs-lookup"><span data-stu-id="0cefa-172">Deallocate qubits</span></span>

<span data-ttu-id="0cefa-173">Ponownie dzwonimy [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , aby zobaczyć stan po operacji, a wreszcie Zastosuj [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) do rejestru qubit, aby zresetować nasze qubits do $ \ket {0} $ przed ukończeniem operacji:</span><span class="sxs-lookup"><span data-stu-id="0cefa-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="0cefa-174">Wymaganie, aby wszystkie cofnięte alokacje qubits były jawnie ustawione na wartość $ \ket {0} $, to podstawowa funkcja systemu Q# , ponieważ umożliwia ona innym operacjom dokładniejsze poznanie ich stanu, gdy zaczynają korzystać z tych samych qubits (ograniczonych zasobów).</span><span class="sxs-lookup"><span data-stu-id="0cefa-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="0cefa-175">Ponadto gwarantuje to, że nie są one Entangled z jakimkolwiek innym qubits w systemie.</span><span class="sxs-lookup"><span data-stu-id="0cefa-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="0cefa-176">Jeśli reset nie zostanie wykonany na końcu `using` bloku alokacji, zostanie zgłoszony błąd czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="0cefa-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="0cefa-177">Pełny Q# plik powinien teraz wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="0cefa-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="0cefa-178">Gdy Q# plik i operacja zakończą pracę, nasz program Quantum jest gotowy do wywołania i symulowania.</span><span class="sxs-lookup"><span data-stu-id="0cefa-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="0cefa-179">Wykonywanie programu</span><span class="sxs-lookup"><span data-stu-id="0cefa-179">Execute the program</span></span>

<span data-ttu-id="0cefa-180">Po zdefiniowaniu naszej Q# operacji w `.qs` pliku musimy teraz wywołać tę operację i obserwować wszystkie zwrócone dane klasyczne.</span><span class="sxs-lookup"><span data-stu-id="0cefa-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="0cefa-181">Na razie nie ma niczego żadnego zwracanego (należy odwołać, że nasza operacja została zdefiniowana powyżej `Unit` ), ale w przypadku późniejszej modyfikacji Q# operacji w celu zwrócenia tablicy wyników pomiaru ( `Result[]` ) nastąpi przekierowanie.</span><span class="sxs-lookup"><span data-stu-id="0cefa-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="0cefa-182">Chociaż program jest powszechny w Q# środowiskach używanych do wywoływania go, sposób postępowania w ten sposób będzie różny.</span><span class="sxs-lookup"><span data-stu-id="0cefa-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="0cefa-183">W związku z tym po prostu postępuj zgodnie z instrukcjami wyświetlanymi na karcie odpowiadającej Twoim Instalatorowi: Praca z poziomu Q# aplikacji wiersza polecenia lub programu hosta w języku Python lub C#.</span><span class="sxs-lookup"><span data-stu-id="0cefa-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="0cefa-184">Wiersz polecenia</span><span class="sxs-lookup"><span data-stu-id="0cefa-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="0cefa-185">Uruchomienie Q# programu z wiersza polecenia wymaga jedynie niewielkiej zmiany Q# pliku.</span><span class="sxs-lookup"><span data-stu-id="0cefa-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="0cefa-186">Po prostu Dodaj `@EntryPoint()` do wiersza poprzedzającego definicję operacji:</span><span class="sxs-lookup"><span data-stu-id="0cefa-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="0cefa-187">Aby uruchomić program, Otwórz terminal w folderze projektu i wprowadź</span><span class="sxs-lookup"><span data-stu-id="0cefa-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="0cefa-188">Po wykonaniu tych czynności powinny zostać `Message` wyświetlone `DumpMachine` poniższe dane wyjściowe w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="0cefa-189">Python</span><span class="sxs-lookup"><span data-stu-id="0cefa-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="0cefa-190">Utwórz plik hosta języka Python: `host.py` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="0cefa-191">Plik hosta został skonstruowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="0cefa-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="0cefa-192">Najpierw należy zaimportować `qsharp` moduł, który rejestruje moduł ładujący modułu pod kątem Q# współdziałania.</span><span class="sxs-lookup"><span data-stu-id="0cefa-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="0cefa-193">Dzięki temu Q# obszary nazw (np. `NamespaceQFT` zdefiniowane w naszym Q# pliku) są wyświetlane jako moduły języka Python, z których można importować Q# operacje.</span><span class="sxs-lookup"><span data-stu-id="0cefa-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="0cefa-194">Następnie należy zaimportować Q# operacje, które zostaną bezpośrednio wywołane---w tym przypadku `Perform3qubitQFT` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="0cefa-195">Potrzebujemy tylko zaimportować punkt wejścia do Q# programu (tj. _nie_ operacje takie jak `H` i `R1` , które są wywoływane przez inne operacje, Q# ale nigdy nie przez klasycznego hosta).</span><span class="sxs-lookup"><span data-stu-id="0cefa-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="0cefa-196">W przypadku symulowania Q# operacji lub funkcji Użyj formularza, `<Q#callable>.simulate(<args>)` Aby uruchomić je na `QuantumSimulator()` komputerze docelowym.</span><span class="sxs-lookup"><span data-stu-id="0cefa-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="0cefa-197">Jeśli chcemy wywołać operację na innym komputerze, na przykład `ResourceEstimator()` po prostu użyjemy `<Q#callable>.estimate_resources(<args>)` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="0cefa-198">Ogólnie rzecz biorąc, Q# operacje są niezależny od na maszynach, na których są uruchamiane, ale niektóre funkcje, takie jak `DumpMachine` mogą zachowywać się inaczej.</span><span class="sxs-lookup"><span data-stu-id="0cefa-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="0cefa-199">Podczas wykonywania symulacji wywołanie operacji zwróci wartości zgodnie z definicją w Q# pliku.</span><span class="sxs-lookup"><span data-stu-id="0cefa-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="0cefa-200">Obecnie nie ma żadnych zwróconych elementów, ale w dalszej części zobaczymy przykład przypisywania i przetwarzania tych wartości.</span><span class="sxs-lookup"><span data-stu-id="0cefa-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="0cefa-201">Dzięki wykorzystaniu danych z naszych rąk i całkowicie klasycznym, możemy zrobić to niezależnie od tego, co chcemy.</span><span class="sxs-lookup"><span data-stu-id="0cefa-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="0cefa-202">Pełny `host.py` plik powinien być następujący:</span><span class="sxs-lookup"><span data-stu-id="0cefa-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="0cefa-203">Uruchom plik języka Python i wydrukowanie w konsoli powinny być widoczne poniższe dane `Message` `DumpMachine` wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="0cefa-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="0cefa-204">C#</span><span class="sxs-lookup"><span data-stu-id="0cefa-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="0cefa-205">Postępując zgodnie z tymi samymi instrukcjami w [przewodniku instalacji](xref:microsoft.quantum.install.cs), Utwórz plik hosta C# i zmień jego nazwę na `host.cs` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="0cefa-206">Host języka C# ma cztery części:</span><span class="sxs-lookup"><span data-stu-id="0cefa-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="0cefa-207">Konstruuje symulator kwantowy.</span><span class="sxs-lookup"><span data-stu-id="0cefa-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="0cefa-208">W poniższym kodzie jest to zmienna `qsim` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="0cefa-209">Oblicza wszystkie argumenty wymagane dla algorytmu kwantowego.</span><span class="sxs-lookup"><span data-stu-id="0cefa-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="0cefa-210">Brak w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0cefa-210">There are none in this example.</span></span>
3. <span data-ttu-id="0cefa-211">Uruchamia algorytm kwantowy.</span><span class="sxs-lookup"><span data-stu-id="0cefa-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="0cefa-212">Każda Q# Operacja generuje klasę języka C# o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="0cefa-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="0cefa-213">Ta klasa ma metodę `Run`, która **asynchronicznie** wykonuje operację.</span><span class="sxs-lookup"><span data-stu-id="0cefa-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="0cefa-214">Wykonanie jest asynchroniczne, ponieważ wykonanie na rzeczywistym sprzęcie będzie asynchroniczne.</span><span class="sxs-lookup"><span data-stu-id="0cefa-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="0cefa-215">Ponieważ `Run` Metoda jest asynchroniczna, wywoływana jest `Wait()` Metoda; ta funkcja blokuje wykonywanie do momentu zakończenia zadania i zwraca wynik synchronicznie.</span><span class="sxs-lookup"><span data-stu-id="0cefa-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="0cefa-216">Przetwarza zwrócony wynik operacji.</span><span class="sxs-lookup"><span data-stu-id="0cefa-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="0cefa-217">Na razie operacja nie zwraca żadnej wartości.</span><span class="sxs-lookup"><span data-stu-id="0cefa-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="0cefa-218">Uruchom aplikację, a dane wyjściowe powinny być zgodne z poniższymi.</span><span class="sxs-lookup"><span data-stu-id="0cefa-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="0cefa-219">Program zostanie zakończony po naciśnięciu klawisza.</span><span class="sxs-lookup"><span data-stu-id="0cefa-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="0cefa-220">Gdy jest wywoływana w symulatorze pełnego stanu, program `DumpMachine()` udostępnia te mutliple reprezentacje wavefunction stanu Quantum.</span><span class="sxs-lookup"><span data-stu-id="0cefa-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="0cefa-221">Możliwe stany $ngo systemu $-qubit mogą być reprezentowane przez $2 ^ n $ Stany obliczeniowe, z których każdy ma odpowiedni współczynnik złożony (po prostu amplituda i faza).</span><span class="sxs-lookup"><span data-stu-id="0cefa-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="0cefa-222">Podstawowe Stany są zgodne ze wszystkimi możliwymi binarnymi ciągami o długości $n $---, czyli wszystkie możliwe kombinacje qubit Stanów $ \ket {0} $ i $ \ket {1} $, gdzie każda cyfra binarna odnosi się do poszczególnych qubit.</span><span class="sxs-lookup"><span data-stu-id="0cefa-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="0cefa-223">Pierwszy wiersz zawiera komentarz z identyfikatorami odpowiednich qubits w ich znaczącej kolejności.</span><span class="sxs-lookup"><span data-stu-id="0cefa-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="0cefa-224">Qubit `2` "najbardziej znaczący" oznacza, że w binarnej reprezentacji wektora stanu podstawy $ \ket{i} $ stan qubit `2` odpowiada cyfrom z lewej strony.</span><span class="sxs-lookup"><span data-stu-id="0cefa-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="0cefa-225">Na przykład $ \ket {6} = \ket {110} $ składa się qubits `2` i `1` oba w $ \ket {1} $ i qubit `0` w $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="0cefa-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="0cefa-226">Pozostała część wierszy zawiera opis amplitudy prawdopodobieństwa pomiaru wektora stanu \ket{i} $ w obu formatach kartezjańskiego i biegunowych.</span><span class="sxs-lookup"><span data-stu-id="0cefa-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="0cefa-227">Szczegółowo dla pierwszego wiersza naszego stanu danych wejściowych $ \ket {000} $:</span><span class="sxs-lookup"><span data-stu-id="0cefa-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="0cefa-228">**`|0>:`** Ten wiersz odnosi się do `0` stanu podstawowego obliczenia (w związku z tym, że nasza początkowa alokacja stanu początkowego to $ \ket {000} $, oczekujemy, że będzie to jedyny stan z amplitudą prawdopodobieństwa w tym punkcie).</span><span class="sxs-lookup"><span data-stu-id="0cefa-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="0cefa-229">**`1.000000 +  0.000000 i`**: amplituda prawdopodobieństwa w formacie kartezjańskiego.</span><span class="sxs-lookup"><span data-stu-id="0cefa-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="0cefa-230">**` == `**: `equal` znak oddziela obie równoważne reprezentacje.</span><span class="sxs-lookup"><span data-stu-id="0cefa-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="0cefa-231">**`********************`**: Graficzna reprezentacja rozmiaru, liczba `*` jest proporcjonalna do prawdopodobieństwa mierzenia tego wektora stanu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="0cefa-232">**`[ 1.000000 ]`**: wartość liczbowa wielkości</span><span class="sxs-lookup"><span data-stu-id="0cefa-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="0cefa-233">**`    ---`**: Graficzna reprezentacja fazy amplitudy.</span><span class="sxs-lookup"><span data-stu-id="0cefa-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="0cefa-234">**`[ 0.0000 rad ]`**: wartość liczbowa fazy (w radianach).</span><span class="sxs-lookup"><span data-stu-id="0cefa-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="0cefa-235">Obie wartości i fazy są wyświetlane ze graficzną reprezentacją.</span><span class="sxs-lookup"><span data-stu-id="0cefa-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="0cefa-236">Reprezentacja wielkości jest prosta: pokazuje pasek `*` , a im wyższe prawdopodobieństwo, tym większy jest pasek.</span><span class="sxs-lookup"><span data-stu-id="0cefa-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="0cefa-237">W przypadku fazy należy zapoznać się z tematem [testowanie i debugowanie: funkcje zrzutu](xref:microsoft.quantum.guide.testingdebugging#dump-functions) dla możliwych reprezentacji symboli w oparciu o zakresy kątów.</span><span class="sxs-lookup"><span data-stu-id="0cefa-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="0cefa-238">W wyniku tego drukowane dane wyjściowe pokazują, że nasze bramy zaprogramowane są przekształcone w nasz stan z</span><span class="sxs-lookup"><span data-stu-id="0cefa-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="0cefa-239">$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="0cefa-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="0cefa-240">na</span><span class="sxs-lookup"><span data-stu-id="0cefa-240">to</span></span> 

<span data-ttu-id="0cefa-241">$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="0cefa-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="0cefa-242">Co to jest dokładne zachowanie transformacji Fouriera 3-qubit.</span><span class="sxs-lookup"><span data-stu-id="0cefa-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="0cefa-243">Jeśli chcesz wiedzieć się na to, w jaki sposób mają wpływ inne Stany wejścia, zachęcamy do rozwinięcia z zastosowaniem operacji qubit przed przekształceniem.</span><span class="sxs-lookup"><span data-stu-id="0cefa-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="0cefa-244">Dodawanie pomiarów</span><span class="sxs-lookup"><span data-stu-id="0cefa-244">Adding measurements</span></span>

<span data-ttu-id="0cefa-245">Niestety, kamień Quantum Mechanics informuje nas, że prawdziwy system Quantum nie może mieć takiej `DumpMachine` funkcji.</span><span class="sxs-lookup"><span data-stu-id="0cefa-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="0cefa-246">Zamiast tego należy wymusić Wyodrębnienie informacji poprzez pomiary, które generalnie nie tylko kończą się niepowodzeniem, aby zapewnić nam pełny stan Quantum, ale może też znacząco zmienić sam system.</span><span class="sxs-lookup"><span data-stu-id="0cefa-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="0cefa-247">Istnieje wiele różnych pomiarów jednostek Quantum, ale będziemy skupić się na najważniejszych pomiarach na jednym qubits.</span><span class="sxs-lookup"><span data-stu-id="0cefa-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="0cefa-248">W przypadku pomiaru w danej lokalizacji (np. obliczenia obliczanej na podstawie $ \{ \ket {0} , \ket {1} \} $) stan qubit jest przewidywany w zależności od stanu,---w związku z tym zniszczenia wszystkich nadmiaru między nimi.</span><span class="sxs-lookup"><span data-stu-id="0cefa-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="0cefa-249">Aby zaimplementować pomiary w ramach Q# programu, używamy `M` operacji (from `Microsoft.Quantum.Intrinsic` ), która zwraca `Result` Typ.</span><span class="sxs-lookup"><span data-stu-id="0cefa-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="0cefa-250">Najpierw zmodyfikujemy naszą `Perform3QubitQFT` operację, aby zwrócić tablicę wyników pomiarów, `Result[]` zamiast `Unit` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="0cefa-251">Zdefiniuj i zainicjuj `Result[]` tablicę</span><span class="sxs-lookup"><span data-stu-id="0cefa-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="0cefa-252">Przed przystąpieniem do przydzielenia qubits (tj. przed `using` instrukcją) deklarujemy i powiążemy tę tablicę o długości-3 (jedną `Result` dla każdej qubit):</span><span class="sxs-lookup"><span data-stu-id="0cefa-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="0cefa-253">Słowo kluczowe "wychodzące" `mutable` `resultArray` pozwala na przykład, aby zmienna była ponownie powiązana w---kodu, podczas dodawania wyników pomiarów.</span><span class="sxs-lookup"><span data-stu-id="0cefa-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="0cefa-254">Wykonaj pomiary w `for` pętli i Dodaj wyniki do tablicy</span><span class="sxs-lookup"><span data-stu-id="0cefa-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="0cefa-255">Po wykonaniu operacji transformacji Fouriera wewnątrz `using` bloku Wstaw następujący kod:</span><span class="sxs-lookup"><span data-stu-id="0cefa-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="0cefa-256">[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)Funkcja wywołana na tablicy (np. Nasza Tablica elementów qubits `qs` ) zwraca zakres przez indeksy tablicy.</span><span class="sxs-lookup"><span data-stu-id="0cefa-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="0cefa-257">W tym miejscu używamy jej w `for` pętli do sekwencyjnego mierzenia poszczególnych qubit przy użyciu `M(qs[i])` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="0cefa-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="0cefa-258">Każdy `Result` Typ mierzony (albo `Zero` `One` ) jest następnie dodawany do odpowiedniej pozycji indeksu w `resultArray` instrukcji Update-and-Reassign.</span><span class="sxs-lookup"><span data-stu-id="0cefa-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="0cefa-259">Składnia tej instrukcji jest unikatowa dla Q# , ale odpowiada podobnej zmiennej ponownemu przypisaniu, która jest `resultArray[i] <- M(qs[i])` widoczna w innych językach, takich jak F # i R.</span><span class="sxs-lookup"><span data-stu-id="0cefa-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="0cefa-260">Słowo kluczowe `set` jest zawsze używane do ponownego przypisania zmiennych powiązanych przy użyciu `mutable` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="0cefa-261">Przesłać`resultArray`</span><span class="sxs-lookup"><span data-stu-id="0cefa-261">Return `resultArray`</span></span>

<span data-ttu-id="0cefa-262">Ze względu na wszystkie trzy qubits i wyniki dodane do `resultArray` , firma Microsoft bezpiecznie resetuje i cofa alokację qubits.</span><span class="sxs-lookup"><span data-stu-id="0cefa-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="0cefa-263">Po `using` zamknięciu bloku Wstaw</span><span class="sxs-lookup"><span data-stu-id="0cefa-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="0cefa-264">Aby ostatecznie zwrócić dane wyjściowe naszej operacji.</span><span class="sxs-lookup"><span data-stu-id="0cefa-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="0cefa-265">Zrozumienie efektów pomiaru</span><span class="sxs-lookup"><span data-stu-id="0cefa-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="0cefa-266">Zmieńmy położenie naszych `DumpMachine` funkcji w celu wygenerowania stanu przed pomiarami i po nich.</span><span class="sxs-lookup"><span data-stu-id="0cefa-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="0cefa-267">Kod operacji końcowej powinien wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="0cefa-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="0cefa-268">Jeśli pracujesz z wiersza polecenia, zwracana tablica zostanie po prostu wydrukowana bezpośrednio do konsoli na końcu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="0cefa-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="0cefa-269">W przeciwnym razie zaktualizuj program hosta, aby przetworzyć zwróconą tablicę.</span><span class="sxs-lookup"><span data-stu-id="0cefa-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="0cefa-270">Wiersz polecenia</span><span class="sxs-lookup"><span data-stu-id="0cefa-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="0cefa-271">Aby lepiej zrozumieć zwracaną tablicę, która zostanie wydrukowana w konsoli programu, można dodać kolejną `Message` Q# plik w pliku tuż przed `return` instrukcją:</span><span class="sxs-lookup"><span data-stu-id="0cefa-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="0cefa-272">Uruchom projekt, a dane wyjściowe powinny wyglądać podobnie do następujących:</span><span class="sxs-lookup"><span data-stu-id="0cefa-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="0cefa-273">Python</span><span class="sxs-lookup"><span data-stu-id="0cefa-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="0cefa-274">Zaktualizuj program Python do poniższego:</span><span class="sxs-lookup"><span data-stu-id="0cefa-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="0cefa-275">Uruchom plik, a dane wyjściowe powinny wyglądać podobnie do następujących:</span><span class="sxs-lookup"><span data-stu-id="0cefa-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="0cefa-276">C#</span><span class="sxs-lookup"><span data-stu-id="0cefa-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="0cefa-277">Teraz, gdy nasza operacja zwraca wynik, Zastąp wywołanie metody `Wait()` pobraniem `Result` właściwości.</span><span class="sxs-lookup"><span data-stu-id="0cefa-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="0cefa-278">Nadal wykonuje to samo Synchronicity omówione wcześniej i można bezpośrednio powiązać tę wartość ze zmienną `measurementResult` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="0cefa-279">Uruchom projekt, a dane wyjściowe powinny wyglądać podobnie do następujących:</span><span class="sxs-lookup"><span data-stu-id="0cefa-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="0cefa-280">To wyjście ilustruje kilka różnych rzeczy:</span><span class="sxs-lookup"><span data-stu-id="0cefa-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="0cefa-281">Porównanie zwróconego wyniku do wstępnego pomiaru `DumpMachine` nie oznacza, że _nie_ zilustrowano w nim położeniu QFT.</span><span class="sxs-lookup"><span data-stu-id="0cefa-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="0cefa-282">Pomiar zwraca tylko jeden stan podstawy, z prawdopodobieństwem określonym przez amplitudę tego stanu w wavefunction systemu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="0cefa-283">Na podstawie miary po pomiarach `DumpMachine` zobaczymy, że pomiar _zmienia_ sam stan, umieszczając go od początkowego nadpozycji względem stanów w pojedynczym stanie, który odnosi się do zmierzonej wartości.</span><span class="sxs-lookup"><span data-stu-id="0cefa-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="0cefa-284">Jeśli udało nam się powtórzyć tę operację wiele razy, zobaczymy statystyki wynikowe, aby zilustrować równomiernie ważoną w stanie QFT, który umożliwia uzyskanie losowego wyniku dla każdego zrzutu.</span><span class="sxs-lookup"><span data-stu-id="0cefa-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="0cefa-285">_Jednak_oprócz są niewydajne i nadal nieidealne, może to jednak jedynie odtworzyć względne amplitudy Stanów bazowych, a nie względne fazy między nimi.</span><span class="sxs-lookup"><span data-stu-id="0cefa-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="0cefa-286">Ten ostatni nie jest problemem w tym przykładzie, ale zobaczysz względne fazy, jeśli podano bardziej złożone dane wejściowe QFT niż $ \ket {000} $.</span><span class="sxs-lookup"><span data-stu-id="0cefa-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="0cefa-287">Pomiary częściowe</span><span class="sxs-lookup"><span data-stu-id="0cefa-287">Partial measurements</span></span> 
<span data-ttu-id="0cefa-288">Aby dowiedzieć się, jak pomiary tylko niektóre qubits rejestru mogą mieć wpływ na stan systemu, spróbuj dodać następujące elementy wewnątrz `for` pętli, po linii pomiaru:</span><span class="sxs-lookup"><span data-stu-id="0cefa-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="0cefa-289">Należy pamiętać, że w celu uzyskania dostępu do `IntAsString` funkcji należy dodać</span><span class="sxs-lookup"><span data-stu-id="0cefa-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="0cefa-290">z resztą instrukcji przestrzeni nazw `open` .</span><span class="sxs-lookup"><span data-stu-id="0cefa-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="0cefa-291">W wynikowym wyjściu zobaczysz stopniowe rzutowanie do podobszarów w miarę mierzenia qubit.</span><span class="sxs-lookup"><span data-stu-id="0cefa-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-no-locq-libraries"></a><span data-ttu-id="0cefa-292">Korzystanie z Q# bibliotek</span><span class="sxs-lookup"><span data-stu-id="0cefa-292">Use the Q# libraries</span></span>
<span data-ttu-id="0cefa-293">Jak wspomniano w wprowadzeniu, większość Q# siły mocy w tym fakcie pozwala na streszczenie martw z poszczególnymi qubitsami.</span><span class="sxs-lookup"><span data-stu-id="0cefa-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="0cefa-294">W rzeczywistości, jeśli chcesz opracowywać kompletne, odpowiednie programy Quantum, martw się o to, czy `H` operacja przejdzie przed lub po określonej rotacji, spowoduje spowolnienie pracy.</span><span class="sxs-lookup"><span data-stu-id="0cefa-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="0cefa-295">Q#Biblioteki programu zawierają operację [QFT](xref:microsoft.quantum.canon.qft) , którą można po prostu wykonać i zastosować do dowolnej liczby qubits.</span><span class="sxs-lookup"><span data-stu-id="0cefa-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="0cefa-296">Aby wypróbować ten element, zdefiniuj nową operację w Q# pliku, która ma tę samą zawartość `Perform3QubitQFT` , ale z wszystko od pierwszego `H` do `SWAP` zastąpione przez dwie proste linie:</span><span class="sxs-lookup"><span data-stu-id="0cefa-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="0cefa-297">Pierwszy wiersz po prostu tworzy [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) wyrażenie przydzieloną tablicę qubits, czyli to `qs` , co operacja [QFT](xref:microsoft.quantum.canon.qft) jest wykonywana jako argument.</span><span class="sxs-lookup"><span data-stu-id="0cefa-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="0cefa-298">Odnosi się to do kolejności indeksu qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="0cefa-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="0cefa-299">Aby mieć dostęp do tych operacji, należy dodać `open` instrukcje dla odpowiednich przestrzeni nazw na początku Q# pliku:</span><span class="sxs-lookup"><span data-stu-id="0cefa-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="0cefa-300">Teraz Dostosuj program hosta, aby wywoływać nazwę nowej operacji (np. `PerformIntrinsicQFT` ) i nadaj jej Whirl.</span><span class="sxs-lookup"><span data-stu-id="0cefa-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="0cefa-301">Aby zobaczyć prawdziwą korzyść z używania Q# operacji biblioteki, Zmień liczbę qubits na coś innego niż `3` :</span><span class="sxs-lookup"><span data-stu-id="0cefa-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="0cefa-302">Z tego względu można zastosować odpowiednie QFT dla dowolnej liczby qubits, bez konieczności zajmowania się komunikatami o wykorzystaniu nowych `H` operacji i obrotów na każdym qubit.</span><span class="sxs-lookup"><span data-stu-id="0cefa-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="0cefa-303">Należy pamiętać, że symulator usługi Quantum trwa wykładniczo więcej czasu, gdy zwiększasz liczbę qubits---dokładniej, dlaczego przejdziemy do prawdziwego sprzętu Quantum.</span><span class="sxs-lookup"><span data-stu-id="0cefa-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













