---
title: Instalowanie i sprawdzanie poprawności biblioteki chemicznej | Microsoft Docs
description: Instalowanie i sprawdzanie poprawności biblioteki chemicznej
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: fd43c783fa82c7219e143a57759919606fdd197f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184206"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="2b438-103">Instalowanie i sprawdzanie poprawności biblioteki chemicznej</span><span class="sxs-lookup"><span data-stu-id="2b438-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="2b438-104">Zestaw Quantum Development Kit zapewnia obsługę aplikacji chemii Quantum za pomocą pakietu NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .</span><span class="sxs-lookup"><span data-stu-id="2b438-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="2b438-105">Podobnie jak w przypadku innych pakietów NuGet, Dodawanie biblioteki chemii do projektu jest proste.</span><span class="sxs-lookup"><span data-stu-id="2b438-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="2b438-106">**Program Visual Studio 2019:** Jeśli używasz programu Visual Studio 2019, możesz dodać pakiety chemii Quantum przy użyciu Menedżera pakietów NuGet.</span><span class="sxs-lookup"><span data-stu-id="2b438-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="2b438-107">Aby otworzyć Menedżera pakietów, kliknij prawym przyciskiem myszy projekt, do którego chcesz dodać bibliotekę chemii, i wybierz pozycję "Zarządzaj pakietami NuGet...", jak na poniższym zrzucie ekranu.</span><span class="sxs-lookup"><span data-stu-id="2b438-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="2b438-108">Na karcie Przeglądaj Wyszukaj nazwę pakietu "Microsoft. Quantum. Chemia".</span><span class="sxs-lookup"><span data-stu-id="2b438-108">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="2b438-109">Upewnij się, że jest to znacznik "Uwzględnij wersję wstępną".</span><span class="sxs-lookup"><span data-stu-id="2b438-109">Make sure to tick "Include prerelease."</span></span>

![](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="2b438-110">Spowoduje to wyświetlenie listy pakietów dostępnych do pobrania.</span><span class="sxs-lookup"><span data-stu-id="2b438-110">This will list the packages available for download.</span></span>
<span data-ttu-id="2b438-111">Kliknij pozycję "Microsoft. Quantum. Chemia w okienku po lewej stronie, wybierz najnowszą wersję wstępną w okienku po prawej stronie, a następnie kliknij pozycję" Zainstaluj ":</span><span class="sxs-lookup"><span data-stu-id="2b438-111">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="2b438-112">Aby uzyskać więcej informacji, zobacz [Przewodnik po interfejsie użytkownika Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="2b438-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="2b438-113">Alternatywnie można użyć konsoli Menedżera pakietów, aby dodać bibliotekę chemii Quantum do projektu za pomocą interfejsu wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="2b438-113">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="2b438-114">W konsoli Menedżera pakietów Uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="2b438-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="2b438-115">Aby uzyskać więcej informacji, zobacz [Przewodnik po konsoli Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="2b438-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="2b438-116">**Wiersz polecenia lub Visual Studio Code:** Przy użyciu wiersza polecenia lub z poziomu Visual Studio Code można użyć polecenia `dotnet`, aby dodać odwołanie do pakietu NuGet do projektu:</span><span class="sxs-lookup"><span data-stu-id="2b438-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="2b438-117">Weryfikowanie instalacji</span><span class="sxs-lookup"><span data-stu-id="2b438-117">Verifying Your Installation</span></span> 

<span data-ttu-id="2b438-118">Podobnie jak w przypadku reszty zestawu Quantum Development Kit, biblioteka chemii Quantum zawiera wiele w pełni udokumentowanych przykładów, które ułatwiają szybkie rozpoczęcie pracy.</span><span class="sxs-lookup"><span data-stu-id="2b438-118">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="2b438-119">Aby przetestować instalację przy użyciu tych przykładów, Sklonuj [repozytorium głównych przykładów](https://github.com/Microsoft/Quantum), a następnie uruchom jedną z przykładów.</span><span class="sxs-lookup"><span data-stu-id="2b438-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="2b438-120">Na przykład, aby uruchomić przykład [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) :</span><span class="sxs-lookup"><span data-stu-id="2b438-120">For example, to run the [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="2b438-121">Aby zweryfikować instalację biblioteki chemii Quantum przy użyciu Microsoft Visual Studio po sklonowaniu repozytorium:</span><span class="sxs-lookup"><span data-stu-id="2b438-121">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="2b438-122">Otwórz rozwiązanie ChemistrySamples. sln w folderze chemia.</span><span class="sxs-lookup"><span data-stu-id="2b438-122">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="2b438-123">Wybierz pozycję Przykłady/1.</span><span class="sxs-lookup"><span data-stu-id="2b438-123">Select Samples/1.</span></span> <span data-ttu-id="2b438-124">Proste cząsteczek/MolecularHydrogen jako projekt startowy.</span><span class="sxs-lookup"><span data-stu-id="2b438-124">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="2b438-125">Naciśnij klawisz F5, aby uruchomić demonstrację fazy Quantum w ramach szacowania.</span><span class="sxs-lookup"><span data-stu-id="2b438-125">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="2b438-126">Aby uzyskać więcej informacji na temat oszacowania wartości poziomów energii, zobacz [otrzymywanie szacunków na poziomie energii](xref:microsoft.quantum.chemistry.examples.energyestimate) .</span><span class="sxs-lookup"><span data-stu-id="2b438-126">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="2b438-127">Korzystanie z zestawu Quantum Development Kit z NWChem</span><span class="sxs-lookup"><span data-stu-id="2b438-127">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="2b438-128">Przykład MolecularHydrogen korzysta z danych wejściowych molekularnych skonfigurowanych ręcznie.</span><span class="sxs-lookup"><span data-stu-id="2b438-128">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="2b438-129">Chociaż jest to bardzo szczegółowe w przypadku małych przykładów, Chemia Quantum na skalę wymaga Hamiltonians z milionami lub miliardami warunków.</span><span class="sxs-lookup"><span data-stu-id="2b438-129">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="2b438-130">Takie Hamiltonians, generowane przez skalowalne pakiety chemii obliczeniowej, są zbyt duże, aby można je było zaimportować.</span><span class="sxs-lookup"><span data-stu-id="2b438-130">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="2b438-131">Biblioteka chemii Quantum dla zestawu Quantum Development Kit została zaprojektowana tak, aby działała prawidłowo [**z obliczanymi**](http://www.nwchem-sw.org/) pakietami chemicznymi EMSL) w laboratorium krajowym Pacyfiku Zachodnie.</span><span class="sxs-lookup"><span data-stu-id="2b438-131">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="2b438-132">W szczególności pakiet `Microsoft.Quantum.Chemistry` udostępnia narzędzia do ładowania wystąpień problemów związanych z symulacją jednostek Quantum przedstawionymi w [schemacie Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), które są również obsługiwane w przypadku eksportowania przez ostatnie wersje programu NWChem.</span><span class="sxs-lookup"><span data-stu-id="2b438-132">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="2b438-133">Aby rozpocząć korzystanie z programu NWChem wraz z zestawem Quantum Development Kit, sugerujemy jedną z następujących metod:</span><span class="sxs-lookup"><span data-stu-id="2b438-133">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="2b438-134">Zacznij korzystać z istniejących plików Broombridge dostarczonych z przykładami w [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="2b438-134">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="2b438-135">Użyj [konstruktora strzałek EMSL dla Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , który jest oparty na sieci Web frontonem NWChem, aby generować nowe pliki wejściowe molekularne w formacie Broombridge.</span><span class="sxs-lookup"><span data-stu-id="2b438-135">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="2b438-136">Użyj [obrazu platformy Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) dostarczonego przez PNNL do uruchomienia NWChem lub</span><span class="sxs-lookup"><span data-stu-id="2b438-136">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="2b438-137">[Kompiluj NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) dla swojej platformy.</span><span class="sxs-lookup"><span data-stu-id="2b438-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="2b438-138">Zobacz [kompleksowe z NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) , aby uzyskać więcej informacji na temat pracy z NWChemami z modelami chemicznymi w celu przeanalizowania za pomocą biblioteki chemii zestawu Quantum opracowuje.</span><span class="sxs-lookup"><span data-stu-id="2b438-138">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="2b438-139">Wprowadzenie do korzystania z plików Broombridge dostarczonych z przykładami</span><span class="sxs-lookup"><span data-stu-id="2b438-139">Getting started using Broombridge files provided with the samples</span></span>
<span data-ttu-id="2b438-140">Folder [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) w repozytorium "Quantum Development Kit Samples" zawiera pliki danych cząsteczków Broombridge.</span><span class="sxs-lookup"><span data-stu-id="2b438-140">The [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="2b438-141">W prostym przykładzie należy użyć przykładowej biblioteki chemij, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) do załadowania hamiltonian z jednego z plików Broombridge i wykonania oszacowania bramy Quantum algorigthms:</span><span class="sxs-lookup"><span data-stu-id="2b438-141">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="2b438-142">Aby uzyskać więcej informacji na temat wprowadzania cząsteczek reprezentowanych przez schemat Broombridge, zobacz [ładowanie hamiltonian z pliku](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="2b438-142">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="2b438-143">Zobacz [Uzyskiwanie liczby zasobów](xref:microsoft.quantum.chemistry.examples.resourcecounts) , aby uzyskać więcej informacji na temat szacowania zasobów.</span><span class="sxs-lookup"><span data-stu-id="2b438-143">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="2b438-144">Wprowadzenie do korzystania z konstruktora strzałek EMSL</span><span class="sxs-lookup"><span data-stu-id="2b438-144">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="2b438-145">Strzałki EMSL to narzędzie, które używa NWChem i chemicznych baz danych do generowania danych cząsteczkowych.</span><span class="sxs-lookup"><span data-stu-id="2b438-145">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="2b438-146">[Konstruktor strzałek EMSL dla Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) umożliwia wprowadzenie modelu przy użyciu wielu konstruktorów modelu molekularnego i wygenerowanie pliku danych Broombridge, który będzie używany przez zestaw Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="2b438-146">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="2b438-147">Na stronie EMSL kliknij kartę ["instuctions"] i postępuj zgodnie z instrukcjami ["Simple przykłady"], aby wygenerować pliki Broombridge.</span><span class="sxs-lookup"><span data-stu-id="2b438-147">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="2b438-148">Następnie spróbuj uruchomić ["GetGateCount"], aby zobaczyć oszacowania zasobów Quantum dla tych cząsteczek.</span><span class="sxs-lookup"><span data-stu-id="2b438-148">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="2b438-149">Instalowanie NWChem ze źródła</span><span class="sxs-lookup"><span data-stu-id="2b438-149">Installing NWChem from Source</span></span>

<span data-ttu-id="2b438-150">Pełne instrukcje dotyczące sposobu instalowania NWChem ze źródła [są udostępniane przez PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span><span class="sxs-lookup"><span data-stu-id="2b438-150">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="2b438-151">Jeśli chcesz używać NWChem z systemu Windows 10, podsystem Windows dla systemu Linux jest doskonałym rozwiązaniem.</span><span class="sxs-lookup"><span data-stu-id="2b438-151">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="2b438-152">Po zainstalowaniu programu [Ubuntu 18,04 LTS dla systemu Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)Uruchom `ubuntu18.04` z ulubionego terminalu i postępuj zgodnie z powyższymi instrukcjami, aby zainstalować NWChem ze źródła.</span><span class="sxs-lookup"><span data-stu-id="2b438-152">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="2b438-153">Po skompilowaniu NWChem ze źródła można uruchomić skrypt `yaml_driver` dostarczony z NWChem, aby szybko utworzyć wystąpienia Broombridge z poziomu NWChem wejściowych pokładów:</span><span class="sxs-lookup"><span data-stu-id="2b438-153">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="2b438-154">To polecenie spowoduje utworzenie nowego pliku `input.yaml` w formacie Broombridge w bieżącym katalogu.</span><span class="sxs-lookup"><span data-stu-id="2b438-154">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="2b438-155">Używanie NWChem z platformą Docker</span><span class="sxs-lookup"><span data-stu-id="2b438-155">Using NWChem with Docker</span></span>

<span data-ttu-id="2b438-156">Wstępnie utworzone obrazy do używania NWChem są dostępne na wielu platformach za pośrednictwem usługi [Docker Hub](https://hub.docker.com).</span><span class="sxs-lookup"><span data-stu-id="2b438-156">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="2b438-157">Aby rozpocząć, postępuj zgodnie z instrukcjami dotyczącymi instalacji platformy Docker na platformie:</span><span class="sxs-lookup"><span data-stu-id="2b438-157">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="2b438-158">Zainstaluj platformę Docker dla Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2b438-158">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="2b438-159">Zainstaluj platformę Docker dla macOS</span><span class="sxs-lookup"><span data-stu-id="2b438-159">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="2b438-160">Zainstaluj Docker for Windows 10</span><span class="sxs-lookup"><span data-stu-id="2b438-160">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="2b438-161">W przypadku korzystania z Docker for Windows należy udostępnić dysk zawierający katalog tymczasowy (zazwyczaj jest to `C:\` dysk) z demonem Docker.</span><span class="sxs-lookup"><span data-stu-id="2b438-161">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="2b438-162">Aby uzyskać więcej informacji, zobacz [dokumentację platformy Docker](https://docs.docker.com/docker-for-windows/#shared-drives) .</span><span class="sxs-lookup"><span data-stu-id="2b438-162">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="2b438-163">Po zainstalowaniu platformy Docker możesz użyć modułu programu PowerShell dostarczonego z zestawami deweloperskich zestawu SDK, aby uruchomić obraz, lub ręcznie uruchomić obraz.</span><span class="sxs-lookup"><span data-stu-id="2b438-163">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="2b438-164">W tym miejscu szczegółowo korzystamy z programu PowerShell. Jeśli chcesz ręcznie używać obrazu platformy Docker, zapoznaj się [z dokumentacją dostarczoną z obrazem](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span><span class="sxs-lookup"><span data-stu-id="2b438-164">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="2b438-165">Uruchamianie NWChem za poorednictwem programu PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="2b438-165">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="2b438-166">Aby użyć obrazu platformy Docker NWChem z zestawem Quantum Development Kit, udostępniamy mały moduł programu PowerShell, który obsługuje przemieszczanie plików do i z NWChem.</span><span class="sxs-lookup"><span data-stu-id="2b438-166">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="2b438-167">Jeśli nie masz jeszcze zainstalowanego programu PowerShell Core, możesz go pobrać z [repozytorium programu PowerShell w serwisie GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span><span class="sxs-lookup"><span data-stu-id="2b438-167">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="2b438-168">Program PowerShell Core jest również używany w niektórych przykładach w celu zaprezentowania współdziałania z przepływami pracy analizy danych i analiz biznesowej.</span><span class="sxs-lookup"><span data-stu-id="2b438-168">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="2b438-169">Po zainstalowaniu programu PowerShell Core zaimportuj `InvokeNWChem.psm1`, aby polecenia NWChem były dostępne w bieżącej sesji:</span><span class="sxs-lookup"><span data-stu-id="2b438-169">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="2b438-170">Spowoduje to udostępnienie `Convert-NWChemToBroombridge` polecenia w bieżącej sesji programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b438-170">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="2b438-171">Aby pobrać zbędne obrazy z platformy Docker i użyć ich do uruchomienia pokładów wejściowych NWChem i przechwycić dane wyjściowe do Broombridge, uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="2b438-171">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="2b438-172">Spowoduje to utworzenie pliku Broombridge przez uruchomienie NWChem na `input.nw`.</span><span class="sxs-lookup"><span data-stu-id="2b438-172">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="2b438-173">Domyślnie dane wyjściowe Broombridge będą mieć taką samą nazwę i ścieżkę co pokład wejściowy z rozszerzeniem `.nw` zastąpione przez `.yaml`.</span><span class="sxs-lookup"><span data-stu-id="2b438-173">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="2b438-174">Tę wartość można zastąpić za pomocą parametru `-DestinationPath`, aby `Convert-NWChemToBroombridge`.</span><span class="sxs-lookup"><span data-stu-id="2b438-174">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="2b438-175">Więcej informacji można uzyskać przy użyciu wbudowanych funkcji pomocy programu PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b438-175">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

