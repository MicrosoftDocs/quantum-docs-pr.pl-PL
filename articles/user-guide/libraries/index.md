---
title: Biblioteki zestawu Quantum Development Kit
description: Omówienie biblioteki standardowej, chemicznej i numerycznej zawartych w zestawie Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: d61fe459362fdb5f3550768a26b34656a8a538a7
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869107"
---
# <a name="overview-of-no-locq-libraries"></a><span data-ttu-id="f832b-103">Omówienie bibliotek języka Q#</span><span class="sxs-lookup"><span data-stu-id="f832b-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="f832b-104">Zestaw Quantum Development Kit jest dostarczany z kilkoma bibliotekami, które ułatwiają tworzenie aplikacji kwantowych w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="f832b-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="f832b-105">W tej sekcji dokumentacji opisano te biblioteki i sposoby ich używania w programach.</span><span class="sxs-lookup"><span data-stu-id="f832b-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="f832b-106">[**Biblioteki standardowe**](xref:microsoft.quantum.libraries.standard.intro): W tej sekcji opisano preludium, bibliotekę definiującą interfejs między programami Q# i maszynami docelowymi, oraz kanon, bibliotekę języka Q# udostępniającą operacje i funkcje ogólnego zastosowania przydatne podczas pisania programów w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="f832b-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="f832b-107">[**Biblioteka dla chemii kwantowej**](xref:microsoft.quantum.chemistry.concepts.intro): W tej sekcji opisano bibliotekę dla chemii kwantowej udostępniającą model danych na potrzeby ładowania reprezentacji funkcji Hamiltona dla fermionów, a także operacje i funkcje symulacji kwantowej, które działają w tych reprezentacjach.</span><span class="sxs-lookup"><span data-stu-id="f832b-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="f832b-108">[**Biblioteka dla liczb kwantowych**](xref:microsoft.quantum.numerics.intro): W tej sekcji opisano bibliotekę dla liczb kwantowych, która udostępnia implementacje dla hosta funkcji matematycznych.</span><span class="sxs-lookup"><span data-stu-id="f832b-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="f832b-109">Obsługuje ona reprezentacje liczb całkowitych (ze znakiem i bez znaki) oraz liczb stałoprzecinkowych.</span><span class="sxs-lookup"><span data-stu-id="f832b-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>
- <span data-ttu-id="f832b-110">[**Biblioteka dla kwantowego uczenia maszynowego**](xref:microsoft.quantum.machine-learning.concepts.intro): Ta sekcja zawiera opis biblioteki dla kwantowego uczenia maszynowego udostępniającej implementację klasyfikatorów sekwencyjnych, które korzystają z obliczeń kwantowych w celu rozumienia danych.</span><span class="sxs-lookup"><span data-stu-id="f832b-110">[**Quantum machine learning library**](xref:microsoft.quantum.machine-learning.concepts.intro): This section describes the quantum machine learning library, which provides an implementation of the sequential classifiers that take advantage of quantum computing to understand data.</span></span>

<span data-ttu-id="f832b-111">Kod źródłowy tych bibliotek oraz przykłady kodu można uzyskać z witryny GitHub.</span><span class="sxs-lookup"><span data-stu-id="f832b-111">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span>
<span data-ttu-id="f832b-112">Aby uzyskać więcej informacji, zobacz [Licencjonowanie](xref:microsoft.quantum.libraries.licensing).</span><span class="sxs-lookup"><span data-stu-id="f832b-112">See [Licensing](xref:microsoft.quantum.libraries.licensing) for further information.</span></span> <span data-ttu-id="f832b-113">Należy zauważyć, że odwołania do pakietów („pliki binarne”) są dostępne również dla bibliotek, które oferują inny sposób dołączania bibliotek do projektów.</span><span class="sxs-lookup"><span data-stu-id="f832b-113">Note that package references ("binaries") are available also for the libraries and offer another way of including the libraries in projects.</span></span>
<span data-ttu-id="f832b-114">Można je łatwo uzyskać z witryny [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="f832b-114">A convenient way of obtaining them is via [NuGet](https://nuget.org).</span></span>
