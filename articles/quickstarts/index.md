---
title: Konfigurowanie zestawu Microsoft Quantum Development Kit (QDK)
description: Dowiedz się, jak skonfigurować zestaw Microsoft Quantum Development Kit dla różnych środowisk.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834486"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="305cf-103">Konfigurowanie zestawu Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="305cf-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="305cf-104">Dowiedz się, jak skonfigurować zestaw Microsoft Quantum Development Kit (QDK) dla swojego środowiska, aby rozpocząć pracę z programowaniem kwantowym.</span><span class="sxs-lookup"><span data-stu-id="305cf-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="305cf-105">Zestaw QDK składa się z:</span><span class="sxs-lookup"><span data-stu-id="305cf-105">The QDK consists of:</span></span>

- <span data-ttu-id="305cf-106">Język programowania Q#</span><span class="sxs-lookup"><span data-stu-id="305cf-106">The Q# programming language</span></span>
- <span data-ttu-id="305cf-107">Zestaw bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#</span><span class="sxs-lookup"><span data-stu-id="305cf-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="305cf-108">Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#</span><span class="sxs-lookup"><span data-stu-id="305cf-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="305cf-109">Narzędzia ułatwiające programowanie</span><span class="sxs-lookup"><span data-stu-id="305cf-109">Tools to facilitate your development</span></span>

<span data-ttu-id="305cf-110">Programy w języku Q# mogą działać jako aplikacje autonomiczne przy użyciu programu Visual Studio Code lub Visual Studio albo za pośrednictwem notesów Jupyter Notebook za pomocą jądra Jupyter IQ# lub sparowane z programem nadrzędnym napisanym w języku Python lub języku platformy .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="305cf-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="305cf-111">Możesz również uruchamiać programy w języku Q# w trybie online, używając platform [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) lub [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="305cf-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="305cf-112">Opcje konfigurowania zestawu QDK</span><span class="sxs-lookup"><span data-stu-id="305cf-112">Options for setting up the QDK</span></span>

<span data-ttu-id="305cf-113">Zestawu QDK można używać na trzy sposoby:</span><span class="sxs-lookup"><span data-stu-id="305cf-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="305cf-114">Instalowanie zestawu QDK lokalnie</span><span class="sxs-lookup"><span data-stu-id="305cf-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="305cf-115">Używanie zestawu QDK online</span><span class="sxs-lookup"><span data-stu-id="305cf-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="305cf-116">Używanie obrazu platformy Docker zestawu QDK</span><span class="sxs-lookup"><span data-stu-id="305cf-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="305cf-117">Instalowanie zestawu QDK lokalnie</span><span class="sxs-lookup"><span data-stu-id="305cf-117">Install the QDK locally</span></span>

<span data-ttu-id="305cf-118">Możesz opracowywać kod w języku Q# w większości ulubionych środowisk IDE, a także integrować język Q# z innymi językami, takimi jak język Python i języki platformy .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="305cf-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="305cf-119">**VS Code<br>(2019 lub nowszy)**</span><span class="sxs-lookup"><span data-stu-id="305cf-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="305cf-120">**Visual Studio<br>(2019 lub nowszy)**</span><span class="sxs-lookup"><span data-stu-id="305cf-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="305cf-121">**Notesy programu Jupyter**</span><span class="sxs-lookup"><span data-stu-id="305cf-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="305cf-122">**Wiersz polecenia**</span><span class="sxs-lookup"><span data-stu-id="305cf-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="305cf-123">**System operacyjny**</span><span class="sxs-lookup"><span data-stu-id="305cf-123">**OS**</span></span> |<span data-ttu-id="305cf-124">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="305cf-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="305cf-125">Tylko Windows</span><span class="sxs-lookup"><span data-stu-id="305cf-125">Windows only</span></span> |<span data-ttu-id="305cf-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="305cf-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="305cf-127">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="305cf-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="305cf-128">**Autonomiczny język Q#**</span><span class="sxs-lookup"><span data-stu-id="305cf-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="305cf-129">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="305cf-130">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="305cf-131">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="305cf-132">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="305cf-133">**Język Q# i język Python**</span><span class="sxs-lookup"><span data-stu-id="305cf-133">**Q#  and Python**</span></span> |[<span data-ttu-id="305cf-134">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="305cf-135">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="305cf-136">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="305cf-137">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="305cf-138">**Język Q# i platforma .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="305cf-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="305cf-139">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="305cf-140">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="305cf-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="305cf-141">&#10006;</span></span> |[<span data-ttu-id="305cf-142">Instalacja</span><span class="sxs-lookup"><span data-stu-id="305cf-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="305cf-143">Używanie zestawu QDK online</span><span class="sxs-lookup"><span data-stu-id="305cf-143">Use the QDK Online</span></span>

<span data-ttu-id="305cf-144">Możesz również opracowywać kod w języku Q# bez instalowania czegokolwiek lokalnie, używając tych opcji:</span><span class="sxs-lookup"><span data-stu-id="305cf-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="305cf-145">Zasób</span><span class="sxs-lookup"><span data-stu-id="305cf-145">Resource</span></span>|<span data-ttu-id="305cf-146">Zalety</span><span class="sxs-lookup"><span data-stu-id="305cf-146">Advantages</span></span>|<span data-ttu-id="305cf-147">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="305cf-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="305cf-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="305cf-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="305cf-149">Zaawansowane środowisko deweloperskie online</span><span class="sxs-lookup"><span data-stu-id="305cf-149">A rich online development environment</span></span>  |<span data-ttu-id="305cf-150">Wymaga planu i subskrypcji platformy Azure</span><span class="sxs-lookup"><span data-stu-id="305cf-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="305cf-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="305cf-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="305cf-152">Bezpłatne środowisko notesu online</span><span class="sxs-lookup"><span data-stu-id="305cf-152">Free online notebook experience</span></span> |<span data-ttu-id="305cf-153">Bez trwałości</span><span class="sxs-lookup"><span data-stu-id="305cf-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="305cf-154">Używanie zestawu QDK z platformą Docker</span><span class="sxs-lookup"><span data-stu-id="305cf-154">Use the QDK with Docker</span></span>

<span data-ttu-id="305cf-155">Można użyć naszego obrazu platformy Docker zestawu QDK w lokalnej instalacji platformy Docker lub w chmurze za pośrednictwem dowolnej usługi, która obsługuje obrazy platformy Docker, takiej jak ACI.</span><span class="sxs-lookup"><span data-stu-id="305cf-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="305cf-156">Obraz platformy Docker języka IQ# można pobrać z witryny https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="305cf-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="305cf-157">Możesz również używać platformy Docker z kontenerem programowania zdalnego programu Visual Studio Code, aby szybko definiować środowiska deweloperskie.</span><span class="sxs-lookup"><span data-stu-id="305cf-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="305cf-158">Aby uzyskać więcej informacji o kontenerach programowania VS Code, zobacz https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="305cf-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="305cf-159">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="305cf-159">Next steps</span></span>

<span data-ttu-id="305cf-160">Przepływy pracy dla każdej z tych konfiguracji są opisane i porównane w sekcji [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="305cf-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
