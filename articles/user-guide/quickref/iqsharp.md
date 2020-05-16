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
# <a name="iq-magic-commands"></a>Polecenia magic IQ#

### <a name="general"></a>Ogólne

- `%config`: Ustawia lub pobiera preferencje konfiguracyjne.
- `%estimate`: Uruchamia daną funkcję lub operację na maszynie docelowej QuantumSimulator.
- `%lsmagic`: Zwraca listę wszystkich aktualnie dostępnych poleceń Magic.
- `%package`: Umożliwia załadowanie pakietu NuGet.
- `%performance`: Zgłasza bieżące metryki wydajności dla tego jądra.
- `%simulate`: Uruchamia daną funkcję lub operację na maszynie docelowej QuantumSimulator.
- `%toffoli`: Uruchamia daną funkcję lub operację na maszynie docelowej symulatora ToffoliSimulator.
- `%who`: Zawiera akcje związane z bieżącym obszarem roboczym.
- `%workspace`: Zwraca listę wszystkich operacji i funkcji zdefiniowanych w bieżącej sesji, interaktywnie lub załadowanych z bieżącego obszaru roboczego.

### <a name="chemistry"></a>Biochemiczne

- `%chemistry.broombridge`: Ładuje i zwraca reprezentację problemu struktury elektronicznej Broombridge z danego pliku YAML.
- `%chemistry.encode`: Koduje Fermion hamiltonian do formatu, którego można używać za pomocą Q #.
- `%chemistry.fh.add_terms`: Dodaje warunki do Fermion hamiltonian.
- `%chemistry.fh.load`: Ładuje Fermion hamiltonian dla problemu ze strukturą elektroniczną. Problem jest ładowany z pliku lub przekazywany jako argument.
- `%chemistry.inputstate.load`: Ładuje problem struktury elektronicznej Broombridge i zwraca wybrany stan danych wejściowych.

### <a name="from-microsoftquantumkatas-package"></a>Z pakietu Microsoft. Quantum. Katas

- `%kata`: Wykonuje pojedynczy test i sprawdza, czy test zakończył się pomyślnie.
- `%check_kata`: Sprawdza implementację odwołania dla testu pojedynczej Kata.
    W odniesieniu do komórki zastępuje implementację odwołania jednego zadania w komórce i informuje, czy test pomyślnie zakończył się powodzeniem.
