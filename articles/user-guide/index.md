---
title: Podręcznik użytkownika języka Q#
description: Omówienie przeznaczenia i zawartości podręcznika użytkownika
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: c5611f3e2907791f2dfc1644be0a45515d50dfd7
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415372"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="8bbac-103">Podręcznik użytkownika języka Q#</span><span class="sxs-lookup"><span data-stu-id="8bbac-103">The Q# User Guide</span></span>

<span data-ttu-id="8bbac-104">Podręcznik użytkownika języka Q# — Zapraszamy!</span><span class="sxs-lookup"><span data-stu-id="8bbac-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="8bbac-105">W poszczególnych tematach tego przewodnika opisano szczegółowo podstawowe pojęcia dotyczące języka Q# oraz wszystkie informacje potrzebne do pisania programów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="8bbac-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="8bbac-106">Zawartość podręcznika użytkownika</span><span class="sxs-lookup"><span data-stu-id="8bbac-106">User Guide Contents</span></span>

- <span data-ttu-id="8bbac-107">[Podstawy języka Q#](xref:microsoft.quantum.guide.basics): Wprowadzające omówienie dotyczące przeznaczenia i funkcjonalności języka programowania Q#.</span><span class="sxs-lookup"><span data-stu-id="8bbac-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="8bbac-108">Język Q#</span><span class="sxs-lookup"><span data-stu-id="8bbac-108">Q# Language</span></span>

- <span data-ttu-id="8bbac-109">[Typy w języku Q#](xref:microsoft.quantum.guide.types): Opis modelu typów języka Q# oraz składni służącej do określania typów i pracy z nimi.</span><span class="sxs-lookup"><span data-stu-id="8bbac-109">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="8bbac-110">[Wyrażenia typów](xref:microsoft.quantum.guide.expressions): Szczegóły dotyczące określania, odwoływania się, łączenia i wykonywania operacji w przypadku wartości poszczególnych typów w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="8bbac-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="8bbac-111">Korzystanie z języka Q#</span><span class="sxs-lookup"><span data-stu-id="8bbac-111">Using Q#</span></span>

- <span data-ttu-id="8bbac-112">[Struktura plików języka Q#](xref:microsoft.quantum.guide.filestructure): Opis struktury i składni pliku języka Q# `*.qs`.</span><span class="sxs-lookup"><span data-stu-id="8bbac-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="8bbac-113">[Operacje i funkcje](xref:microsoft.quantum.guide.operationsfunctions): Szczegóły dwóch wywoływalnych typów w języku Q#: *operacji*, które obejmują akcje dotyczące rejestrów kubitów, oraz *funkcji*, które współpracują wyłącznie z informacjami klasycznymi.</span><span class="sxs-lookup"><span data-stu-id="8bbac-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="8bbac-114">W tym miejscu opisano, jak je definiować i wywoływać, łącznie ze sprzężonymi i kontrolowanymi wersjami operacji kwantowych.</span><span class="sxs-lookup"><span data-stu-id="8bbac-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="8bbac-115">[Zmienne](xref:microsoft.quantum.guide.variables): Opis roli zmiennych w programach języka Q# oraz sposobu ich skutecznego używania.</span><span class="sxs-lookup"><span data-stu-id="8bbac-115">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="8bbac-116">Na przykład dostępne są informacje o zakresach powiązań, różnicach między zmiennymi, których nie można modyfikować, i tymi, które można modyfikować, a także o sposobie ich przypisywania i ponownego przypisywania.</span><span class="sxs-lookup"><span data-stu-id="8bbac-116">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="8bbac-117">[Praca z kubitami](xref:microsoft.quantum.guide.qubits): Opis funkcji języka Q# używanych do adresowania poszczególnych kubitów i systemów kubitów, w szczególności do alokowania ich, wykonywania operacji na nich i mierzenia ich.</span><span class="sxs-lookup"><span data-stu-id="8bbac-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="8bbac-118">[Przepływ sterowania](xref:microsoft.quantum.guide.controlflow): Szczegóły programowania wzorców przepływu sterowania dostępnych w języku Q#, które obejmują wiele standardowych technik (wykonywanie warunkowe, pętle for, pętle while itp.), a także wzorzec specyficzny dla programów kwantowych „Repeat-Until-Success”.</span><span class="sxs-lookup"><span data-stu-id="8bbac-118">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional execution, for loops, while loops) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="8bbac-119">[Testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging): Szczegóły niektórych technik służących do upewniania się, że kod działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="8bbac-119">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="8bbac-120">Ze względu na ogólną nieprzezroczystość informacji kwantowych debugowanie programu kwantowego może wymagać wyspecjalizowanych technik.</span><span class="sxs-lookup"><span data-stu-id="8bbac-120">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="8bbac-121">Na szczęście język Q# obsługuje wiele klasycznych technik debugowania, które są znane programistom, a także tych, które są specyficzne dla programów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="8bbac-121">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="8bbac-122">Obejmuje to tworzenie i uruchamianie testów jednostkowych w języku Q#, osadzanie *asercji* dotyczących wartości i prawdopodobieństwa w kodzie oraz funkcje `Dump`, które wyprowadzają stan maszyn docelowych.</span><span class="sxs-lookup"><span data-stu-id="8bbac-122">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="8bbac-123">Tych ostatnich funkcji można używać wraz z naszym symulatorem pełnego stanu do debugowania niektórych części obliczeń przez ominięcie pewnych ograniczeń kwantowych (np. [twierdzenia o braku klonowania](xref:microsoft.quantum.concepts.pauli)).</span><span class="sxs-lookup"><span data-stu-id="8bbac-123">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="8bbac-124">Symulatory kwantowe i narzędzia do szacowania zasobów</span><span class="sxs-lookup"><span data-stu-id="8bbac-124">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="8bbac-125">[Symulatory kwantowe i aplikacje hosta](xref:microsoft.quantum.machines): Omówienie różnych dostępnych symulatorów oraz ogólnego modelu wykonywania między programami hosta a maszynami docelowymi.</span><span class="sxs-lookup"><span data-stu-id="8bbac-125">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well as the general execution model between host programs and target machines.</span></span>

- <span data-ttu-id="8bbac-126">[Symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator): Maszyna docelowa, która symuluje pełny stan kwantowy.</span><span class="sxs-lookup"><span data-stu-id="8bbac-126">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="8bbac-127">Przydatne do pełnego uruchomienia lub debugowania programów o mniejszej skali (mniej niż kilkadziesiąt kubitów)</span><span class="sxs-lookup"><span data-stu-id="8bbac-127">Useful for fully executing or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="8bbac-128">[Narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator): Szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji w języku Q# na komputerze kwantowym.</span><span class="sxs-lookup"><span data-stu-id="8bbac-128">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="8bbac-129">[Symulator śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Umożliwia wykonywanie programu kwantowego bez faktycznego symulowania stanu komputera kwantowego i w związku z tym może wykonywać programy kwantowe korzystające z tysięcy kubitów.</span><span class="sxs-lookup"><span data-stu-id="8bbac-129">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="8bbac-130">Przydatne do debugowania kodu klasycznego w ramach programu kwantowego, a także do oszacowania wymaganych zasobów.</span><span class="sxs-lookup"><span data-stu-id="8bbac-130">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="8bbac-131">[Symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): Symulator kwantowy specjalnego przeznaczenia, który może być używany z milionami kubitów, ale tylko w przypadku programów z ograniczonym zestawem operacji kwantowych (X, CNOT i kontrolowanych wielokrotnie operacji X).</span><span class="sxs-lookup"><span data-stu-id="8bbac-131">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="8bbac-132">Strony skróconej dokumentacji</span><span class="sxs-lookup"><span data-stu-id="8bbac-132">Quick Reference Pages</span></span>

- <span data-ttu-id="8bbac-133">[Polecenia magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Strona skróconej dokumentacji dla poleceń magic IQ# w ramach notesów Jupyter dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="8bbac-133">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
