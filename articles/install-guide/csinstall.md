---
title: Tworzenie zawartości za pomocą języka Q# i platformy .NET
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 155367dbb1373f00e2b0bd732a5319b32462c9f9
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426500"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="7218e-102">Tworzenie zawartości za pomocą języka Q# i platformy .NET</span><span class="sxs-lookup"><span data-stu-id="7218e-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="7218e-103">Program Q # jest zbudowany z użyciem języków .NET, takich jak C# i F #.</span><span class="sxs-lookup"><span data-stu-id="7218e-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="7218e-104">W tym przewodniku pokazano, jak używać Q # z programem hosta zapisaną w języku .NET.</span><span class="sxs-lookup"><span data-stu-id="7218e-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7218e-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="7218e-105">Prerequisites</span></span>

- <span data-ttu-id="7218e-106">Zainstaluj zestaw Quantum Development Kit [do użycia z projektami wiersza polecenia Q #](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="7218e-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="7218e-107">Tworzenie biblioteki Q # i hosta .NET</span><span class="sxs-lookup"><span data-stu-id="7218e-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="7218e-108">Pierwszym krokiem jest utworzenie projektów dla biblioteki Q # oraz dla hosta .NET, który będzie wywoływał operacje i funkcje zdefiniowane w bibliotece Q #.</span><span class="sxs-lookup"><span data-stu-id="7218e-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="7218e-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="7218e-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="7218e-110">Utwórz nową bibliotekę Q #</span><span class="sxs-lookup"><span data-stu-id="7218e-110">Create a new Q# library</span></span>
  - <span data-ttu-id="7218e-111">Przejdź do **pliku**  ->  **Nowy**  ->  **projekt**</span><span class="sxs-lookup"><span data-stu-id="7218e-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="7218e-112">Wpisz "Q #" w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="7218e-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="7218e-113">Wybierz **bibliotekę Q #**</span><span class="sxs-lookup"><span data-stu-id="7218e-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="7218e-114">Wybierz pozycję **dalej**</span><span class="sxs-lookup"><span data-stu-id="7218e-114">Select **Next**</span></span>
  - <span data-ttu-id="7218e-115">Wybierz nazwę i lokalizację biblioteki</span><span class="sxs-lookup"><span data-stu-id="7218e-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="7218e-116">Upewnij się, że pole "Umieść projekt i rozwiązanie w tym samym katalogu" nie jest **zaznaczone**</span><span class="sxs-lookup"><span data-stu-id="7218e-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="7218e-117">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="7218e-117">Select **Create**</span></span>
- <span data-ttu-id="7218e-118">Tworzenie nowego programu hosta C# lub F #</span><span class="sxs-lookup"><span data-stu-id="7218e-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="7218e-119">Przejdź do **pliku** → **Nowy** → **projekt**</span><span class="sxs-lookup"><span data-stu-id="7218e-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="7218e-120">Wybierz pozycję "Aplikacja konsolowa (.NET Core") dla języka C# lub F #</span><span class="sxs-lookup"><span data-stu-id="7218e-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="7218e-121">Wybierz pozycję **dalej**</span><span class="sxs-lookup"><span data-stu-id="7218e-121">Select **Next**</span></span>
  - <span data-ttu-id="7218e-122">W obszarze *rozwiązanie*wybierz pozycję "Dodaj do rozwiązania".</span><span class="sxs-lookup"><span data-stu-id="7218e-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="7218e-123">Wybierz nazwę programu hosta</span><span class="sxs-lookup"><span data-stu-id="7218e-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="7218e-124">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="7218e-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="7218e-125">Visual Studio Code lub wiersz polecenia</span><span class="sxs-lookup"><span data-stu-id="7218e-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="7218e-126">Utwórz nową bibliotekę Q #</span><span class="sxs-lookup"><span data-stu-id="7218e-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="7218e-127">Utwórz nowy projekt konsoli języka C# lub języka F #</span><span class="sxs-lookup"><span data-stu-id="7218e-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="7218e-128">Dodaj bibliotekę Q # jako odwołanie z programu hosta</span><span class="sxs-lookup"><span data-stu-id="7218e-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="7218e-129">Obowiązkowe Utwórz rozwiązanie dla obu projektów</span><span class="sxs-lookup"><span data-stu-id="7218e-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="7218e-130">Wywoływanie funkcji Q # z platformy .NET</span><span class="sxs-lookup"><span data-stu-id="7218e-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="7218e-131">Po skonfigurowaniu projektów zgodnie z powyższymi instrukcjami można wywołać polecenie Q # z aplikacji konsolowej platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="7218e-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="7218e-132">Kompilator Q # utworzy klasy .NET dla każdej operacji Q # i funkcji, która pozwala na uruchamianie programów Quantum w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="7218e-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="7218e-133">Na przykład przykład [współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) obejmuje następujący przykład operacji Q #:</span><span class="sxs-lookup"><span data-stu-id="7218e-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="7218e-134">Aby wywołać tę operację z platformy .NET w symulatorze Quantum, można użyć `Run` metody `RunAlgorithm` klasy .NET wygenerowanej przez kompilator Q #:</span><span class="sxs-lookup"><span data-stu-id="7218e-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="7218e-135">C#</span><span class="sxs-lookup"><span data-stu-id="7218e-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="7218e-136">F#</span><span class="sxs-lookup"><span data-stu-id="7218e-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="7218e-137">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="7218e-137">Next steps</span></span>

<span data-ttu-id="7218e-138">Teraz, gdy zestaw Quantum Development Kit jest skonfigurowany dla programów wiersza polecenia Q # i dla współdziałania z platformą .NET można napisać i uruchomić [pierwszy program Quantum](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="7218e-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
