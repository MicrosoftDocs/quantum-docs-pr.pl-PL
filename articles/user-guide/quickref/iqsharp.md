---
title: I Q# polecenia Magic
description: Szybka Strona referencyjna dla Q# poleceń Magic z Q# notesami Jupyter
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: reference
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb6517b782a82c1cb159951af41df9bfde51c0bb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858531"
---
# <a name="ino-locq-magic-commands"></a>I Q# polecenia Magic

### <a name="general"></a>Ogólne

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Umożliwia ustawianie lub badanie opcji konfiguracji.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Uruchamia daną funkcję lub operację na maszynie docelowej ResourcesEstimator.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Zwraca listę wszystkich aktualnie dostępnych poleceń Magic.
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): Wyświetla listę aktualnie otwartych obszarów nazw i ich aliasów.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Umożliwia załadowanie pakietu NuGet.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Zgłasza bieżące metryki wydajności dla tego jądra.
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Umożliwia wyświetlanie lub Dodawanie Q# odwołań do projektu. 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Uruchamia daną funkcję lub operację na maszynie docelowej QuantumSimulator.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Uruchamia daną funkcję lub operację na maszynie docelowej ToffoliSimulator.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Wyświetla listę Q# operacji dostępnych w bieżącej sesji.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Zawiera akcje związane z bieżącym obszarem roboczym.

### <a name="azure-quantum-integration"></a>Integracja z usługą Quantum platformy Azure

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Nawiązuje połączenie z obszarem roboczym usługi Azure Quantum lub wyświetla bieżący stan połączenia.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Przesyła zadanie do obszaru roboczego usługi Azure Quantum i czeka na jego zakończenie.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Wyświetla listę zadań w bieżącym obszarze roboczym usługi Azure Quantum.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Wyświetla wyniki zadania w bieżącym obszarze roboczym usługi Azure Quantum.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Wyświetla stan zadania w bieżącym obszarze roboczym usługi Azure Quantum.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Przesyła zadanie do obszaru roboczego usługi Azure Quantum.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Ustawia lub wyświetla aktywny obiekt docelowy przebiegu do Q# przesłania zadania w obszarze roboczym usługi Azure Quantum.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Chemia (z pakietu Microsoft. Quantum. chemii)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Ładuje i zwraca reprezentację problemu struktury elektronicznej Broombridge z danego pliku YAML.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Koduje Fermion hamiltonian do formatu, którego można używać Q# .
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Dodaje warunki do Fermion hamiltonian.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Ładuje Fermion hamiltonian dla problemu ze strukturą elektroniczną. Problem jest ładowany z pliku lub przekazywany jako argument.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Ładuje problem struktury elektronicznej Broombridge i zwraca wybrany stan danych wejściowych.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (z pakietu Microsoft. Quantum. Katas)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Uruchamia pojedynczy test i zgłasza, czy test pomyślnie zakończył się powodzeniem.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Sprawdza implementację odwołania dla testu pojedynczej Kata.
    W odniesieniu do komórki zastępuje implementację odwołania jednego zadania w komórce i informuje, czy test pomyślnie zakończył się powodzeniem.
