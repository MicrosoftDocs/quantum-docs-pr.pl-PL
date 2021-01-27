---
title: Wprowadzenie do pakietu Quantum Machine Learning | Microsoft Docs
description: Wprowadzenie do pakietu Quantum Machine Learning
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: conceptual
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1e36948a216a06d76b99cd451bbfac6f5defd7c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858791"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="a5456-103">Wprowadzenie do biblioteki Quantum Machine Learning</span><span class="sxs-lookup"><span data-stu-id="a5456-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="a5456-104">Biblioteka Quantum Machine Learning to interfejs API napisany w języku Q#, który umożliwia uruchamianie hybrydowych, kwantowo-klasycznych eksperymentów uczenia maszynowego.</span><span class="sxs-lookup"><span data-stu-id="a5456-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="a5456-105">Biblioteka daje następujące możliwości:</span><span class="sxs-lookup"><span data-stu-id="a5456-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="a5456-106">Ładowanie własnych danych do klasyfikowania za pomocą symulatorów kwantowych</span><span class="sxs-lookup"><span data-stu-id="a5456-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="a5456-107">Wejście w świat kwantowego uczenia maszynowego dzięki przykładom i samouczkom</span><span class="sxs-lookup"><span data-stu-id="a5456-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="a5456-108">Wydajność będzie niska w porównaniu do aktualnie stosowanych klasycznych platform uczenia maszynowego. Pamiętaj, że wszystko działa w oparciu o symulowane urządzenie kwantowe, które samo w sobie jest kosztowne obliczeniowo.</span><span class="sxs-lookup"><span data-stu-id="a5456-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="a5456-109">Ta dokumentacja ma następujące cele:</span><span class="sxs-lookup"><span data-stu-id="a5456-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="a5456-110">Zwięzłe wprowadzenie do narzędzi uczenia maszynowego (napisanych w języku Q\#) dla hybrydowego uczenia kwantowo-klasycznego.</span><span class="sxs-lookup"><span data-stu-id="a5456-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="a5456-111">Przedstawienie koncepcji z zakresu uczenia maszynowego ze szczególnym naciskiem na ich realizację w klasyfikatorach ukierunkowanych na obwody kwantowe (nazywanych również kwantowymi klasyfikatorami sekwencyjnymi).</span><span class="sxs-lookup"><span data-stu-id="a5456-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="a5456-112">Udostępnienie zestawu samouczków poświęconych podstawom, które pozwalają rozpocząć korzystanie z narzędzi oferowanych przez bibliotekę.</span><span class="sxs-lookup"><span data-stu-id="a5456-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="a5456-113">Omówienie metod trenowania i weryfikacji dla takich klasyfikatorów oraz sposób ich przekształcana na konkretne operacje w języku Q\# udostępniane przez bibliotekę.</span><span class="sxs-lookup"><span data-stu-id="a5456-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="a5456-114">Model zaimplementowany w tej bibliotece bazuje na kwantowo-klasycznym schemacie trenowania prezentowanym przez [klasyfikatory kwantowe ukierunkowane na obwody](https://arxiv.org/abs/1804.00633)</span><span class="sxs-lookup"><span data-stu-id="a5456-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
