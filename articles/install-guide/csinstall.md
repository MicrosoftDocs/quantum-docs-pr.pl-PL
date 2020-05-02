---
title: Programowanie przy użyciu języków Q# i C#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680161"
---
# <a name="using-q-with-c-and-f"></a><span data-ttu-id="91a7c-102">Używanie Q # z C\# i F\#</span><span class="sxs-lookup"><span data-stu-id="91a7c-102">Using Q# with C\# and F\#</span></span>

<span data-ttu-id="91a7c-103">Program Q # jest zbudowany z użyciem języków .NET, takich jak C# i F #.</span><span class="sxs-lookup"><span data-stu-id="91a7c-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="91a7c-104">W tym przewodniku pokazano, jak używać Q # z programem hosta zapisaną w języku .NET.</span><span class="sxs-lookup"><span data-stu-id="91a7c-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="91a7c-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="91a7c-105">Prerequisites</span></span>

- <span data-ttu-id="91a7c-106">Zainstaluj zestaw Quantum Development Kit [do użycia z projektami wiersza polecenia Q #](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="91a7c-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="91a7c-107">Tworzenie biblioteki Q # i hosta .NET</span><span class="sxs-lookup"><span data-stu-id="91a7c-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="91a7c-108">Pierwszym krokiem jest utworzenie projektów dla biblioteki Q # oraz dla hosta .NET, który będzie wywoływał operacje i funkcje zdefiniowane w bibliotece Q #.</span><span class="sxs-lookup"><span data-stu-id="91a7c-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="91a7c-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="91a7c-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="91a7c-110">Utwórz nową bibliotekę Q #</span><span class="sxs-lookup"><span data-stu-id="91a7c-110">Create a new Q# library</span></span>
  - <span data-ttu-id="91a7c-111">Przejdź do **pliku** -> **Nowy** -> **projekt**</span><span class="sxs-lookup"><span data-stu-id="91a7c-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="91a7c-112">Wpisz "Q #" w polu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="91a7c-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="91a7c-113">Wybierz **bibliotekę Q #**</span><span class="sxs-lookup"><span data-stu-id="91a7c-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="91a7c-114">Wybierz pozycję **dalej**</span><span class="sxs-lookup"><span data-stu-id="91a7c-114">Select **Next**</span></span>
  - <span data-ttu-id="91a7c-115">Wybierz nazwę i lokalizację biblioteki</span><span class="sxs-lookup"><span data-stu-id="91a7c-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="91a7c-116">Upewnij się, że pole "Umieść projekt i rozwiązanie w tym samym katalogu" nie jest **zaznaczone**</span><span class="sxs-lookup"><span data-stu-id="91a7c-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="91a7c-117">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="91a7c-117">Select **Create**</span></span>
- <span data-ttu-id="91a7c-118">Tworzenie nowego programu hosta C# lub F #</span><span class="sxs-lookup"><span data-stu-id="91a7c-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="91a7c-119">Przejdź do **pliku** → **Nowy** → **projekt**</span><span class="sxs-lookup"><span data-stu-id="91a7c-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="91a7c-120">Wybierz pozycję "Aplikacja konsolowa (.NET Core") dla języka C# lub F #</span><span class="sxs-lookup"><span data-stu-id="91a7c-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="91a7c-121">Wybierz pozycję **dalej**</span><span class="sxs-lookup"><span data-stu-id="91a7c-121">Select **Next**</span></span>
  - <span data-ttu-id="91a7c-122">W obszarze *rozwiązanie*wybierz pozycję "Dodaj do rozwiązania".</span><span class="sxs-lookup"><span data-stu-id="91a7c-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="91a7c-123">Wybierz nazwę programu hosta</span><span class="sxs-lookup"><span data-stu-id="91a7c-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="91a7c-124">Wybierz pozycję **Utwórz**</span><span class="sxs-lookup"><span data-stu-id="91a7c-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="91a7c-125">Visual Studio Code lub wiersz polecenia</span><span class="sxs-lookup"><span data-stu-id="91a7c-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="91a7c-126">Utwórz nową bibliotekę Q #</span><span class="sxs-lookup"><span data-stu-id="91a7c-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="91a7c-127">Utwórz nowy projekt konsoli języka C# lub języka F #</span><span class="sxs-lookup"><span data-stu-id="91a7c-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="91a7c-128">Dodaj bibliotekę Q # jako odwołanie z programu hosta</span><span class="sxs-lookup"><span data-stu-id="91a7c-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="91a7c-129">Obowiązkowe Utwórz rozwiązanie dla obu projektów</span><span class="sxs-lookup"><span data-stu-id="91a7c-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="91a7c-130">Wywoływanie funkcji Q # z platformy .NET</span><span class="sxs-lookup"><span data-stu-id="91a7c-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="91a7c-131">Po skonfigurowaniu projektów zgodnie z powyższymi instrukcjami można wywołać polecenie Q # z aplikacji konsolowej platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="91a7c-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="91a7c-132">Kompilator Q # utworzy klasy .NET dla każdej operacji Q # i funkcji, która pozwala na uruchamianie programów Quantum w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="91a7c-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="91a7c-133">Na przykład przykład [współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) obejmuje następujący przykład operacji Q #:</span><span class="sxs-lookup"><span data-stu-id="91a7c-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="91a7c-134">Aby wywołać tę operację z platformy .NET w symulatorze Quantum, można użyć `Run` metody klasy `RunAlgorithm` .NET wygenerowanej przez kompilator Q #:</span><span class="sxs-lookup"><span data-stu-id="91a7c-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="91a7c-135">S #</span><span class="sxs-lookup"><span data-stu-id="91a7c-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="91a7c-136">F#</span><span class="sxs-lookup"><span data-stu-id="91a7c-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a><span data-ttu-id="91a7c-137">Co dalej?</span><span class="sxs-lookup"><span data-stu-id="91a7c-137">What's next?</span></span>

<span data-ttu-id="91a7c-138">Teraz, gdy zestaw Quantum Development Kit jest skonfigurowany dla programów wiersza polecenia Q # i dla współdziałania z platformą .NET można napisać i uruchomić [pierwszy program Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="91a7c-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
