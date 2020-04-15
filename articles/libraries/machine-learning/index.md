---
title: Wprowadzenie do pakietu Quantum Machine Learning | Microsoft Docs
description: Wprowadzenie do pakietu Quantum Machine Learning
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907855"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="9c1d1-103">Wprowadzenie do biblioteki Quantum Machine Learning</span><span class="sxs-lookup"><span data-stu-id="9c1d1-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="9c1d1-104">Biblioteka Quantum Machine Learning to interfejs API napisany w języku Q#, który umożliwia uruchamianie hybrydowych, kwantowo-klasycznych eksperymentów uczenia maszynowego.</span><span class="sxs-lookup"><span data-stu-id="9c1d1-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="9c1d1-105">Biblioteka daje następujące możliwości:</span><span class="sxs-lookup"><span data-stu-id="9c1d1-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="9c1d1-106">Ładowanie własnych danych do klasyfikowania za pomocą symulatorów kwantowych</span><span class="sxs-lookup"><span data-stu-id="9c1d1-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="9c1d1-107">Wejście w świat kwantowego uczenia maszynowego dzięki przykładom i samouczkom</span><span class="sxs-lookup"><span data-stu-id="9c1d1-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="9c1d1-108">Wydajność będzie niska w porównaniu do aktualnie stosowanych klasycznych platform uczenia maszynowego. Pamiętaj, że wszystko działa w oparciu o symulowane urządzenie kwantowe, które samo w sobie jest kosztowne obliczeniowo.</span><span class="sxs-lookup"><span data-stu-id="9c1d1-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="9c1d1-109">Ta dokumentacja ma następujące cele:</span><span class="sxs-lookup"><span data-stu-id="9c1d1-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="9c1d1-110">Zwięzłe wprowadzenie do narzędzi uczenia maszynowego (napisanych w języku Q\#) dla hybrydowego uczenia kwantowo-klasycznego.</span><span class="sxs-lookup"><span data-stu-id="9c1d1-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="9c1d1-111">Przedstawienie koncepcji z zakresu uczenia maszynowego ze szczególnym naciskiem na ich realizację w klasyfikatorach ukierunkowanych na obwody kwantowe (nazywanych również kwantowymi klasyfikatorami sekwencyjnymi).</span><span class="sxs-lookup"><span data-stu-id="9c1d1-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="9c1d1-112">Udostępnienie zestawu samouczków poświęconych podstawom, które pozwalają rozpocząć korzystanie z narzędzi oferowanych przez bibliotekę.</span><span class="sxs-lookup"><span data-stu-id="9c1d1-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="9c1d1-113">Omówienie metod trenowania i weryfikacji dla takich klasyfikatorów oraz sposób ich przekształcana na konkretne operacje w języku Q\# udostępniane przez bibliotekę.</span><span class="sxs-lookup"><span data-stu-id="9c1d1-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="9c1d1-114">Model zaimplementowany w tej bibliotece bazuje na kwantowo-klasycznym schemacie trenowania prezentowanym przez [klasyfikatory kwantowe ukierunkowane na obwody](https://arxiv.org/abs/1804.00633)</span><span class="sxs-lookup"><span data-stu-id="9c1d1-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
