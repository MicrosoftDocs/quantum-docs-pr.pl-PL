---
title: Instalowanie zestawu Microsoft Quantum Development Kit (QDK)
description: Sposób instalowania zestawu Microsoft Quantum Development Kit dla różnych środowisk.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863710"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="a7177-103">Instalowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="a7177-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="a7177-104">Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym.</span><span class="sxs-lookup"><span data-stu-id="a7177-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="a7177-105">Zestaw QDK składa się z:</span><span class="sxs-lookup"><span data-stu-id="a7177-105">The QDK consists of:</span></span>

- <span data-ttu-id="a7177-106">Język programowania Q#</span><span class="sxs-lookup"><span data-stu-id="a7177-106">The Q# programming language</span></span>
- <span data-ttu-id="a7177-107">Zestaw bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#</span><span class="sxs-lookup"><span data-stu-id="a7177-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="a7177-108">Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="a7177-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="a7177-109">Narzędzia ułatwiające programowanie</span><span class="sxs-lookup"><span data-stu-id="a7177-109">Tools to facilitate your development</span></span>

<span data-ttu-id="a7177-110">Programy w języku Q# mogą działać jako aplikacje autonomiczne przy użyciu programu Visual Studio Code lub Visual Studio albo za pośrednictwem notesów Jupyter za pomocą jądra Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="a7177-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="a7177-111">Mogą być również sparowane z programem hosta napisanym w języku .NET (zazwyczaj C#) lub Python, umożliwiając wywoływanie operacji kwantowych z poziomu klasycznego programu.</span><span class="sxs-lookup"><span data-stu-id="a7177-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="a7177-112">Przepływy pracy dla każdej z tych konfiguracji są opisane i porównane w sekcji [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="a7177-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="a7177-113">Aby kontynuować instalowanie zestawu QDK i tworzenie projektów języka Q#, wybierz preferowaną konfigurację:</span><span class="sxs-lookup"><span data-stu-id="a7177-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="a7177-114">[Twórz przy użyciu aplikacji języka Q#](xref:microsoft.quantum.install.standalone) — wybierz tę metodę, aby korzystać z języka Q# za pomocą wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="a7177-114">[Develop with Q# applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command prompt.</span></span> <span data-ttu-id="a7177-115">W przeciwieństwie do opcji znajdujących się niżej nie wymaga to sterownika ani programu hosta.</span><span class="sxs-lookup"><span data-stu-id="a7177-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="a7177-116">[Twórz przy użyciu notesów Jupyter dla języka Q#](xref:microsoft.quantum.install.jupyter) — wybierz to środowisko, aby uruchamiać kod Q# w komórkach z osadzonym tekstem lub tworzyć interaktywne samouczki z zakresu obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="a7177-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="a7177-117">[Twórz aplikacje za pomocą języków Q# i Python](xref:microsoft.quantum.install.python) — umożliwia połączenie języków Python i Q# w celu utworzenia programu hosta w języku Python, który wywołuje operacje w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="a7177-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="a7177-118">[Twórz aplikacje za pomocą języków Q# i .NET](xref:microsoft.quantum.install.cs) — połącz języki C#, F# lub VB.NET z językiem Q# w celu utworzenia programu hosta platformy .NET, który wywołuje operacje w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="a7177-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
