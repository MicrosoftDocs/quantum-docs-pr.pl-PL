---
title: 'Korzystanie z dodatkowych bibliotek Q #'
description: 'Dowiedz się, jak dodać dodatkowe biblioteki Q # do aplikacji Quantum.'
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
ms.openlocfilehash: b82113b925870d07c8a28aecd50176e009826062
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86872638"
---
# <a name="using-additional-q-libraries"></a><span data-ttu-id="a3ef8-103">Korzystanie z dodatkowych bibliotek Q #</span><span class="sxs-lookup"><span data-stu-id="a3ef8-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="a3ef8-104">Zestaw Quantum Development Kit udostępnia dodatkowe funkcje specyficzne dla domeny za pomocą _pakietów NuGet_ , które można dodać do projektów Q #.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="a3ef8-105">Biblioteka Q #</span><span class="sxs-lookup"><span data-stu-id="a3ef8-105">Q# Library</span></span>  | <span data-ttu-id="a3ef8-106">Pakiet NuGet</span><span class="sxs-lookup"><span data-stu-id="a3ef8-106">NuGet package</span></span> | <span data-ttu-id="a3ef8-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a3ef8-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="a3ef8-108">Standardowa biblioteka Q</span><span class="sxs-lookup"><span data-stu-id="a3ef8-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="a3ef8-109">**Microsoft. Quantum. Standard**</span><span class="sxs-lookup"><span data-stu-id="a3ef8-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="a3ef8-110">Uwzględnione domyślnie</span><span class="sxs-lookup"><span data-stu-id="a3ef8-110">Included by default</span></span> |
| [<span data-ttu-id="a3ef8-111">Biblioteka dla chemii kwantowej</span><span class="sxs-lookup"><span data-stu-id="a3ef8-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="a3ef8-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="a3ef8-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="a3ef8-113">Biblioteka dla liczb kwantowych</span><span class="sxs-lookup"><span data-stu-id="a3ef8-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="a3ef8-114">**Microsoft. Quantum. Numerics**</span><span class="sxs-lookup"><span data-stu-id="a3ef8-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="a3ef8-115">Biblioteka dla kwantowego uczenia maszynowego</span><span class="sxs-lookup"><span data-stu-id="a3ef8-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="a3ef8-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="a3ef8-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="a3ef8-117">Po zainstalowaniu zestawu Quantum Development Kit do użycia z preferowanym środowiskiem i językiem hosta możesz łatwo dodać biblioteki do poszczególnych projektów Q # bez żadnej dalszej instalacji.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="a3ef8-118">Niektóre biblioteki Q # mogą współpracować z dodatkowymi narzędziami, które działają razem z programami Q # lub które integrują się z aplikacjami hosta.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="a3ef8-119">Na przykład [instrukcje instalacji biblioteki chemicznej](xref:microsoft.quantum.chemistry.concepts.installation) opisują, jak używać pakietu [ **Microsoft. Quantum. chemii** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) wraz z NWChem obliczeniową, a także jak instalować `qdk-chem` narzędzia wiersza polecenia do pracy z danymi chemii Quantum.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="q-command-line-applications-or-net-interopability"></a>[<span data-ttu-id="a3ef8-120">Q # aplikacje wiersza polecenia lub .NET Interop</span><span class="sxs-lookup"><span data-stu-id="a3ef8-120">Q# command-line applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="a3ef8-121">**Wiersz polecenia lub Visual Studio Code:** Przy użyciu wiersza polecenia lub z poziomu Visual Studio Code można użyć `dotnet` polecenia, aby dodać odwołanie do pakietu NuGet do projektu.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-121">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="a3ef8-122">Aby na przykład dodać pakiet [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) , uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="a3ef8-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="a3ef8-123">**Program Visual Studio:** Jeśli używasz programu Visual Studio 2019 lub nowszego, możesz dodać dodatkowe pakiety Q # przy użyciu Menedżera pakietów NuGet.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="a3ef8-124">Aby załadować pakiet:</span><span class="sxs-lookup"><span data-stu-id="a3ef8-124">To load a package:</span></span> 
1. <span data-ttu-id="a3ef8-125">Mając otwarty projekt w programie Visual Studio, wybierz pozycję **Zarządzaj pakietami NuGet...** z menu **projekt** .</span><span class="sxs-lookup"><span data-stu-id="a3ef8-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="a3ef8-126">Kliknij przycisk **Przeglądaj**, wybierz opcję **Uwzględnij wersję wstępną** i wyszukaj nazwę pakietu "Microsoft. Quantum. Numerics".</span><span class="sxs-lookup"><span data-stu-id="a3ef8-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="a3ef8-127">Spowoduje to wyświetlenie listy pakietów dostępnych do pobrania.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="a3ef8-128">Zatrzymaj wskaźnik myszy na **Microsoft. Quantum. Numerics** i kliknij strzałkę w dół znajdującą się po prawej stronie numeru wersji, aby zainstalować pakiet liczbowy.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="a3ef8-129">Aby uzyskać więcej informacji, zobacz [Przewodnik po interfejsie użytkownika Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="a3ef8-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="a3ef8-130">Alternatywnie można użyć konsoli Menedżera pakietów, aby dodać bibliotekę liczbową do projektu za pomocą interfejsu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Korzystanie z konsoli Menedżera pakietów z poziomu wiersza polecenia](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="a3ef8-132">W konsoli Menedżera pakietów Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="a3ef8-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="a3ef8-133">Aby uzyskać więcej informacji, zobacz [Przewodnik po konsoli Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="a3ef8-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="iq-notebooks"></a>[<span data-ttu-id="a3ef8-134">Notesy IQ #</span><span class="sxs-lookup"><span data-stu-id="a3ef8-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="a3ef8-135">Można udostępnić dodatkowe pakiety do użycia w notesie IQ # przy użyciu [ `%package` polecenia Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="a3ef8-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="a3ef8-136">Aby na przykład dodać pakiet [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) do użycia w notesie IQ #, uruchom następujące polecenie w komórce notesu:</span><span class="sxs-lookup"><span data-stu-id="a3ef8-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="a3ef8-137">Po tym poleceniu pakiet jest dostępny dla wszystkich komórek w notesie.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="a3ef8-138">Aby udostępnić pakiet z kodu Q # w bieżącym obszarze roboczym, Załaduj ponownie obszar roboczy po dodaniu pakietu:</span><span class="sxs-lookup"><span data-stu-id="a3ef8-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="a3ef8-139">Współdziałanie języka Python</span><span class="sxs-lookup"><span data-stu-id="a3ef8-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="a3ef8-140">Dodatkowe pakiety mogą być dostępne do użycia w programie hosta Python przy użyciu [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) metody.</span><span class="sxs-lookup"><span data-stu-id="a3ef8-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="a3ef8-141">Aby na przykład dodać pakiet [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) do użycia w notesie IQ #, uruchom następujący kod w języku Python:</span><span class="sxs-lookup"><span data-stu-id="a3ef8-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="a3ef8-142">Po wykonaniu tego polecenia pakiet zostanie udostępniony dla dowolnego kodu Q # skompilowanego przy użyciu `qsharp.compile` .</span><span class="sxs-lookup"><span data-stu-id="a3ef8-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="a3ef8-143">Aby udostępnić pakiet z kodu Q # w bieżącym obszarze roboczym, Załaduj ponownie obszar roboczy po dodaniu pakietu:</span><span class="sxs-lookup"><span data-stu-id="a3ef8-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
