---
title: Programowanie przy użyciu języka Q# i platformy .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 24318380e0e63957a51961762a33446fe0121b21
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863670"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="8d31c-102">Programowanie przy użyciu języka Q# i platformy .NET</span><span class="sxs-lookup"><span data-stu-id="8d31c-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="8d31c-103">Język Q# został opracowany z myślą o współdziałaniu z językami platformy .NET, takimi jak C# i F#.</span><span class="sxs-lookup"><span data-stu-id="8d31c-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="8d31c-104">W tym przewodniku pokazujemy, jak używać języka Q# z programem hosta napisanym w języku platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="8d31c-104">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="8d31c-105">Najpierw tworzymy aplikację w języku Q# i hosta na platformie .NET, a następnie pokazujemy, jak wywoływać język Q# z hosta.</span><span class="sxs-lookup"><span data-stu-id="8d31c-105">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d31c-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="8d31c-106">Prerequisites</span></span>

- <span data-ttu-id="8d31c-107">Zainstaluj zestaw Quantum Development Kit [do użycia z projektami w języku Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="8d31c-107">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="8d31c-108">Tworzenie biblioteki języka Q# i hosta platformy .NET</span><span class="sxs-lookup"><span data-stu-id="8d31c-108">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="8d31c-109">Pierwszym krokiem jest utworzenie projektów biblioteki języka Q# oraz hosta platformy .NET, który będzie wywoływał operacje i funkcje zdefiniowane w bibliotece języka Q#.</span><span class="sxs-lookup"><span data-stu-id="8d31c-109">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="8d31c-110">Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku programistycznemu.</span><span class="sxs-lookup"><span data-stu-id="8d31c-110">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="8d31c-111">Jeśli używasz edytora innego niż Visual Studio lub VS Code, po prostu postępuj zgodnie z krokami wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="8d31c-111">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="8d31c-112">Program Visual Studio Code lub wiersz polecenia</span><span class="sxs-lookup"><span data-stu-id="8d31c-112">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="8d31c-113">Utwórz nową bibliotekę języka Q#</span><span class="sxs-lookup"><span data-stu-id="8d31c-113">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="8d31c-114">Utwórz nowy projekt konsolowy języka C# lub F#</span><span class="sxs-lookup"><span data-stu-id="8d31c-114">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="8d31c-115">Dodaj bibliotekę języka Q# jako odwołanie w programie hosta</span><span class="sxs-lookup"><span data-stu-id="8d31c-115">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="8d31c-116">[Opcjonalnie] Utwórz rozwiązanie dla obu projektów</span><span class="sxs-lookup"><span data-stu-id="8d31c-116">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="8d31c-117">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="8d31c-117">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="8d31c-118">Utwórz nową bibliotekę języka Q#</span><span class="sxs-lookup"><span data-stu-id="8d31c-118">Create a new Q# library</span></span>
  - <span data-ttu-id="8d31c-119">Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**</span><span class="sxs-lookup"><span data-stu-id="8d31c-119">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="8d31c-120">Wpisz „Q#” w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="8d31c-120">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="8d31c-121">Wybierz pozycję **Biblioteka języka Q#**</span><span class="sxs-lookup"><span data-stu-id="8d31c-121">Select **Q# Library**</span></span>
  - <span data-ttu-id="8d31c-122">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="8d31c-122">Select **Next**</span></span>
  - <span data-ttu-id="8d31c-123">Wybierz nazwę i lokalizację biblioteki</span><span class="sxs-lookup"><span data-stu-id="8d31c-123">Choose a name and location for your library</span></span>
  - <span data-ttu-id="8d31c-124">Upewnij się, że pole „Umieść projekt i rozwiązanie w tym samym katalogu” jest **niezaznaczone**</span><span class="sxs-lookup"><span data-stu-id="8d31c-124">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="8d31c-125">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="8d31c-125">Select **Create**</span></span>
- <span data-ttu-id="8d31c-126">Utwórz nowy program hosta w języku C# lub F#</span><span class="sxs-lookup"><span data-stu-id="8d31c-126">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="8d31c-127">Przejdź do pozycji **Plik** → **Nowy** → **Projekt**</span><span class="sxs-lookup"><span data-stu-id="8d31c-127">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="8d31c-128">Wybierz pozycję „Aplikacja konsolowa (.NET Core)” dla języka C# lub F#</span><span class="sxs-lookup"><span data-stu-id="8d31c-128">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="8d31c-129">Wybierz pozycję **Dalej**</span><span class="sxs-lookup"><span data-stu-id="8d31c-129">Select **Next**</span></span>
  - <span data-ttu-id="8d31c-130">W obszarze *Rozwiązanie* wybierz pozycję „Dodaj do rozwiązania”</span><span class="sxs-lookup"><span data-stu-id="8d31c-130">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="8d31c-131">Wybierz nazwę programu hosta</span><span class="sxs-lookup"><span data-stu-id="8d31c-131">Choose a name for your host program</span></span>
  - <span data-ttu-id="8d31c-132">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="8d31c-132">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="8d31c-133">Wywoływanie funkcji języka Q# z aplikacji platformy .NET</span><span class="sxs-lookup"><span data-stu-id="8d31c-133">Calling into Q# from .NET</span></span>

<span data-ttu-id="8d31c-134">Po skonfigurowaniu projektów zgodnie z powyższymi instrukcjami można wywoływać funkcje języka Q# z aplikacji konsolowej platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="8d31c-134">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="8d31c-135">Kompilator języka Q# utworzy klasy platformy .NET dla wszystkich operacji i funkcji języka Q#, co umożliwi uruchamianie programów kwantowych w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="8d31c-135">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="8d31c-136">[Przykład współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) zawiera następującą przykładową operację języka Q#:</span><span class="sxs-lookup"><span data-stu-id="8d31c-136">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="8d31c-137">Aby wywołać tę operację z poziomu aplikacji platformy .NET w symulatorze kwantowym, możesz użyć metody `Run` w klasie platformy .NET `RunAlgorithm` wygenerowanej przez kompilator języka Q#:</span><span class="sxs-lookup"><span data-stu-id="8d31c-137">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="8d31c-138">C#</span><span class="sxs-lookup"><span data-stu-id="8d31c-138">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="8d31c-139">F#</span><span class="sxs-lookup"><span data-stu-id="8d31c-139">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="8d31c-140">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="8d31c-140">Next steps</span></span>

<span data-ttu-id="8d31c-141">Po skonfigurowaniu zestawu Quantum Development Kit zarówno na potrzeby aplikacji w języku Q#, jak i współdziałania z platformą .NET, możesz napisać i uruchomić swój [pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="8d31c-141">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
