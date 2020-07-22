---
title: Polecenia magic IQ#
description: 'Szybka Strona referencyjna dla poleceń IQ # Magic z notesami Q # Jupyter'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 2fb542df8723fa437c82b4a1dfada77e22c1d6e4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870547"
---
# <a name="iq-magic-commands"></a>Polecenia magic IQ#

### <a name="general"></a>Ogólne

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Umożliwia ustawianie lub badanie opcji konfiguracji.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Uruchamia daną funkcję lub operację na maszynie docelowej ResourcesEstimator.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Zwraca listę wszystkich aktualnie dostępnych poleceń Magic.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Umożliwia załadowanie pakietu NuGet.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Zgłasza bieżące metryki wydajności dla tego jądra.
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Uruchamia daną funkcję lub operację na maszynie docelowej QuantumSimulator.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Uruchamia daną funkcję lub operację na maszynie docelowej ToffoliSimulator.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Wyświetla listę operacji Q # dostępnych w bieżącej sesji.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Zawiera akcje związane z bieżącym obszarem roboczym.

### <a name="azure-quantum-integration"></a>Integracja z usługą Quantum platformy Azure

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Nawiązuje połączenie z obszarem roboczym usługi Azure Quantum lub wyświetla bieżący stan połączenia.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Wykonuje zadanie w obszarze roboczym usługi Azure Quantum.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Wyświetla listę zadań w bieżącym obszarze roboczym usługi Azure Quantum.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Wyświetla wyniki zadania w bieżącym obszarze roboczym usługi Azure Quantum.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Wyświetla stan zadania w bieżącym obszarze roboczym usługi Azure Quantum.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Przesyła zadanie do obszaru roboczego usługi Azure Quantum.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Ustawia lub wyświetla aktywny cel wykonywania dla zadania Q # w obszarze roboczym usługi Azure Quantum.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Chemia (z pakietu Microsoft. Quantum. chemii)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Ładuje i zwraca reprezentację problemu struktury elektronicznej Broombridge z danego pliku YAML.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Koduje Fermion hamiltonian do formatu, którego można używać za pomocą Q #.
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Dodaje warunki do Fermion hamiltonian.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Ładuje Fermion hamiltonian dla problemu ze strukturą elektroniczną. Problem jest ładowany z pliku lub przekazywany jako argument.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Ładuje problem struktury elektronicznej Broombridge i zwraca wybrany stan danych wejściowych.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (z pakietu Microsoft. Quantum. Katas)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Wykonuje pojedynczy test i sprawdza, czy test zakończył się pomyślnie.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Sprawdza implementację odwołania dla testu pojedynczej Kata.
    W odniesieniu do komórki zastępuje implementację odwołania jednego zadania w komórce i informuje, czy test pomyślnie zakończył się powodzeniem.
