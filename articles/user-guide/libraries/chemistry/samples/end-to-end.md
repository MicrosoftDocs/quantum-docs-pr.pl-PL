---
title: Przykładowy program NWChem Quantum
description: Za pomocą pokładu wejściowego NWChem należy zapoznać się z przykładem uzyskiwania liczby bram dla symulacji chemicznej Quantum.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: 528c34ea9b28b2f9b8f9a8bad681557f44bfcdaa
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759719"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="ca832-103">Kompleksowe rozwiązanie z NWChem</span><span class="sxs-lookup"><span data-stu-id="ca832-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="ca832-104">W tym artykule przedstawiono przykład uzyskiwania liczby bram dla symulacji chemicznej Quantum, rozpoczynając od pokładu wejściowego [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .</span><span class="sxs-lookup"><span data-stu-id="ca832-104">In this article, you will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="ca832-105">Przed kontynuowaniem tego przykładu upewnij się, że zainstalowano platformę Docker, postępując zgodnie z [przewodnikiem instalacji i weryfikacji](xref:microsoft.quantum.chemistry.concepts.installation).</span><span class="sxs-lookup"><span data-stu-id="ca832-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="ca832-106">Więcej informacji:</span><span class="sxs-lookup"><span data-stu-id="ca832-106">For more information:</span></span>
- [<span data-ttu-id="ca832-107">Struktura pokładów wejściowych NWChem</span><span class="sxs-lookup"><span data-stu-id="ca832-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="ca832-108">Polecenia dotyczące pokładu wejściowego do użycia z zestawem Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="ca832-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [<span data-ttu-id="ca832-109">Instalowanie biblioteki i zależności chemii</span><span class="sxs-lookup"><span data-stu-id="ca832-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="ca832-110">Zliczanie zasobów</span><span class="sxs-lookup"><span data-stu-id="ca832-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="ca832-111">Ten przykład wymaga uruchomienia środowiska Windows PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="ca832-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="ca832-112">Pobierz rdzeń programu PowerShell dla systemu Windows, macOS lub Linux pod adresem https://github.com/PowerShell/PowerShell .</span><span class="sxs-lookup"><span data-stu-id="ca832-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="ca832-113">Importowanie wymaganych modułów programu PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca832-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="ca832-114">Jeśli jeszcze tego nie zrobiono, Sklonuj [repozytorium Microsoft/Quantum](https://github.com/Microsoft/Quantum), które zawiera przykłady i narzędzia do pracy z zestawem Quantum Development Kit:</span><span class="sxs-lookup"><span data-stu-id="ca832-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="ca832-115">Po sklonowaniu `Microsoft/Quantum` należy wykonać `cd` w `utilities/` folderze i zaimportować moduł PowerShell do pracy z platformą Docker i NWChem:</span><span class="sxs-lookup"><span data-stu-id="ca832-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="ca832-116">Domyślnie system Windows zapobiega wykonywaniu skryptów lub modułów jako miary zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="ca832-116">By default, Windows prevents the execution of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="ca832-117">Aby zezwolić na uruchamianie modułów `Invoke-NWChem.psm1` w systemie Windows, może być konieczna zmiana zasad wykonywania.</span><span class="sxs-lookup"><span data-stu-id="ca832-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the execution policy.</span></span>
> <span data-ttu-id="ca832-118">Aby to zrobić, uruchom `Set-ExecutionPolicy` polecenie:</span><span class="sxs-lookup"><span data-stu-id="ca832-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="ca832-119">Zasady wykonywania zostaną następnie przywrócone po zakończeniu działania programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca832-119">The execution policy will then be reverted when you exit PowerShell.</span></span>
> <span data-ttu-id="ca832-120">Jeśli chcesz zapisać zasady wykonywania, użyj innej wartości dla `-Scope` :</span><span class="sxs-lookup"><span data-stu-id="ca832-120">If you would like to save the execution policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="ca832-121">Teraz powinno być `Convert-NWChemToBroombridge` dostępne polecenie:</span><span class="sxs-lookup"><span data-stu-id="ca832-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="ca832-122">Następnie zaimportujemy `Get-GateCount` polecenie dostarczone z przykładem **GetGateCount** .</span><span class="sxs-lookup"><span data-stu-id="ca832-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="ca832-123">Aby uzyskać szczegółowe informacje, zobacz [instrukcje dostarczone z przykładem](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).</span><span class="sxs-lookup"><span data-stu-id="ca832-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).</span></span>
<span data-ttu-id="ca832-124">Następnie uruchom następujące polecenie, zastępując je `<runtime>` `win10-x64` , `osx-x64` lub, w zależności od `linux-x64` używanego systemu operacyjnego:</span><span class="sxs-lookup"><span data-stu-id="ca832-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="ca832-125">Teraz powinno być `Get-GateCount` dostępne polecenie:</span><span class="sxs-lookup"><span data-stu-id="ca832-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="ca832-126">Pokłady wejściowe</span><span class="sxs-lookup"><span data-stu-id="ca832-126">Input Decks</span></span> ##

<span data-ttu-id="ca832-127">Pakiet NWChem przyjmuje plik tekstowy o nazwie _pokład wejściowy_ , który określa problem z chemią Quantum, który ma zostać rozwiązany, wraz z innymi parametrami, takimi jak ustawienia alokacji pamięci.</span><span class="sxs-lookup"><span data-stu-id="ca832-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="ca832-128">Na potrzeby tego przykładu użyjemy jednego z wstępnie utworzonych pokładów wejściowych, które są dostarczane z NWChem.</span><span class="sxs-lookup"><span data-stu-id="ca832-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="ca832-129">Najpierw Sklonuj [repozytorium nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):</span><span class="sxs-lookup"><span data-stu-id="ca832-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="ca832-130">Ponieważ jest to bardzo duże repozytorium, możemy wykonać płytki klonowania, aby zaoszczędzić pewną przepustowość i miejsce na dysku przy użyciu `--depth 1` argumentu.</span><span class="sxs-lookup"><span data-stu-id="ca832-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="ca832-131">Jest to jednak opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="ca832-131">This is optional, however.</span></span>
> <span data-ttu-id="ca832-132">Klonowanie będzie działać tylko w sposób niewidoczny `--depth 1` .</span><span class="sxs-lookup"><span data-stu-id="ca832-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="ca832-133">`nwchemgit/nwchem`Repozytorium zawiera różne pokłady wejściowe przeznaczone do użycia z zestawem Quantum Development Kit, które znajdują się w [ `QA/chem_library_tests` folderze](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).</span><span class="sxs-lookup"><span data-stu-id="ca832-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).</span></span>
<span data-ttu-id="ca832-134">Na potrzeby tego przykładu będziemy używać `H4` pokładu wejściowego:</span><span class="sxs-lookup"><span data-stu-id="ca832-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="ca832-135">Dana cząsteczka to system 4 atomów wodoru, które są ułożone w pewnej geometrii, która zależy od jednego kąta, parametr `alpha` wskazany w nazwie `h4_sto6g_alpha.nw` talii.</span><span class="sxs-lookup"><span data-stu-id="ca832-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="ca832-136">H4 jest znanym [wzorcem molekularnym](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) dla chemii obliczeniowej od 1970s.</span><span class="sxs-lookup"><span data-stu-id="ca832-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="ca832-137">Parametr `sto6g` ma charakter wskazujący, że talia implementuje reprezentację w odniesieniu do typu Slater, a w związku z tym, w odniesieniu do [Ustawienia podstawy konie-ng](https://en.wikipedia.org/wiki/STO-nG_basis_sets) z 6 funkcjami bazowymi.</span><span class="sxs-lookup"><span data-stu-id="ca832-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="ca832-138">Ten pokład wejściowy zawiera kilka instrukcji dotyczących aparatu wykonawcy NWChem (TCE), który kieruje NWChem w celu utworzenia informacji niezbędnych do współdziałania z zestawem Quantum Development Kit:</span><span class="sxs-lookup"><span data-stu-id="ca832-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="ca832-139">Produkowanie i zużywanie danych wyjściowych Broombridge z NWChem</span><span class="sxs-lookup"><span data-stu-id="ca832-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="ca832-140">Masz teraz wszystko, czego potrzebujesz, aby tworzyć i korzystać z dokumentów Broombridge.</span><span class="sxs-lookup"><span data-stu-id="ca832-140">You now have everything you need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="ca832-141">Aby uruchomić NWChem i utworzyć dokument Broombridge dla `h4_sto6g_0.000.nw` pokładu wejściowego, uruchom polecenie `Convert-NWChemToBroombridge` :</span><span class="sxs-lookup"><span data-stu-id="ca832-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="ca832-142">Przy pierwszym uruchomieniu tego polecenia program Docker pobierze `nwchemorg/nwchem-qc` obraz.</span><span class="sxs-lookup"><span data-stu-id="ca832-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="ca832-143">Może to potrwać trochę czasu, w zależności od szybkości połączenia, dzięki czemu można uzyskać dostęp do filiżanki kawy.</span><span class="sxs-lookup"><span data-stu-id="ca832-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="ca832-144">Spowoduje to wygenerowanie dokumentu Broombridge o nazwie `h4_sto6g_0.000.yaml` , który może być używany z `Get-GateCount` :</span><span class="sxs-lookup"><span data-stu-id="ca832-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that you can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="ca832-145">Teraz powinny być widoczne dane wyjściowe konsoli zawierające oszacowanie zasobów, takie jak T-Count, liczba obrotów, liczba CNOT itp. dla różnych metod symulacji Quantum:</span><span class="sxs-lookup"><span data-stu-id="ca832-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="ca832-146">Istnieje wiele rzeczy, które należy wykonać w tym miejscu:</span><span class="sxs-lookup"><span data-stu-id="ca832-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="ca832-147">Wypróbuj różne wstępnie zdefiniowane talie wejściowe, np., zmieniając parametr `alpha` w `h4_sto6g_alpha.nw` ,</span><span class="sxs-lookup"><span data-stu-id="ca832-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="ca832-148">Spróbuj zmodyfikować talie, edytując talie NWChem bezpośrednio, np. Eksplorowanie `STO-nG` modeli dla różnych wyborów n,</span><span class="sxs-lookup"><span data-stu-id="ca832-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="ca832-149">Wypróbuj inne wstępnie zdefiniowane pokłady wejściowe NWChem, które są dostępne w programie `nwchem/qa/chem_library_tests` ,</span><span class="sxs-lookup"><span data-stu-id="ca832-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="ca832-150">Wypróbuj pakiet wstępnie zdefiniowanych testów porównawczych Broombridge YAML, które zostały wygenerowane z NWChem i są dostępne jako część [repozytorium Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="ca832-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="ca832-151">Te testy porównawcze obejmują:</span><span class="sxs-lookup"><span data-stu-id="ca832-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="ca832-152">małe cząsteczek, takie jak wodór wodoru (H2), beryl (hydride), litu (LiH),</span><span class="sxs-lookup"><span data-stu-id="ca832-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="ca832-153">większe cząsteczek, takie jak ozon (O3), beta-karoten, cytosine i wiele innych.</span><span class="sxs-lookup"><span data-stu-id="ca832-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="ca832-154">Wypróbuj graficzną [strzałkę EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) frontonu, która oferuje interfejs do Microsoft Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="ca832-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="ca832-155">Tworzenie danych wyjściowych Broombridge z strzałek EMSL</span><span class="sxs-lookup"><span data-stu-id="ca832-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="ca832-156">Aby rozpocząć pracę z EMSL strzałkami frontonu opartymi na sieci Web, w [tym miejscu](https://arrows.emsl.pnnl.gov/api/qsharp_chem)przejdź do przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="ca832-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="ca832-157">Uruchamianie strzałek EMSL w przeglądarce internetowej wymaga włączenia języka JavaScript.</span><span class="sxs-lookup"><span data-stu-id="ca832-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="ca832-158">Zapoznaj się z tymi [instrukcjami](https://www.enable-javascript.com/) dotyczącymi sposobu włączania języka JavaScript w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="ca832-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="ca832-159">Najpierw wprowadź cząsteczkę w polu zapytania, które mówi ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="ca832-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="ca832-160">Można wprowadzić wiele cząsteczek według ich nazwy Colloquial, na przykład "kofeiny" zamiast "1, 3, 7-trimethylxanthine".</span><span class="sxs-lookup"><span data-stu-id="ca832-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="ca832-161">Następnie kliknij przycisk, który jest wyświetlany ``theory{qsharp_chem}`` .</span><span class="sxs-lookup"><span data-stu-id="ca832-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="ca832-162">Spowoduje to zapełnienie pola zapytania instrukcją, która będzie informować o przebiegu eksportowania danych wyjściowych w formacie Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="ca832-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="ca832-163">Teraz Zarejestruj się ``Run Arrows`` .</span><span class="sxs-lookup"><span data-stu-id="ca832-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="ca832-164">W zależności od rozmiaru danych wejściowych może to chwilę potrwać.</span><span class="sxs-lookup"><span data-stu-id="ca832-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="ca832-165">Lub, na wypadek, gdyby określony model został już wcześniej obliczony, można to zrobić bardzo szybko, ponieważ będzie to miało miejsce tylko w odniesieniu do wyszukiwania w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="ca832-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="ca832-166">W obu przypadkach nastąpi przekierowanie do nowej strony, która zawiera mnóstwo informacji o konkretnym przebiegu NWChem na pokładzie określonym przez dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="ca832-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="ca832-167">Plik Broombridge YAML można pobrać i zapisać z sekcji, która rozpoczyna się od następującego nagłówka:</span><span class="sxs-lookup"><span data-stu-id="ca832-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="ca832-168">Kliknij pozycję włączone ``download`` , co spowoduje zapisanie kopii lokalnej z unikatową nazwą pliku, taką jak ``qsharp_chem48443.yaml`` (określona nazwa będzie inna dla każdego przebiegu).</span><span class="sxs-lookup"><span data-stu-id="ca832-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="ca832-169">Następnie można przetworzyć ten plik jak powyżej, np., z</span><span class="sxs-lookup"><span data-stu-id="ca832-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="ca832-170">Aby uzyskać liczbę zasobów.</span><span class="sxs-lookup"><span data-stu-id="ca832-170">to get resource counts.</span></span> 

<span data-ttu-id="ca832-171">Można korzystać z konstruktora cząsteczkowego 3D, do którego można uzyskać dostęp z ``Arrows Entry - 3D Builder`` karty na stronie początkowej strzałek EMSL.</span><span class="sxs-lookup"><span data-stu-id="ca832-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="ca832-172">Kliknięcie obrazu 3D [JSMol](http://wiki.jmol.org/index.php/JSmol) pokazanej cząsteczki umożliwi jego edytowanie.</span><span class="sxs-lookup"><span data-stu-id="ca832-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="ca832-173">Można przenieść atomy dookoła, a następnie przeciągnąć atomy, tak aby ich odległości między cząsteczkami były zmieniane, dodawać i usuwać atomy itp. Dla każdej z tych opcji, po dodaniu ``theory{qsharp_chem}`` w polu zapytania, można wygenerować wystąpienie schematu BROOMBRIDGE YAML i dodatkowo zbadać je przy użyciu biblioteki chemii Quantum.</span><span class="sxs-lookup"><span data-stu-id="ca832-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
