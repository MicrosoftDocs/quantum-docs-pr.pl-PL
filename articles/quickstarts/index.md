---
title: Konfigurowanie zestawu Microsoft Quantum Development Kit (QDK)
description: Dowiedz się, jak skonfigurować zestaw Microsoft Quantum Development Kit dla różnych środowisk.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859021"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="0aeb7-103">Konfigurowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="0aeb7-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="0aeb7-104">Dowiedz się, jak skonfigurować zestaw Microsoft Quantum Development Kit (QDK) dla swojego środowiska, aby rozpocząć pracę z programowaniem kwantowym.</span><span class="sxs-lookup"><span data-stu-id="0aeb7-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="0aeb7-105">Zestaw QDK składa się z:</span><span class="sxs-lookup"><span data-stu-id="0aeb7-105">The QDK consists of:</span></span>

- <span data-ttu-id="0aeb7-106">Język programowania Q#</span><span class="sxs-lookup"><span data-stu-id="0aeb7-106">The Q# programming language</span></span>
- <span data-ttu-id="0aeb7-107">Zestaw bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#</span><span class="sxs-lookup"><span data-stu-id="0aeb7-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="0aeb7-108">Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="0aeb7-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="0aeb7-109">Narzędzia ułatwiające programowanie</span><span class="sxs-lookup"><span data-stu-id="0aeb7-109">Tools to facilitate your development</span></span>

<span data-ttu-id="0aeb7-110">Programy w języku Q# mogą działać jako aplikacje autonomiczne przy użyciu programu Visual Studio Code lub Visual Studio albo za pośrednictwem notesów Jupyter Notebook za pomocą jądra Jupyter IQ# lub sparowane z programem nadrzędnym napisanym w języku Python lub języku platformy .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="0aeb7-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="0aeb7-111">Możesz również uruchamiać programy w języku Q# w trybie online, używając platform [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) lub [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="0aeb7-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="0aeb7-112">Opcje konfigurowania zestawu QDK</span><span class="sxs-lookup"><span data-stu-id="0aeb7-112">Options for setting up the QDK</span></span>

<span data-ttu-id="0aeb7-113">Zestawu QDK można używać na trzy sposoby:</span><span class="sxs-lookup"><span data-stu-id="0aeb7-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="0aeb7-114">Instalowanie zestawu QDK lokalnie</span><span class="sxs-lookup"><span data-stu-id="0aeb7-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="0aeb7-115">Używanie zestawu QDK online</span><span class="sxs-lookup"><span data-stu-id="0aeb7-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="0aeb7-116">Używanie obrazu platformy Docker zestawu QDK</span><span class="sxs-lookup"><span data-stu-id="0aeb7-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="0aeb7-117">Instalowanie zestawu QDK lokalnie</span><span class="sxs-lookup"><span data-stu-id="0aeb7-117">Install the QDK locally</span></span>

<span data-ttu-id="0aeb7-118">Możesz opracowywać kod w języku Q# w większości ulubionych środowisk IDE, a także integrować język Q# z innymi językami, takimi jak język Python i języki platformy .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="0aeb7-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="0aeb7-119"><b>VS Code</span><span class="sxs-lookup"><span data-stu-id="0aeb7-119"><b>VS Code</span></span><br><span data-ttu-id="0aeb7-120">(2019 lub nowsza wersja)</b></span><span class="sxs-lookup"><span data-stu-id="0aeb7-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="0aeb7-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0aeb7-121"><b>Visual Studio</span></span><br><span data-ttu-id="0aeb7-122">(2019 lub nowsza wersja)</b></span><span class="sxs-lookup"><span data-stu-id="0aeb7-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="0aeb7-123"><b>Notesy programu Jupyter</b></span><span class="sxs-lookup"><span data-stu-id="0aeb7-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="0aeb7-124"><b>Wiersz polecenia</b></span><span class="sxs-lookup"><span data-stu-id="0aeb7-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="0aeb7-125"><b>Obsługa systemu operacyjnego:</b></span><span class="sxs-lookup"><span data-stu-id="0aeb7-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="0aeb7-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-127">Tylko Windows</span><span class="sxs-lookup"><span data-stu-id="0aeb7-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="0aeb7-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="0aeb7-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="0aeb7-130"><b>Autonomiczny język Q#</b></span><span class="sxs-lookup"><span data-stu-id="0aeb7-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-131"><a href="xref:microsoft.quantum.install.standalone">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-132"><a href="xref:microsoft.quantum.install.standalone">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-133"><a href="xref:microsoft.quantum.install.jupyter">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-134"><a href="xref:microsoft.quantum.install.standalone">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="0aeb7-135"><b>Język Q# i język Python</b></span><span class="sxs-lookup"><span data-stu-id="0aeb7-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-136"><a href="xref:microsoft.quantum.install.python">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-137"><a href="xref:microsoft.quantum.install.python">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-138"><a href="xref:microsoft.quantum.install.python">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-139"><a href="xref:microsoft.quantum.install.python">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="0aeb7-140"><b>Język Q# i platforma .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="0aeb7-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="0aeb7-141"><a href="xref:microsoft.quantum.install.cs">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-142"><a href="xref:microsoft.quantum.install.cs">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="0aeb7-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="0aeb7-144"><a href="xref:microsoft.quantum.install.cs">Instalacja</a></span><span class="sxs-lookup"><span data-stu-id="0aeb7-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="0aeb7-145">Używanie zestawu QDK online</span><span class="sxs-lookup"><span data-stu-id="0aeb7-145">Use the QDK Online</span></span>

<span data-ttu-id="0aeb7-146">Możesz również opracowywać kod w języku Q# bez instalowania czegokolwiek lokalnie, używając tych opcji:</span><span class="sxs-lookup"><span data-stu-id="0aeb7-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="0aeb7-147">Zasób</span><span class="sxs-lookup"><span data-stu-id="0aeb7-147">Resource</span></span>|<span data-ttu-id="0aeb7-148">Zalety</span><span class="sxs-lookup"><span data-stu-id="0aeb7-148">Advantages</span></span>|<span data-ttu-id="0aeb7-149">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="0aeb7-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="0aeb7-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="0aeb7-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="0aeb7-151">Zaawansowane środowisko deweloperskie online</span><span class="sxs-lookup"><span data-stu-id="0aeb7-151">A rich online development environment</span></span>  |<span data-ttu-id="0aeb7-152">Wymaga planu i subskrypcji platformy Azure</span><span class="sxs-lookup"><span data-stu-id="0aeb7-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="0aeb7-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="0aeb7-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="0aeb7-154">Bezpłatne środowisko notesu online</span><span class="sxs-lookup"><span data-stu-id="0aeb7-154">Free online notebook experience</span></span> |<span data-ttu-id="0aeb7-155">Bez trwałości</span><span class="sxs-lookup"><span data-stu-id="0aeb7-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="0aeb7-156">Używanie zestawu QDK z platformą Docker</span><span class="sxs-lookup"><span data-stu-id="0aeb7-156">Use the QDK with Docker</span></span>

<span data-ttu-id="0aeb7-157">Można użyć naszego obrazu platformy Docker zestawu QDK w lokalnej instalacji platformy Docker lub w chmurze za pośrednictwem dowolnej usługi, która obsługuje obrazy platformy Docker, takiej jak ACI.</span><span class="sxs-lookup"><span data-stu-id="0aeb7-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="0aeb7-158">Obraz platformy Docker języka IQ# można pobrać z witryny https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="0aeb7-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="0aeb7-159">Możesz również używać platformy Docker z kontenerem programowania zdalnego programu Visual Studio Code, aby szybko definiować środowiska deweloperskie.</span><span class="sxs-lookup"><span data-stu-id="0aeb7-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="0aeb7-160">Aby uzyskać więcej informacji o kontenerach programowania VS Code, zobacz https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="0aeb7-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0aeb7-161">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="0aeb7-161">Next steps</span></span>

<span data-ttu-id="0aeb7-162">Przepływy pracy dla każdej z tych konfiguracji są opisane i porównane w sekcji [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="0aeb7-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
