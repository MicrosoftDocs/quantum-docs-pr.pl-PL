---
title: Instalacja biblioteki liczb i walidacja | Microsoft Docs
description: Instalacja biblioteki liczb i walidacja
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184631"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="a0c4f-103">Instalacja biblioteki liczb i walidacja</span><span class="sxs-lookup"><span data-stu-id="a0c4f-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="a0c4f-104">Zestaw Quantum Development Kit zapewnia obsługę funkcji liczbowych za pomocą pakietu NuGet [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .</span><span class="sxs-lookup"><span data-stu-id="a0c4f-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="a0c4f-105">**Program Visual Studio > = 2019:** Jeśli używasz programu Visual Studio 2019 lub nowszego, możesz dodać pakiet liczbowy przy użyciu Menedżera pakietów NuGet.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="a0c4f-106">Aby to zrobić, wybierz pozycję "Zarządzaj pakietami NuGet..." z elementu menu "projekt" w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="a0c4f-107">Na karcie Przeglądaj Wyszukaj nazwę pakietu "Microsoft. Quantum. Numerics".</span><span class="sxs-lookup"><span data-stu-id="a0c4f-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="a0c4f-108">Upewnij się, że jest to znaczniki "Uwzględnij wersję wstępną"</span><span class="sxs-lookup"><span data-stu-id="a0c4f-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="a0c4f-109">Spowoduje to wyświetlenie listy pakietów dostępnych do pobrania.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-109">This will list the packages available for download.</span></span>
<span data-ttu-id="a0c4f-110">Umieszczenie wskaźnika myszy na "Microsoft. Quantum. Numerics" powoduje wyświetlenie strzałki skierowanej w dół z prawej strony numeru wersji.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="a0c4f-111">Kliknij strzałkę w celu zainstalowania pakietu liczbowego.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="a0c4f-112">Aby uzyskać więcej informacji, zobacz [Przewodnik po interfejsie użytkownika Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="a0c4f-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="a0c4f-113">Alternatywnie można użyć konsoli Menedżera pakietów, aby dodać bibliotekę liczbową do projektu za pomocą interfejsu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="a0c4f-114">W konsoli Menedżera pakietów Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="a0c4f-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="a0c4f-115">Aby uzyskać więcej informacji, zobacz [Przewodnik po konsoli Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="a0c4f-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="a0c4f-116">**Wiersz polecenia lub Visual Studio Code:** Przy użyciu wiersza polecenia lub z poziomu Visual Studio Code można użyć polecenia `dotnet`, aby dodać odwołanie do pakietu NuGet do projektu:</span><span class="sxs-lookup"><span data-stu-id="a0c4f-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="a0c4f-117">Weryfikowanie instalacji</span><span class="sxs-lookup"><span data-stu-id="a0c4f-117">Verifying your installation</span></span>

<span data-ttu-id="a0c4f-118">Podobnie jak w przypadku reszty zestawu Quantum Development Kit, biblioteka liczbowa zawiera przykłady, które ułatwiają rozpoczęcie pracy jak najszybciej.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-118">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="a0c4f-119">Aby przetestować instalację przy użyciu tych przykładów, Sklonuj [repozytorium głównych przykładów](https://github.com/Microsoft/Quantum) , a następnie uruchom jeden z przykładów.</span><span class="sxs-lookup"><span data-stu-id="a0c4f-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="a0c4f-120">Aby uruchomić przykład [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) :</span><span class="sxs-lookup"><span data-stu-id="a0c4f-120">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```