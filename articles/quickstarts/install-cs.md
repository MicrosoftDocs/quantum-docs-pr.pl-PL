---
title: Programowanie przy użyciu języka Q# i platformy .NET
description: Dowiedz się, jak utworzyć aplikację Q# przy użyciu języków platformy .NET.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: de79c361331766572f5608c341be766e071e01b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844306"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="47890-103">Programowanie przy użyciu języka Q# i platformy .NET</span><span class="sxs-lookup"><span data-stu-id="47890-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="47890-104">Język Q# został opracowany z myślą o współdziałaniu z językami platformy .NET, takimi jak C# i F#.</span><span class="sxs-lookup"><span data-stu-id="47890-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="47890-105">W tym przewodniku pokazujemy, jak używać języka Q# z programem hosta napisanym w języku platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="47890-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="47890-106">Najpierw tworzymy aplikację w języku Q# i hosta na platformie .NET, a następnie pokazujemy, jak wywoływać język Q# z hosta.</span><span class="sxs-lookup"><span data-stu-id="47890-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="47890-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="47890-107">Prerequisites</span></span>

- <span data-ttu-id="47890-108">Zainstaluj zestaw Quantum Development Kit [do użycia z projektami w języku Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="47890-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="47890-109">Tworzenie biblioteki języka Q# i hosta platformy .NET</span><span class="sxs-lookup"><span data-stu-id="47890-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="47890-110">Pierwszym krokiem jest utworzenie projektów biblioteki języka Q# oraz hosta platformy .NET, który będzie wywoływał operacje i funkcje zdefiniowane w bibliotece języka Q#.</span><span class="sxs-lookup"><span data-stu-id="47890-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="47890-111">Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku programistycznemu.</span><span class="sxs-lookup"><span data-stu-id="47890-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="47890-112">Jeśli używasz edytora innego niż Visual Studio lub VS Code, po prostu postępuj zgodnie z krokami wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="47890-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="47890-113">Program Visual Studio Code lub wiersz polecenia</span><span class="sxs-lookup"><span data-stu-id="47890-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="47890-114">Utwórz nową bibliotekę języka Q#</span><span class="sxs-lookup"><span data-stu-id="47890-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="47890-115">Utwórz nowy projekt konsolowy języka C# lub F#</span><span class="sxs-lookup"><span data-stu-id="47890-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="47890-116">Dodaj bibliotekę języka Q# jako odwołanie w programie hosta</span><span class="sxs-lookup"><span data-stu-id="47890-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="47890-117">[Opcjonalnie] Utwórz rozwiązanie dla obu projektów</span><span class="sxs-lookup"><span data-stu-id="47890-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="47890-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="47890-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="47890-119">Utwórz nową bibliotekę języka Q#</span><span class="sxs-lookup"><span data-stu-id="47890-119">Create a new Q# library</span></span>
  - <span data-ttu-id="47890-120">Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="47890-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="47890-121">Wpisz „Q#” w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="47890-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="47890-122">Wybierz pozycję **Biblioteka języka Q#**</span><span class="sxs-lookup"><span data-stu-id="47890-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="47890-123">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="47890-123">Select **Next**</span></span>
  - <span data-ttu-id="47890-124">Wybierz nazwę i lokalizację biblioteki</span><span class="sxs-lookup"><span data-stu-id="47890-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="47890-125">Upewnij się, że pole „Umieść projekt i rozwiązanie w tym samym katalogu” jest **niezaznaczone**</span><span class="sxs-lookup"><span data-stu-id="47890-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="47890-126">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="47890-126">Select **Create**</span></span>
- <span data-ttu-id="47890-127">Utwórz nowy program hosta w języku C# lub F#</span><span class="sxs-lookup"><span data-stu-id="47890-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="47890-128">Przejdź do pozycji **Plik** → **Nowy** → **Projekt**</span><span class="sxs-lookup"><span data-stu-id="47890-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="47890-129">Wybierz pozycję „Aplikacja konsolowa (.NET Core)” dla języka C# lub F#</span><span class="sxs-lookup"><span data-stu-id="47890-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="47890-130">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="47890-130">Select **Next**</span></span>
  - <span data-ttu-id="47890-131">W obszarze *Rozwiązanie* wybierz pozycję „Dodaj do rozwiązania”</span><span class="sxs-lookup"><span data-stu-id="47890-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="47890-132">Wybierz nazwę programu hosta</span><span class="sxs-lookup"><span data-stu-id="47890-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="47890-133">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="47890-133">Select **Create**</span></span>

<span data-ttu-id="47890-134">\*\*_</span><span class="sxs-lookup"><span data-stu-id="47890-134">\*\*_</span></span>

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="47890-135">Wywoływanie funkcji języka Q# z aplikacji platformy .NET</span><span class="sxs-lookup"><span data-stu-id="47890-135">Calling into Q# from .NET</span></span>

<span data-ttu-id="47890-136">Po skonfigurowaniu projektów zgodnie z powyższymi instrukcjami można wywoływać funkcje języka Q# z aplikacji konsolowej platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="47890-136">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="47890-137">Kompilator języka Q# utworzy klasy platformy .NET dla wszystkich operacji i funkcji języka Q#, co umożliwi uruchamianie programów kwantowych w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="47890-137">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="47890-138">[Przykład współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) zawiera następującą przykładową operację języka Q#:</span><span class="sxs-lookup"><span data-stu-id="47890-138">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="47890-139">Aby wywołać tę operację z poziomu aplikacji platformy .NET w symulatorze kwantowym, możesz użyć metody `Run` w klasie platformy .NET `RunAlgorithm` wygenerowanej przez kompilator języka Q#:</span><span class="sxs-lookup"><span data-stu-id="47890-139">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="47890-140">C#</span><span class="sxs-lookup"><span data-stu-id="47890-140">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="47890-141">F#</span><span class="sxs-lookup"><span data-stu-id="47890-141">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

<span data-ttu-id="47890-142">_\*\*</span><span class="sxs-lookup"><span data-stu-id="47890-142">_\*\*</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="47890-143">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="47890-143">Next steps</span></span>

<span data-ttu-id="47890-144">Po skonfigurowaniu zestawu Quantum Development Kit zarówno na potrzeby aplikacji w języku Q#, jak i współdziałania z platformą .NET, możesz napisać i uruchomić swój [pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="47890-144">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
