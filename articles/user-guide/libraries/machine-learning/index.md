---
title: Wprowadzenie do pakietu Quantum Machine Learning | Microsoft Docs
description: Wprowadzenie do pakietu Quantum Machine Learning
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 321901a7976e4633a672495827c27c5f1645ad30
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835693"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Wprowadzenie do biblioteki Quantum Machine Learning

Biblioteka Quantum Machine Learning to interfejs API napisany w języku Q#, który umożliwia uruchamianie hybrydowych, kwantowo-klasycznych eksperymentów uczenia maszynowego. Biblioteka daje następujące możliwości:

- Ładowanie własnych danych do klasyfikowania za pomocą symulatorów kwantowych

- Wejście w świat kwantowego uczenia maszynowego dzięki przykładom i samouczkom

Wydajność będzie niska w porównaniu do aktualnie stosowanych klasycznych platform uczenia maszynowego. Pamiętaj, że wszystko działa w oparciu o symulowane urządzenie kwantowe, które samo w sobie jest kosztowne obliczeniowo.

Ta dokumentacja ma następujące cele:

- Zwięzłe wprowadzenie do narzędzi uczenia maszynowego (napisanych w języku Q\#) dla hybrydowego uczenia kwantowo-klasycznego.
- Przedstawienie koncepcji z zakresu uczenia maszynowego ze szczególnym naciskiem na ich realizację w klasyfikatorach ukierunkowanych na obwody kwantowe (nazywanych również kwantowymi klasyfikatorami sekwencyjnymi).
- Udostępnienie zestawu samouczków poświęconych podstawom, które pozwalają rozpocząć korzystanie z narzędzi oferowanych przez bibliotekę.
- Omówienie metod trenowania i weryfikacji dla takich klasyfikatorów oraz sposób ich przekształcana na konkretne operacje w języku Q\# udostępniane przez bibliotekę.

Model zaimplementowany w tej bibliotece bazuje na kwantowo-klasycznym schemacie trenowania prezentowanym przez [klasyfikatory kwantowe ukierunkowane na obwody](https://arxiv.org/abs/1804.00633)
