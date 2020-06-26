---
title: Tworzenie zawartości za pomocą języka Q# i platformy .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274152"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="abdd9-102">Tworzenie zawartości za pomocą języka Q# i platformy .NET</span><span class="sxs-lookup"><span data-stu-id="abdd9-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="abdd9-103">Język Q# został opracowany z myślą o współdziałaniu z językami platformy .NET, takimi jak C# i F#.</span><span class="sxs-lookup"><span data-stu-id="abdd9-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="abdd9-104">W tym przewodniku pokazano, jak używać języka Q# z programem hosta napisanym w języku platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="abdd9-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abdd9-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="abdd9-105">Prerequisites</span></span>

- <span data-ttu-id="abdd9-106">Zainstaluj zestaw Quantum Development Kit [do użycia z projektami wiersza polecenia w języku Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="abdd9-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="abdd9-107">Tworzenie biblioteki języka Q# i hosta platformy .NET</span><span class="sxs-lookup"><span data-stu-id="abdd9-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="abdd9-108">Pierwszym krokiem jest utworzenie projektów biblioteki języka Q# oraz hosta platformy .NET, który będzie wywoływał operacje i funkcje zdefiniowane w bibliotece języka Q#.</span><span class="sxs-lookup"><span data-stu-id="abdd9-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="abdd9-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="abdd9-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="abdd9-110">Utwórz nową bibliotekę języka Q#</span><span class="sxs-lookup"><span data-stu-id="abdd9-110">Create a new Q# library</span></span>
  - <span data-ttu-id="abdd9-111">Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="abdd9-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="abdd9-112">Wpisz „Q#” w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="abdd9-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="abdd9-113">Wybierz pozycję **Biblioteka Q#**</span><span class="sxs-lookup"><span data-stu-id="abdd9-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="abdd9-114">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="abdd9-114">Select **Next**</span></span>
  - <span data-ttu-id="abdd9-115">Wybierz nazwę i lokalizację biblioteki</span><span class="sxs-lookup"><span data-stu-id="abdd9-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="abdd9-116">Upewnij się, że pole „Umieść projekt i rozwiązanie w tym samym katalogu” jest **niezaznaczone**</span><span class="sxs-lookup"><span data-stu-id="abdd9-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="abdd9-117">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="abdd9-117">Select **Create**</span></span>
- <span data-ttu-id="abdd9-118">Utwórz nowy program hosta w języku C# lub F#</span><span class="sxs-lookup"><span data-stu-id="abdd9-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="abdd9-119">Przejdź do pozycji **Plik** → **Nowy** → **Projekt**</span><span class="sxs-lookup"><span data-stu-id="abdd9-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="abdd9-120">Wybierz pozycję „Aplikacja konsolowa (.NET Core)” dla języka C# lub F#</span><span class="sxs-lookup"><span data-stu-id="abdd9-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="abdd9-121">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="abdd9-121">Select **Next**</span></span>
  - <span data-ttu-id="abdd9-122">W obszarze *Rozwiązanie* wybierz pozycję „Dodaj do rozwiązania”</span><span class="sxs-lookup"><span data-stu-id="abdd9-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="abdd9-123">Wybierz nazwę programu hosta</span><span class="sxs-lookup"><span data-stu-id="abdd9-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="abdd9-124">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="abdd9-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="abdd9-125">Program Visual Studio Code lub wiersz polecenia</span><span class="sxs-lookup"><span data-stu-id="abdd9-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="abdd9-126">Utwórz nową bibliotekę języka Q#</span><span class="sxs-lookup"><span data-stu-id="abdd9-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="abdd9-127">Utwórz nowy projekt konsolowy języka C# lub F#</span><span class="sxs-lookup"><span data-stu-id="abdd9-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="abdd9-128">Dodaj bibliotekę języka Q# jako odwołanie w programie hosta</span><span class="sxs-lookup"><span data-stu-id="abdd9-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="abdd9-129">[Opcjonalnie] Utwórz rozwiązanie dla obu projektów</span><span class="sxs-lookup"><span data-stu-id="abdd9-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="abdd9-130">Wywoływanie funkcji języka Q# z aplikacji platformy .NET</span><span class="sxs-lookup"><span data-stu-id="abdd9-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="abdd9-131">Po skonfigurowaniu projektów zgodnie z powyższymi instrukcjami można wywoływać funkcje języka Q# z aplikacji konsolowej platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="abdd9-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="abdd9-132">Kompilator języka Q# utworzy klasy platformy .NET dla wszystkich operacji i funkcji języka Q#, co umożliwi uruchamianie programów kwantowych w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="abdd9-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="abdd9-133">[Przykład współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) zawiera następującą przykładową operację języka Q#:</span><span class="sxs-lookup"><span data-stu-id="abdd9-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="abdd9-134">Aby wywołać tę operację z poziomu aplikacji platformy .NET w symulatorze kwantowym, możesz użyć metody `Run` w klasie platformy .NET `RunAlgorithm`, wygenerowanej przez kompilator języka Q#:</span><span class="sxs-lookup"><span data-stu-id="abdd9-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="abdd9-135">C#</span><span class="sxs-lookup"><span data-stu-id="abdd9-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="abdd9-136">F#</span><span class="sxs-lookup"><span data-stu-id="abdd9-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="abdd9-137">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="abdd9-137">Next steps</span></span>

<span data-ttu-id="abdd9-138">Po skonfigurowaniu zestawu Quantum Development Kit zarówno na potrzeby programów wiersza polecenia w języku Q#, jak i współdziałania z platformą .NET, możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="abdd9-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
