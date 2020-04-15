---
title: Wprowadzenie do biblioteki Quantum Chemistry
description: Poznaj bibliotekę Microsoft Quantum Chemistry i zobacz, jak jest używana do symulowania problemów związanych ze strukturą elektroniczną na komputerach kwantowych.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: 4268eafa5e53c0a026d179503ac6db88652a8f90
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907328"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Wprowadzenie do biblioteki Quantum Chemistry

Symulacja systemów fizycznych była długo głównym zastosowaniem obliczeń kwantowych.  Wynika to z faktu, że dynamika kwantowa jest szeroko uważana za niemożliwą do symulowania na komputerach kwantowych. Dzieje się tak, ponieważ złożoność symulowania systemu rośnie wykładniczo wraz ze wzrostem rozmiaru badanego systemu kwantowego.  Symulowanie problemów chemicznych i materiałowych pozostaje prawdopodobnie najbardziej sugestywnym zastosowaniem obliczeń kwantowych i umożliwia nam sondowanie mechanizmów reakcji chemicznych, które w inny sposób byłyby niemożliwe do mierzenia lub symulowania.  Obliczenia kwantowe umożliwią nam też symulowanie skorelowanych materiałów elektronicznych, takich jak nadprzewodniki wysokotemperaturowe. Lista zastosowań w tej dziedzinie jest bardzo obszerna.

W zamierzeniu ta dokumentacja miała stanowić zwięzłe wprowadzenie do symulowania problemów ze strukturą elektroniczną na komputerach kwantowych i pomóc czytelnikowi zrozumieć rolę, jaką odgrywa w tej dziedzinie wiele aspektów biblioteki symulacji Hamiltona.  Zaczniemy od krótkiego wprowadzenia do mechaniki kwantowej, a następnie przejdziemy do omówienia, w jaki sposób są w niej modelowane systemy elektroniczne.  Następnie przedyskutujemy, jak dynamika kwantowa może być emulowana przy użyciu komputera kwantowego.  Po zakończeniu tej dyskusji omówimy dwie metody kompilowania dynamiki kwantowej w sekwencje bramek elementarnych: dekompozycje Suzuki-Trottera i kubityzację.
