---
title: Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 0e9dd1c74316eeb1fa7bbbf657d2e78231ee4294
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036512"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="23de7-102">Instalowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="23de7-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="23de7-103">Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym.</span><span class="sxs-lookup"><span data-stu-id="23de7-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="23de7-104">Zestaw QDK składa się z:</span><span class="sxs-lookup"><span data-stu-id="23de7-104">The QDK consists of:</span></span>

- <span data-ttu-id="23de7-105">języka programowania Q#</span><span class="sxs-lookup"><span data-stu-id="23de7-105">the Q# programming language</span></span>
- <span data-ttu-id="23de7-106">zestawu bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#</span><span class="sxs-lookup"><span data-stu-id="23de7-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="23de7-107">Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="23de7-107">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="23de7-108">narzędzia ułatwiające programowanie</span><span class="sxs-lookup"><span data-stu-id="23de7-108">tools to facilitate your development</span></span>

<span data-ttu-id="23de7-109">Programy Q# są często parowane z programem hosta napisanym w języku .NET (zazwyczaj C#) lub Python.</span><span class="sxs-lookup"><span data-stu-id="23de7-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="23de7-110">Pozwala to na wywoływanie operacji kwantowych z poziomu klasycznego programu.</span><span class="sxs-lookup"><span data-stu-id="23de7-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="23de7-111">Ponadto zestaw QDK zapewnia obsługę języka Q# przez notesy Jupyter przy użyciu jądra Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="23de7-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="23de7-112">Zestaw QDK jest dostępny dla wielu środowisk projektowych.</span><span class="sxs-lookup"><span data-stu-id="23de7-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="23de7-113">Wybierz preferowaną konfigurację z poniższych sekcji:</span><span class="sxs-lookup"><span data-stu-id="23de7-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="23de7-114">[Zainstaluj język Q# dla języka C#:](xref:microsoft.quantum.install.cs) wybierz to środowisko, jeśli chcesz połączyć języki C# i Q# w celu utworzenia programu hosta w języku C#, który wywołuje operacje w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="23de7-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="23de7-115">[Zainstaluj język Q# dla języka Python:](xref:microsoft.quantum.install.python) wybierz to środowisko, jeśli chcesz połączyć języki Python i Q# w celu utworzenia programu hosta w języku Python, który wywołuje operacje w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="23de7-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="23de7-116">[Zainstaluj język Q# dla notesów Jupyter:](xref:microsoft.quantum.install.jupyter) wybierz to środowisko, aby wykonywać kod Q# w komórkach z osadzonym tekstem lub tworzyć interaktywne samouczki z zakresu obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="23de7-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="23de7-117">Nie wybieraj tego środowiska, jeśli chcesz połączyć język Q# z zewnętrznym klasycznym programem hosta.</span><span class="sxs-lookup"><span data-stu-id="23de7-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
