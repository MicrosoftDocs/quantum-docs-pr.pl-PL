---
title: Podręcznik użytkownika języka Q#
description: Omówienie przeznaczenia i zawartości podręcznika użytkownika
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430615"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="ddedb-103">Podręcznik użytkownika języka Q#</span><span class="sxs-lookup"><span data-stu-id="ddedb-103">The Q# User Guide</span></span>

<span data-ttu-id="ddedb-104">Podręcznik użytkownika języka Q# — Zapraszamy!</span><span class="sxs-lookup"><span data-stu-id="ddedb-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="ddedb-105">Opisano tutaj szczegółowo podstawowe pojęcia dotyczące języka Q# oraz wszystkie informacje potrzebne do pisania programów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="ddedb-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="ddedb-106">Zawartość podręcznika użytkownika</span><span class="sxs-lookup"><span data-stu-id="ddedb-106">User Guide Contents</span></span>

- <span data-ttu-id="ddedb-107">[Podstawy języka Q# ](xref:microsoft.quantum.guide.basics): omówienie wprowadzające dotyczące przeznaczenia i funkcjonalności języka programowania Q#.</span><span class="sxs-lookup"><span data-stu-id="ddedb-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="ddedb-108">Język Q#</span><span class="sxs-lookup"><span data-stu-id="ddedb-108">Q# Language</span></span>

- <span data-ttu-id="ddedb-109">[Typy w języku Q#](xref:microsoft.quantum.guide.types): sekcja określa model typu języka Q# i opisuje składnię służącą do określania typów i pracy z nimi.</span><span class="sxs-lookup"><span data-stu-id="ddedb-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="ddedb-110">[Wyrażenia typu](xref:microsoft.quantum.guide.expressions): w sekcji znajdują się szczegóły dotyczące określania, odwoływania, łączenia i wykonywania operacji na wartościach każdego typu w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="ddedb-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="ddedb-111">Korzystanie z języka Q#</span><span class="sxs-lookup"><span data-stu-id="ddedb-111">Using Q#</span></span>

- <span data-ttu-id="ddedb-112">[Struktura plików języka Q#](xref:microsoft.quantum.guide.filestructure): w tej sekcji opisano strukturę i składnię pliku języka Q# `*.qs`.</span><span class="sxs-lookup"><span data-stu-id="ddedb-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="ddedb-113">[Operacje i funkcje](xref:microsoft.quantum.guide.operationsfunctions): sekcja zawiera szczegóły dwóch wywoływalnych typów w języku Q#: *operacji*, które obejmują akcje względem rejestrów kubitów oraz *funkcji*, które współpracują wyłącznie z informacjami klasycznymi.</span><span class="sxs-lookup"><span data-stu-id="ddedb-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="ddedb-114">W tym miejscu opisano, jak je definiować i wywoływać, łącznie ze sprzężonymi i kontrolowanymi wersjami operacji kwantowych.</span><span class="sxs-lookup"><span data-stu-id="ddedb-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="ddedb-115">[Zmienne lokalne](xref:microsoft.quantum.guide.variables): sekcja opisuje rolę zmiennych w programach w języku Q# oraz sposób ich skutecznego używania.</span><span class="sxs-lookup"><span data-stu-id="ddedb-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="ddedb-116">Na przykład można znaleźć informacje na temat zakresów powiązań, a także różnice między zmiennymi, których nie można modyfikować, i tymi, które można modyfikować, oraz dowiesz się, jak je przypisywać i przypisywać ponownie.</span><span class="sxs-lookup"><span data-stu-id="ddedb-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="ddedb-117">[Praca z kubitami](xref:microsoft.quantum.guide.qubits): sekcja zawiera opis funkcji języka Q# używanych do obsługi pojedynczych kubitów i systemów kubitów.</span><span class="sxs-lookup"><span data-stu-id="ddedb-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="ddedb-118">W szczególności oznacza to ich alokację, wykonywanie na nich operacji oraz, ostatecznie, ich pomiar.</span><span class="sxs-lookup"><span data-stu-id="ddedb-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="ddedb-119">[Przepływ sterowania](xref:microsoft.quantum.guide.controlflow): sekcja zawiera szczegóły programowania wzorców przepływu sterowania dostępne w języku Q#, które obejmują wiele standardowych technik (wykonywanie warunkowe, pętle for, pętle while itp.), a także wzorzec specyficzny dla programów kwantowych „Repeat-Until-Success”.</span><span class="sxs-lookup"><span data-stu-id="ddedb-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="ddedb-120">[Testowanie i debugowanie](xref:microsoft.quantum.guide.testingdebugging): w sekcji opisano szczegóły niektórych technik służących do upewniania się, że kod działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="ddedb-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="ddedb-121">Ze względu na ogólną nieprzezroczystość informacji kwantowych debugowanie programu kwantowego może wymagać wyspecjalizowanych technik.</span><span class="sxs-lookup"><span data-stu-id="ddedb-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="ddedb-122">Na szczęście język Q# obsługuje wiele klasycznych technik debugowania, do których programiści są przyzwyczajeni, a także tych, które są specyficzne dla programów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="ddedb-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="ddedb-123">Obejmuje to tworzenie/uruchamianie testów jednostkowych w języku Q#, osadzanie *asercji* dotyczących wartości i prawdopodobieństwa w kodzie oraz funkcje `Dump`, które wyprowadzają stan maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="ddedb-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="ddedb-124">Tych ostatnich funkcji można używać wraz z naszym symulatorem pełnego stanu do debugowania niektórych części obliczeń przez ominięcie pewnych ograniczeń kwantowych (np. twierdzenia o braku klonowania).</span><span class="sxs-lookup"><span data-stu-id="ddedb-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="ddedb-125">Symulatory kwantowe i narzędzia do szacowania zasobów</span><span class="sxs-lookup"><span data-stu-id="ddedb-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="ddedb-126">[Symulatory kwantowe i aplikacje hosta](xref:microsoft.quantum.machines): sekcja zawiera przegląd różnych dostępnych symulatorów, a także ogólny model wykonywania między programem hosta a maszynami docelowymi.</span><span class="sxs-lookup"><span data-stu-id="ddedb-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="ddedb-127">[Symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator): maszyna docelowa, która symuluje pełny stan kwantowy.</span><span class="sxs-lookup"><span data-stu-id="ddedb-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="ddedb-128">Przydatne do pełnego uruchomienia lub debugowania programów o mniejszej skali (mniej niż kilkadziesiąt kubitów)</span><span class="sxs-lookup"><span data-stu-id="ddedb-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="ddedb-129">[Narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator): szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji w języku Q# na komputerze kwantowym.</span><span class="sxs-lookup"><span data-stu-id="ddedb-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="ddedb-130">[Symulator śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro): umożliwia wykonywanie programu kwantowego bez faktycznego symulowania stanu komputera kwantowego i w związku z tym może wykonywać programy kwantowe korzystające z tysięcy kubitów.</span><span class="sxs-lookup"><span data-stu-id="ddedb-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="ddedb-131">Przydatne do debugowania kodu klasycznego w ramach programu kwantowego, a także do oszacowania wymaganych zasobów.</span><span class="sxs-lookup"><span data-stu-id="ddedb-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="ddedb-132">[Symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): symulator kwantowy specjalnego przeznaczenia, który może być używany z milionami kubitów, ale tylko w przypadku programów z ograniczonym zestawem operacji kwantowych (mianowicie X, CNOT i kontrolowanych wielokrotnie operacji X).</span><span class="sxs-lookup"><span data-stu-id="ddedb-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="ddedb-133">Strony skróconej dokumentacji</span><span class="sxs-lookup"><span data-stu-id="ddedb-133">Quick Reference Pages</span></span>

- <span data-ttu-id="ddedb-134">[Polecenia magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Strona skróconej dokumentacji dla poleceń magic IQ# w ramach notesów Jupyter dla języka Q#.</span><span class="sxs-lookup"><span data-stu-id="ddedb-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
