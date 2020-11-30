---
title: Podręcznik użytkownika języka Q#
description: Omówienie przeznaczenia i zawartości podręcznika użytkownika
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231761"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="58dbe-103">Podręcznik użytkownika języka Q#</span><span class="sxs-lookup"><span data-stu-id="58dbe-103">The Q# User Guide</span></span>

<span data-ttu-id="58dbe-104">Podręcznik użytkownika języka Q# — Zapraszamy!</span><span class="sxs-lookup"><span data-stu-id="58dbe-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="58dbe-105">W różnych tematach tego przewodnika wprowadzamy podstawowe informacje na temat tworzenia programów kwantowych za pomocą języka Q#.</span><span class="sxs-lookup"><span data-stu-id="58dbe-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="58dbe-106">Odwołujemy się do [podręcznika języka Q#](xref:microsoft.quantum.qsharp.index), który zawiera pełną specyfikację i dokumentację kwantowego języka programowania Q#.</span><span class="sxs-lookup"><span data-stu-id="58dbe-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="58dbe-107">Zawartość podręcznika użytkownika</span><span class="sxs-lookup"><span data-stu-id="58dbe-107">User Guide Contents</span></span>

- <span data-ttu-id="58dbe-108">[Programy w języku Q#](xref:microsoft.quantum.guide.programs): Krótkie wprowadzenie do programów kwantowych w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="58dbe-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="58dbe-109">[Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs): Zawiera opis sposobu uruchamiania programu w języku Q# i udostępnia przegląd różnych metod wywoływania programu: z wiersza polecenia, w notesach Jupyter Notebook języka Q# lub z klasycznego programu hosta napisanego w języku Python lub języku platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="58dbe-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="58dbe-110">[Testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging): Szczegóły niektórych technik służących do upewniania się, że kod działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="58dbe-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="58dbe-111">Ze względu na ogólną nieprzezroczystość informacji kwantowych debugowanie programu kwantowego może wymagać wyspecjalizowanych technik.</span><span class="sxs-lookup"><span data-stu-id="58dbe-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="58dbe-112">Na szczęście język Q# obsługuje wiele klasycznych technik debugowania, które są znane programistom, a także tych, które są specyficzne dla programów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="58dbe-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="58dbe-113">Obejmuje to tworzenie i uruchamianie testów jednostkowych w języku Q#, osadzanie *asercji* dotyczących wartości i prawdopodobieństwa w kodzie oraz funkcje `Dump`, które wyprowadzają stany maszyn docelowych.</span><span class="sxs-lookup"><span data-stu-id="58dbe-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="58dbe-114">Tych ostatnich funkcji można używać wraz z naszym symulatorem pełnego stanu do debugowania niektórych części obliczeń przez ominięcie pewnych ograniczeń kwantowych (np. [twierdzenia o braku klonowania](xref:microsoft.quantum.concepts.pauli)).</span><span class="sxs-lookup"><span data-stu-id="58dbe-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="58dbe-115">Symulatory kwantowe i narzędzia do szacowania zasobów</span><span class="sxs-lookup"><span data-stu-id="58dbe-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="58dbe-116">[Symulatory kwantowe i aplikacje hosta](xref:microsoft.quantum.machines): Omówienie różnych dostępnych symulatorów oraz tego, jak programy hosta i maszyny docelowe współdziałają w celu uruchamiania programów Q#.</span><span class="sxs-lookup"><span data-stu-id="58dbe-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="58dbe-117">[Symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator): Maszyna docelowa, która symuluje pełny stan kwantowy.</span><span class="sxs-lookup"><span data-stu-id="58dbe-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="58dbe-118">Przydatne do pełnego uruchamiania lub debugowania programów o mniejszej skali (mniej niż kilkadziesiąt kubitów)</span><span class="sxs-lookup"><span data-stu-id="58dbe-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="58dbe-119">[Narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator): Szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji w języku Q# na komputerze kwantowym.</span><span class="sxs-lookup"><span data-stu-id="58dbe-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="58dbe-120">[Symulator śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Umożliwia uruchamianie programu kwantowego bez faktycznego symulowania stanu komputera kwantowego i w związku z tym może uruchamiać programy kwantowe korzystające z tysięcy kubitów.</span><span class="sxs-lookup"><span data-stu-id="58dbe-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="58dbe-121">Przydatne do debugowania kodu klasycznego w ramach programu kwantowego, a także do oszacowania wymaganych zasobów.</span><span class="sxs-lookup"><span data-stu-id="58dbe-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="58dbe-122">[Symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): Symulator kwantowy specjalnego przeznaczenia, który może być używany z milionami kubitów, ale tylko w przypadku programów z ograniczonym zestawem operacji kwantowych (X, CNOT i kontrolowanych wielokrotnie operacji X).</span><span class="sxs-lookup"><span data-stu-id="58dbe-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="58dbe-123">Strony skróconej dokumentacji</span><span class="sxs-lookup"><span data-stu-id="58dbe-123">Quick Reference Pages</span></span>

- <span data-ttu-id="58dbe-124">[Polecenia magic rozszerzenia IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Strona skróconej dokumentacji dla poleceń magic rozszerzenia IQ# w ramach notesów Jupyter Notebook dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="58dbe-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
