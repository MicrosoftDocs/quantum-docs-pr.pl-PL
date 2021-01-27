---
title: Wprowadzenie do biblioteki Quantum Chemistry
description: Poznaj bibliotekę Microsoft Quantum Chemistry i zobacz, jak jest używana do symulowania problemów związanych ze strukturą elektroniczną na komputerach kwantowych.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3fa606600db1641b9f8b86ccefebb7681f181b92
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847484"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Wprowadzenie do biblioteki Quantum Chemistry

Symulacja systemów fizycznych była długo głównym zastosowaniem obliczeń kwantowych.  Wynika to z faktu, że dynamika kwantowa jest szeroko uważana za niemożliwą do symulowania na komputerach kwantowych. Dzieje się tak, ponieważ złożoność symulowania systemu rośnie wykładniczo wraz ze wzrostem rozmiaru badanego systemu kwantowego.  Symulowanie problemów chemicznych i materiałowych pozostaje prawdopodobnie najbardziej sugestywnym zastosowaniem obliczeń kwantowych i umożliwia nam sondowanie mechanizmów reakcji chemicznych, które w inny sposób byłyby niemożliwe do mierzenia lub symulowania.  Obliczenia kwantowe umożliwią nam też symulowanie skorelowanych materiałów elektronicznych, takich jak nadprzewodniki wysokotemperaturowe. Lista zastosowań w tej dziedzinie jest bardzo obszerna.

W zamierzeniu ta dokumentacja miała stanowić zwięzłe wprowadzenie do symulowania problemów ze strukturą elektroniczną na komputerach kwantowych i pomóc czytelnikowi zrozumieć rolę, jaką odgrywa w tej dziedzinie wiele aspektów biblioteki symulacji Hamiltona.  Zaczniemy od krótkiego wprowadzenia do mechaniki kwantowej, a następnie przejdziemy do omówienia, w jaki sposób są w niej modelowane systemy elektroniczne.  Następnie przedyskutujemy, jak dynamika kwantowa może być emulowana przy użyciu komputera kwantowego.  Po zakończeniu tej dyskusji omówimy dwie metody kompilowania dynamiki kwantowej w sekwencje bramek elementarnych: dekompozycje Suzuki-Trottera i kubityzację.
