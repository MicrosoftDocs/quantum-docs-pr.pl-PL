---
title: Symulatory kwantowe i programy w języku Q#
description: Opisuje symulatory kwantowe dostępne jako maszyny docelowe dla programów w języku Q#.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6a2a4bb829301f9db9bd14f3240556a403b9a54f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833432"
---
# <a name="quantum-simulators"></a>Symulatory kwantowe

Symulatory kwantowe to programy działające na klasycznych komputerach pełniące rolę *maszyny docelowej* dla programu w języku Q# i umożliwiające uruchamianie oraz testowanie programów kwantowych w środowisku, które przewiduje, jak kubity będą reagować na różne operacje. W tym artykule opisano, które symulatory kwantowe są dołączone do zestawu Quantum Development Kit (QDK), a także różne sposoby przekazywania programu w języku Q# do symulatorów kwantowych, na przykład za pośrednictwem wiersza polecenia lub przy użyciu kodu sterownika napisanego w języku klasycznym.  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Symulatory kwantowe zestawu Quantum Development Kit (QDK)

Symulator kwantowy zapewnia implementacje kwantowych typów pierwotnych algorytmu. Obejmują one operacje pierwotne, takie jak `H`, `CNOT` i `Measure`, a także śledzenie kubitów i zarządzanie nimi. Zestaw QDK zawiera różne klasy symulatorów kwantowych reprezentujące różne modele uruchamiania dla tego samego algorytmu kwantowego. 


Każdy typ symulatora kwantowego może udostępniać odrębną implementację typów pierwotnych. Na przykład [symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator) uruchamia algorytm kwantowy, w pełni symulując [wektor stanu kwantowego](xref:microsoft.quantum.glossary#quantum-state), podczas gdy [symulator śledzenia komputera kwantowego](xref:microsoft.quantum.machines.qc-trace-simulator.intro) w ogóle nie uwzględnia rzeczywistego stanu kwantowego. Zamiast tego śledzi on użycie bramy, kubitów oraz innych zasobów.

### <a name="quantum-machine-classes"></a>Klasy maszyn kwantowych

W przyszłości w zestawie QDK zostaną zdefiniowane dodatkowe klasy maszyn kwantowych umożliwiające obsługę innych typów symulacji oraz uruchamianie na sprzęcie kwantowym. Zapewnienie niezmienności algorytmu przy różnych bazowych implementacjach na maszynach ułatwia jego testowanie i debugowanie w symulacji, a następnie uruchamianie na używanym komputerze z poczuciem pewności, że nie został zmieniony.

Zestaw QDK zawiera kilka klas maszyn kwantowych, z których wszystkie są zdefiniowane w przestrzeni nazw `Microsoft.Quantum.Simulation.Simulators`.

|Symulator |Klasa|Opis|
|-----|------|---|
|[Symulator pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | Uruchamia oraz debuguje algorytmy kwantowe i jest ograniczony do około 30 kubitów. |
|[Proste narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | Wykonuje ogólną analizę zasobów wymaganych do uruchomienia algorytmu kwantowego i obsługuje tysiące kubitów.|
|[Oparte na śledzeniu narzędzie do szacowania zasobów](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |Uruchamia zaawansowaną analizę zużycia zasobów dla całego grafu wywołań algorytmu i obsługuje tysiące kubitów.|
|[Symulator Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |Symuluje algorytmy kwantowe ograniczone do operacji `X` i `CNOT` oraz kontrolowanych wielokrotnie operacji kwantowych `X`; obsługuje tysiące kubitów. |

## <a name="invoking-the-quantum-simulator"></a>Wywoływanie symulatora kwantowego

W sekcji [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs) przedstawiono trzy sposoby przekazywania kodu w języku Q# do symulatora kwantowego: 

* Za pomocą wiersza polecenia
* Za pomocą programu hosta w języku Python
* Za pomocą programu hosta w języku C#

Maszyny kwantowe to normalne wystąpienia klas .NET, dlatego tworzy się je przez wywołanie konstruktora, tak jak w przypadku dowolnej klasy .NET. To, jak zostanie to zrobione, zależy sposobu uruchamiania programu w języku Q#.

## <a name="next-steps"></a>Następne kroki

* Aby uzyskać szczegółowe informacje o sposobie wywoływania maszyn docelowych dla programów w języku Q# w różnych środowiskach, zobacz [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs).
