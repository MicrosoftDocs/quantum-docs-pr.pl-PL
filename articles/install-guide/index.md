---
title: Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: b209f0b600d973c3870c66060e1b484ec519322f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820712"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="9aa89-102">Instalowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="9aa89-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="9aa89-103">Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym.</span><span class="sxs-lookup"><span data-stu-id="9aa89-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="9aa89-104">Zestaw QDK składa się z:</span><span class="sxs-lookup"><span data-stu-id="9aa89-104">The QDK consists of:</span></span>

- <span data-ttu-id="9aa89-105">języka programowania Q#</span><span class="sxs-lookup"><span data-stu-id="9aa89-105">the Q# programming language</span></span>
- <span data-ttu-id="9aa89-106">zestawu bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#</span><span class="sxs-lookup"><span data-stu-id="9aa89-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="9aa89-107">interfejsów API dla języków Python i .NET (tj. C#, F# i VB.NET) umożliwiających uruchamianie programów kwantowych napisanych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="9aa89-107">APIs for Python and .NET languages (i.e.: C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="9aa89-108">narzędzia ułatwiające programowanie</span><span class="sxs-lookup"><span data-stu-id="9aa89-108">tools to facilitate your development</span></span>

<span data-ttu-id="9aa89-109">Programy Q# są często parowane z programem hosta napisanym w języku .NET (zazwyczaj C#) lub Python.</span><span class="sxs-lookup"><span data-stu-id="9aa89-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="9aa89-110">Pozwala to na wywoływanie operacji kwantowych z poziomu klasycznego programu.</span><span class="sxs-lookup"><span data-stu-id="9aa89-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="9aa89-111">Ponadto zestaw QDK zapewnia obsługę języka Q# przez notesy Jupyter przy użyciu jądra Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="9aa89-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="9aa89-112">Zestaw QDK jest dostępny dla wielu środowisk projektowych.</span><span class="sxs-lookup"><span data-stu-id="9aa89-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="9aa89-113">Wybierz preferowaną konfigurację z poniższych sekcji:</span><span class="sxs-lookup"><span data-stu-id="9aa89-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="9aa89-114">[Zainstaluj język Q# dla języka C#:](xref:microsoft.quantum.install.cs) wybierz to środowisko, jeśli chcesz połączyć języki C# i Q# w celu utworzenia programu hosta w języku C#, który wywołuje operacje w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="9aa89-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="9aa89-115">[Zainstaluj język Q# dla języka Python:](xref:microsoft.quantum.install.python) wybierz to środowisko, jeśli chcesz połączyć języki Python i Q# w celu utworzenia programu hosta w języku Python, który wywołuje operacje w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="9aa89-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="9aa89-116">[Zainstaluj język Q# dla notesów Jupyter:](xref:microsoft.quantum.install.jupyter) wybierz to środowisko, aby wykonywać kod Q# w komórkach z osadzonym tekstem lub tworzyć interaktywne samouczki z zakresu obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="9aa89-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="9aa89-117">Nie wybieraj tego środowiska, jeśli chcesz połączyć język Q# z zewnętrznym klasycznym programem hosta.</span><span class="sxs-lookup"><span data-stu-id="9aa89-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
