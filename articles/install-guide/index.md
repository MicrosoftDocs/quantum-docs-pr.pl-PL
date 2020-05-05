---
title: Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK)
description: Jak zainstalować zestaw Microsoft Quantum Development Kit dla środowisk C#, Python i Jupyter Notebook.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680195"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="3e70d-103">Instalowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="3e70d-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="3e70d-104">Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym.</span><span class="sxs-lookup"><span data-stu-id="3e70d-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="3e70d-105">Zestaw QDK składa się z:</span><span class="sxs-lookup"><span data-stu-id="3e70d-105">The QDK consists of:</span></span>

- <span data-ttu-id="3e70d-106">języka programowania Q#</span><span class="sxs-lookup"><span data-stu-id="3e70d-106">the Q# programming language</span></span>
- <span data-ttu-id="3e70d-107">zestawu bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#</span><span class="sxs-lookup"><span data-stu-id="3e70d-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="3e70d-108">Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="3e70d-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="3e70d-109">narzędzia ułatwiające programowanie</span><span class="sxs-lookup"><span data-stu-id="3e70d-109">tools to facilitate your development</span></span>

<span data-ttu-id="3e70d-110">Programy Q# są często parowane z programem hosta napisanym w języku .NET (zazwyczaj C#) lub Python.</span><span class="sxs-lookup"><span data-stu-id="3e70d-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="3e70d-111">Pozwala to na wywoływanie operacji kwantowych z poziomu klasycznego programu.</span><span class="sxs-lookup"><span data-stu-id="3e70d-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="3e70d-112">Ponadto zestaw QDK zapewnia obsługę języka Q# przez notesy Jupyter przy użyciu jądra Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="3e70d-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="3e70d-113">Zestaw QDK jest dostępny dla wielu środowisk projektowych.</span><span class="sxs-lookup"><span data-stu-id="3e70d-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="3e70d-114">Wybierz preferowaną konfigurację z poniższych sekcji:</span><span class="sxs-lookup"><span data-stu-id="3e70d-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="3e70d-115">[Aplikacja wiersza polecenia dla języka Q#:](xref:microsoft.quantum.install.standalone) wybierz tę metodę, jeśli chcesz korzystać z języka Q# za pomocą wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="3e70d-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="3e70d-116">W przeciwieństwie do opcji znajdujących się niżej nie wymaga to sterownika ani programu hosta.</span><span class="sxs-lookup"><span data-stu-id="3e70d-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="3e70d-117">[Zainstaluj język Q# dla notesów Jupyter:](xref:microsoft.quantum.install.jupyter) wybierz to środowisko, aby wykonywać kod Q# w komórkach z osadzonym tekstem lub tworzyć interaktywne samouczki z zakresu obliczeń kwantowych.</span><span class="sxs-lookup"><span data-stu-id="3e70d-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="3e70d-118">[Twórz aplikacje za pomocą języków Q# i Python:](xref:microsoft.quantum.install.python) wybierz tę metodę, jeśli chcesz połączyć języki Python i Q# w celu utworzenia programu hosta w języku Python, który wywołuje operacje w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="3e70d-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="3e70d-119">[Twórz aplikacje za pomocą języków Q# i C# lub F#:](xref:microsoft.quantum.install.cs) wybierz tę metodę, jeśli chcesz połączyć języki C# lub F# i Q# w celu utworzenia programu hosta platformy .NET, który wywołuje operacje w języku Q#.</span><span class="sxs-lookup"><span data-stu-id="3e70d-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
