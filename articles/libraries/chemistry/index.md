---
title: Wprowadzenie do pakietu Quantum Chemistry | Microsoft Docs
description: Wprowadzenie do pakietu Quantum Chemistry
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: e5a9dd70874f1ae0baf4b781346278195a980a7e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960420"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Wprowadzenie do biblioteki Quantum Chemistry

Symulacja systemów fizycznych była długo głównym zastosowaniem obliczeń kwantowych.  Wynika to z faktu, że dynamika kwantowa jest szeroko uważana za niemożliwą do symulowania na komputerach kwantowych. Dzieje się tak, ponieważ złożoność symulowania systemu rośnie wykładniczo wraz ze wzrostem rozmiaru badanego systemu kwantowego.  Symulowanie problemów chemicznych i materiałowych pozostaje prawdopodobnie najbardziej sugestywnym zastosowaniem obliczeń kwantowych i umożliwia nam sondowanie mechanizmów reakcji chemicznych, które w inny sposób byłyby niemożliwe do mierzenia lub symulowania.  Obliczenia kwantowe umożliwią nam też symulowanie skorelowanych materiałów elektronicznych, takich jak nadprzewodniki wysokotemperaturowe. Lista zastosowań w tej dziedzinie jest bardzo obszerna.

W zamierzeniu ta dokumentacja miała stanowić zwięzłe wprowadzenie do symulowania problemów ze strukturą elektroniczną na komputerach kwantowych i pomóc czytelnikowi zrozumieć rolę, jaką odgrywa w tej dziedzinie wiele aspektów biblioteki symulacji Hamiltona.  Zaczniemy od krótkiego wprowadzenia do mechaniki kwantowej, a następnie przejdziemy do omówienia, w jaki sposób są w niej modelowane systemy elektroniczne.  Następnie przedyskutujemy, jak dynamika kwantowa może być emulowana przy użyciu komputera kwantowego.  Po zakończeniu tej dyskusji omówimy dwie metody kompilowania dynamiki kwantowej w sekwencje bramek elementarnych: dekompozycje Suzuki-Trottera i kubityzację.
