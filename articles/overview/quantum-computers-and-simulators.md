---
title: Komputery kwantowe i symulatory kwantowe
description: Dowiedz się więcej na temat sprzętu kwantowego, symulatorów kwantowych i działania operacji kwantowych.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
no-loc:
- Q#
- $$v
ms.openlocfilehash: 714d8163a66feea2766a71886c6d07275098ac2f
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771358"
---
# <a name="quantum-computers-and-quantum-simulators"></a>Komputery kwantowe i symulatory kwantowe

Komputery kwantowe są nadal w początkowej fazie ich rozwoju. Sprzęt i konserwacja są kosztowne, a większość systemów znajduje się na uniwersytetach i w laboratoriach badawczych. Technologia jednak się rozwija i możliwy jest ograniczony dostęp publiczny do niektórych systemów.

Symulatory kwantowe to programy działające na klasycznych komputerach umożliwiające uruchamianie i testowanie programów kwantowych w środowisku, które przewiduje, jak kubity będą reagować na różne operacje.

## <a name="quantum-hardware"></a>Sprzęt kwantowy

Komputer kwantowy składa się z trzech głównych części: obszaru do przechowywania kubitów, metody przesyłania sygnałów do kubitów i klasycznego komputera do uruchamiania programu i wysyłania instrukcji.

- Materiał kwantowy, z którego składają się kubity, jest delikatny i niezwykle czuły na wpływy środowiska. W przypadku niektórych metod magazynowania kubitów jednostka, w której znajdują się kubity, jest przetrzymywana w temperaturze bliskiej zeru bezwzględnemu, aby zmaksymalizować ich spójność. Inne typy magazynów kubitów korzystają z komory próżniowej w celu zminimalizowania drgań i ustabilizowania kubitów.  
- Istnieją różne metody wysyłania sygnałów do kubitów, na przykład mikrofale, laser i napięcie elektryczne.

Aby uzyskać prawidłowe działanie komputerów kwantowych, należy sprostać wielu wyzwaniom. Istotnym problemem dotyczącym komputerów kwantowych jest korekcja błędów, a skalowanie w górę (dodanie większej liczby kubitów) zwiększa jeszcze częstotliwość ich występowania. Ze względu na te ograniczenia kwantowy komputer osobisty stojący na Twoim biurku to nadal jeszcze obrazek z dalekiej przyszłości, ale laboratoryjne komputery kwantowe dostępne komercyjnie to już niedaleka przyszłość.

## <a name="quantum-simulators"></a>Symulatory kwantowe

Symulatory kwantowe, które działają na klasycznych komputerach, umożliwiają symulowanie uruchamiania algorytmów kwantowych w systemie kwantowym.  Zestaw Microsoft Quantum Development Kit (QDK) zawiera wektorowy symulator pełnego stanu oraz inne wyspecjalizowane symulatory kwantowe.

## <a name="topological-qubit"></a>Kubit topologiczny

Firma Microsoft opracowuje komputer kwantowy oparty na kubitach topologicznych. Kubit topologiczny będzie mniej zależny od zmian w środowisku, co z kolei spowoduje ograniczenie liczby wymaganych procesów naprawiania błędów zewnętrznych.

Funkcja kubitów topologicznych zwiększa stabilność i odporność na zakłócenia środowiskowe, co oznacza, że kubity mogą być łatwiej skalowane i dłużej pozostać niezawodnie.

## <a name="microsoft-and-quantum-hardware-partnerships"></a>Partnerstwo firmy Microsoft i producentów sprzętu kwantowego

Firma Microsoft współpracuje z producentami sprzętu kwantowego, takimi jak IonQ, Honeywell i QCI, w celu opracowania komputerów kwantowych dostępnych w przyszłości dla deweloperów. Korzystając z platformy Azure Quantum, deweloperzy będą mogli używać zestawu Microsoft Quantum Development Kit (QDK) i języka Q# do pisania programów kwantowych i ich zdalnego uruchamiania.

## <a name="quantum-computations"></a>Obliczenia kwantowe

Wykonywanie obliczeń na komputerze kwantowym lub symulatorze kwantowym przebiega w ramach podstawowego procesu:

- Uzyskiwanie dostępu do kubitów
- Inicjowanie kubitów do żądanego stanu
- Wykonywanie operacji przekształcania stanów kubitów
- Pomiar nowych stanów kubitów

Inicjowanie i przekształcanie kubitów odbywa się za pomocą **operacji kwantowych** (czasami nazywanych bramami kwantowymi). Operacje kwantowe są podobne do operacji logicznych wykonywanych w klasycznych obliczeniach, takich jak ORAZ, LUB, NIE i XOR. Przeprowadzać można różne operacje: od podstawowego przerzucania stanu kubitu z 1 na 0 lub splątania pary kubitów do korzystania z serii wielu operacji w celu wpłynięcia na prawdopodobieństwo kolapsu kubitu z superpozycją w jeden sposób lub inny.

> [!NOTE] 
> [Biblioteki języka Q#](xref:microsoft.quantum.libraries) udostępniają wbudowane operacje, które definiują złożone kombinacje operacji kwantowych niskiego poziomu. Operacje biblioteki mogą być stosowane do przekształcania kubitów i tworzenia bardziej złożonych operacji zdefiniowanych przez użytkownika.  

Pomiar wyniku obliczeń daje nam odpowiedź, ale w przypadku niektórych algorytmów kwantowych nie jest to zawsze odpowiedź poprawna. Ponieważ wyniki niektórych algorytmów kwantowych bazują na prawdopodobieństwie skonfigurowanym przez operacje kwantowe, te obliczenia są uruchamiane wiele razy, aby uzyskać rozkład prawdopodobieństwa i uściślić dokładność wyników.  Sprawdzanie, czy operacja zwróciła poprawną odpowiedź, czyli weryfikacja kwantowa, jest sporym wyzwaniem w obliczeniach kwantowych.

## <a name="summary"></a>Podsumowanie

Niektóre pojęcia używane w obliczeniach kwantowych są takie same jak w przypadku klasycznych obliczeń, ale występują też pewne dodatkowe elementy. Oto kilka kluczowych wniosków:

- Sprzęt kwantowy jest kosztowny i delikatny w obsłudze, dlatego do pisania i testowania programów są używane symulatory kwantowe.
- Zarówno komputery klasyczne, jak i kwantowe do przygotowywania obliczeń używają operacji logicznych (lub bram).
- Obliczenia kwantowe zwracają prawdopodobieństwa.

Postęp w sprzęcie i technikach kwantowych szybko zmieniają sytuację. W tym miejscu przedstawiono zaledwie kilka [aktualnych opracowań](https://phys.org/search/?search=quantum+computer&s=0).

## <a name="next-steps"></a>Następne kroki

[Co to jest język programowania Q# i zestaw QDK?](xref:microsoft.quantum.overview.q-sharp)
