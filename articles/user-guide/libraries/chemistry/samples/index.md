---
title: Przykładowe aplikacje dla biblioteki Quantum Chemistry
description: Przyjrzyj się przykładowym aplikacjom dla biblioteki Microsoft Quantum Chemistry.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273930"
---
# <a name="quantum-chemistry-examples"></a>Przykłady dla chemii kwantowej

W pojęciach dotyczących chemii kwantowej ręcznie konstruowaliśmy przykładowe hamiltoniany fermionów. Teraz w bibliotece canon łączymy algorytmy symulacji chemicznej opisane w artykule [Symulowanie dynamiki Hamiltona](xref:microsoft.quantum.libraries.standard.algorithms) z [szacowaniem fazy kwantowej](xref:microsoft.quantum.libraries.characterization). Ta kombinacja pozwala nam uzyskać szacunkowe poziomy energii w reprezentowanej molekule. Jest to jedno z kluczowych zastosowań chemii kwantowej na komputerze kwantowym. 

Zamiast pojedynczo określać warunki hamiltonianów, analizujemy również niektóre przykłady, dzięki czemu możemy wykonywać eksperymenty z zakresu chemii kwantowej na dużą skalę. Zaczynamy od przykładów, które ładują hamiltonian z dziedziny chemii zakodowany w [schemacie Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

W przypadku molekuł, które są zbyt duże, aby je symulować na [symulatorze pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator), można nadal uprawiać interesującą naukę. Na przykład koszty zasobów związane z wykonywaniem dużych symulacji chemicznych mogą być nadal oceniane przy użyciu [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

Spróbujmy teraz zilustrować interesujące zastosowania biblioteki symulacji chemicznych za pomocą kilku z udostępnionych przykładów.
