---
title: Polecenia magic IQ#
description: 'Szybka Strona referencyjna dla poleceń IQ # Magic z notesami Q # Jupyter'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431023"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="ea46a-103">Polecenia magic IQ#</span><span class="sxs-lookup"><span data-stu-id="ea46a-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="ea46a-104">Ogólne</span><span class="sxs-lookup"><span data-stu-id="ea46a-104">General</span></span>

- <span data-ttu-id="ea46a-105">`%config`: Ustawia lub pobiera preferencje konfiguracyjne.</span><span class="sxs-lookup"><span data-stu-id="ea46a-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="ea46a-106">`%estimate`: Uruchamia daną funkcję lub operację na maszynie docelowej QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="ea46a-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="ea46a-107">`%lsmagic`: Zwraca listę wszystkich aktualnie dostępnych poleceń Magic.</span><span class="sxs-lookup"><span data-stu-id="ea46a-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="ea46a-108">`%package`: Umożliwia załadowanie pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="ea46a-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="ea46a-109">`%performance`: Zgłasza bieżące metryki wydajności dla tego jądra.</span><span class="sxs-lookup"><span data-stu-id="ea46a-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="ea46a-110">`%simulate`: Uruchamia daną funkcję lub operację na maszynie docelowej QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="ea46a-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="ea46a-111">`%toffoli`: Uruchamia daną funkcję lub operację na maszynie docelowej symulatora ToffoliSimulator.</span><span class="sxs-lookup"><span data-stu-id="ea46a-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="ea46a-112">`%who`: Zawiera akcje związane z bieżącym obszarem roboczym.</span><span class="sxs-lookup"><span data-stu-id="ea46a-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="ea46a-113">`%workspace`: Zwraca listę wszystkich operacji i funkcji zdefiniowanych w bieżącej sesji, interaktywnie lub załadowanych z bieżącego obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="ea46a-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="ea46a-114">Biochemiczne</span><span class="sxs-lookup"><span data-stu-id="ea46a-114">Chemistry</span></span>

- <span data-ttu-id="ea46a-115">`%chemistry.broombridge`: Ładuje i zwraca reprezentację problemu struktury elektronicznej Broombridge z danego pliku YAML.</span><span class="sxs-lookup"><span data-stu-id="ea46a-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="ea46a-116">`%chemistry.encode`: Koduje Fermion hamiltonian do formatu, którego można używać za pomocą Q #.</span><span class="sxs-lookup"><span data-stu-id="ea46a-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="ea46a-117">`%chemistry.fh.add_terms`: Dodaje warunki do Fermion hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="ea46a-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="ea46a-118">`%chemistry.fh.load`: Ładuje Fermion hamiltonian dla problemu ze strukturą elektroniczną.</span><span class="sxs-lookup"><span data-stu-id="ea46a-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="ea46a-119">Problem jest ładowany z pliku lub przekazywany jako argument.</span><span class="sxs-lookup"><span data-stu-id="ea46a-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="ea46a-120">`%chemistry.inputstate.load`: Ładuje problem struktury elektronicznej Broombridge i zwraca wybrany stan danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="ea46a-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="ea46a-121">Z pakietu Microsoft. Quantum. Katas</span><span class="sxs-lookup"><span data-stu-id="ea46a-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="ea46a-122">`%kata`: Wykonuje pojedynczy test i sprawdza, czy test zakończył się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="ea46a-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="ea46a-123">`%check_kata`: Sprawdza implementację odwołania dla testu pojedynczej Kata.</span><span class="sxs-lookup"><span data-stu-id="ea46a-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="ea46a-124">W odniesieniu do komórki zastępuje implementację odwołania jednego zadania w komórce i informuje, czy test pomyślnie zakończył się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="ea46a-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
