---
title: Instalowanie i sprawdzanie poprawności biblioteki chemicznej | Microsoft Docs
description: Instalowanie i sprawdzanie poprawności biblioteki chemicznej
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: de13d1814821c612ed74a347dc8ffb5881063576
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036478"
---
# <a name="chemistry-library-installation-and-validation"></a>Instalowanie i sprawdzanie poprawności biblioteki chemicznej

Zestaw Quantum Development Kit zapewnia obsługę aplikacji chemii Quantum za pomocą pakietu NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .
Podobnie jak w przypadku innych pakietów NuGet, Dodawanie biblioteki chemii do projektu jest proste.

**Program Visual Studio 2019:** Jeśli używasz programu Visual Studio 2019, możesz dodać pakiety chemii Quantum przy użyciu Menedżera pakietów NuGet.
Aby otworzyć Menedżera pakietów, kliknij prawym przyciskiem myszy projekt, do którego chcesz dodać bibliotekę chemii, i wybierz pozycję "Zarządzaj pakietami NuGet...", jak na poniższym zrzucie ekranu.

![](~/media/vs2017-nuget-manage-packages.png)

Na karcie Przeglądaj Wyszukaj nazwę pakietu "Microsoft. Quantum. Chemia".

> [!NOTE]
> Upewnij się, że jest to znacznik "Uwzględnij wersję wstępną".

![](~/media/vs2017-nuget-package-search.png)

Spowoduje to wyświetlenie listy pakietów dostępnych do pobrania.
Kliknij pozycję "Microsoft. Quantum. Chemia w okienku po lewej stronie, wybierz najnowszą wersję wstępną w okienku po prawej stronie, a następnie kliknij pozycję" Zainstaluj ":

![](~/media/vs2017-nuget-select-chem.png)

Aby uzyskać więcej informacji, zobacz [Przewodnik po interfejsie użytkownika Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternatywnie można użyć konsoli Menedżera pakietów, aby dodać bibliotekę chemii Quantum do projektu za pomocą interfejsu wiersza polecenia.

![](~/media/vs2017-nuget-console-menu.png)

W konsoli Menedżera pakietów Uruchom następujące polecenie:

```
Install-Package Microsoft.Quantum.Chemistry
```

Aby uzyskać więcej informacji, zobacz [Przewodnik po konsoli Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Wiersz polecenia lub Visual Studio Code:** Przy użyciu wiersza polecenia lub z poziomu Visual Studio Code można użyć polecenia `dotnet`, aby dodać odwołanie do pakietu NuGet do projektu:

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Weryfikowanie instalacji 

Podobnie jak w przypadku reszty zestawu Quantum Development Kit, biblioteka chemii Quantum zawiera wiele w pełni udokumentowanych przykładów, które ułatwiają szybkie rozpoczęcie pracy.
Aby przetestować instalację przy użyciu tych przykładów, Sklonuj [repozytorium głównych przykładów](https://github.com/Microsoft/Quantum), a następnie uruchom jedną z przykładów.  Na przykład, aby uruchomić przykład [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

Aby zweryfikować instalację biblioteki chemii Quantum przy użyciu Microsoft Visual Studio po sklonowaniu repozytorium:
    1. Otwórz rozwiązanie ChemistrySamples. sln w folderze chemia.  
    2. Wybierz pozycję Przykłady/1. Proste cząsteczek/MolecularHydrogen jako projekt startowy.
    3. Naciśnij klawisz F5, aby uruchomić demonstrację fazy Quantum w ramach szacowania.

Aby uzyskać więcej informacji na temat oszacowania wartości poziomów energii, zobacz [otrzymywanie szacunków na poziomie energii](xref:microsoft.quantum.chemistry.examples.energyestimate) .   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>Korzystanie z zestawu Quantum Development Kit z NWChem ##

Przykład MolecularHydrogen korzysta z danych wejściowych molekularnych skonfigurowanych ręcznie.  Chociaż jest to bardzo szczegółowe w przypadku małych przykładów, Chemia Quantum na skalę wymaga Hamiltonians z milionami lub miliardami warunków. Takie Hamiltonians, generowane przez skalowalne pakiety chemii obliczeniowej, są zbyt duże, aby można je było zaimportować. 

Biblioteka chemii Quantum dla zestawu Quantum Development Kit została zaprojektowana tak, aby działała prawidłowo z obliczanymi pakietami chemicznymi, w szczególności [**NWChem**](http://www.nwchem-sw.org/) obliczeniową platformą chemiczną, opracowaną przez laboratorium ds. analiz molekularnych (EMSL) w krajowym laboratorium zachodnie Pacyfiku.
W szczególności pakiet `Microsoft.Quantum.Chemistry` udostępnia narzędzia do ładowania wystąpień problemów związanych z symulacją jednostek Quantum przedstawionymi w [schemacie Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), które są również obsługiwane w przypadku eksportowania przez ostatnie wersje programu NWChem.

Aby rozpocząć korzystanie z programu NWChem wraz z zestawem Quantum Development Kit, sugerujemy jedną z następujących metod:
- Zacznij korzystać z istniejących plików Broombridge dostarczonych z przykładami w [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).
- Użyj [konstruktora strzałek EMSL dla Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , który jest oparty na sieci Web frontonem NWChem, aby generować nowe pliki wejściowe molekularne w formacie Broombridge.  
- Użyj [obrazu platformy Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) dostarczonego przez PNNL do uruchomienia NWChem lub
- [Kompiluj NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) dla swojej platformy.

Zobacz [kompleksowe z NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) , aby uzyskać więcej informacji na temat pracy z NWChemami z modelami chemicznymi w celu przeanalizowania za pomocą biblioteki chemii zestawu Quantum opracowuje.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Wprowadzenie do korzystania z plików Broombridge dostarczonych z przykładami

Folder [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) w repozytorium "Quantum Development Kit Samples" zawiera pliki danych cząsteczków Broombridge.  

W prostym przykładzie należy użyć przykładowej biblioteki chemij, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) do załadowania hamiltonian z jednego z plików Broombridge i wykonania oszacowania bramy Quantum algorigthms:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Aby uzyskać więcej informacji na temat wprowadzania cząsteczek reprezentowanych przez schemat Broombridge, zobacz [ładowanie hamiltonian z pliku](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .  

Zobacz [Uzyskiwanie liczby zasobów](xref:microsoft.quantum.chemistry.examples.resourcecounts) , aby uzyskać więcej informacji na temat szacowania zasobów.  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Wprowadzenie do korzystania z konstruktora strzałek EMSL

Strzałki EMSL to narzędzie, które używa NWChem i chemicznych baz danych do generowania danych cząsteczkowych.  [Konstruktor strzałek EMSL dla Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) umożliwia wprowadzenie modelu przy użyciu wielu konstruktorów modelu molekularnego i wygenerowanie pliku danych Broombridge, który będzie używany przez zestaw Quantum Development Kit.  

Na stronie EMSL kliknij kartę ["instuctions"] i postępuj zgodnie z instrukcjami ["Simple przykłady"], aby wygenerować pliki Broombridge.  Następnie spróbuj uruchomić ["GetGateCount"], aby zobaczyć oszacowania zasobów Quantum dla tych cząsteczek.

### <a name="installing-nwchem-from-source"></a>Instalowanie NWChem ze źródła

Pełne instrukcje dotyczące sposobu instalowania NWChem ze źródła [są udostępniane przez PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Jeśli chcesz używać NWChem z systemu Windows 10, podsystem Windows dla systemu Linux jest doskonałym rozwiązaniem.
> Po zainstalowaniu programu [Ubuntu 18,04 LTS dla systemu Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)Uruchom `ubuntu18.04` z ulubionego terminalu i postępuj zgodnie z powyższymi instrukcjami, aby zainstalować NWChem ze źródła.

Po skompilowaniu NWChem ze źródła można uruchomić skrypt `yaml_driver` dostarczony z NWChem, aby szybko utworzyć wystąpienia Broombridge z poziomu NWChem wejściowych pokładów:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

To polecenie spowoduje utworzenie nowego pliku `input.yaml` w formacie Broombridge w bieżącym katalogu.

### <a name="using-nwchem-with-docker"></a>Używanie NWChem z platformą Docker

Wstępnie utworzone obrazy do używania NWChem są dostępne na wielu platformach za pośrednictwem usługi [Docker Hub](https://hub.docker.com).
Aby rozpocząć, postępuj zgodnie z instrukcjami dotyczącymi instalacji platformy Docker na platformie:

- [Zainstaluj platformę Docker dla Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Zainstaluj platformę Docker dla macOS](https://docs.docker.com/docker-for-mac/install/)
- [Zainstaluj Docker for Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> W przypadku korzystania z Docker for Windows należy udostępnić dysk zawierający katalog tymczasowy (zazwyczaj jest to `C:\` dysk) z demonem Docker. Aby uzyskać więcej informacji, zobacz [dokumentację platformy Docker](https://docs.docker.com/docker-for-windows/#shared-drives) .

Po zainstalowaniu platformy Docker możesz użyć modułu programu PowerShell dostarczonego z zestawami deweloperskich zestawu SDK, aby uruchomić obraz, lub ręcznie uruchomić obraz.
W tym miejscu szczegółowo korzystamy z programu PowerShell. Jeśli chcesz ręcznie używać obrazu platformy Docker, zapoznaj się [z dokumentacją dostarczoną z obrazem](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Uruchamianie NWChem za poorednictwem programu PowerShell Core

Aby użyć obrazu platformy Docker NWChem z zestawem Quantum Development Kit, udostępniamy mały moduł programu PowerShell, który obsługuje przemieszczanie plików do i z NWChem.
Jeśli nie masz jeszcze zainstalowanego programu PowerShell Core, możesz go pobrać z [repozytorium programu PowerShell w serwisie GitHub](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> Program PowerShell Core jest również używany w niektórych przykładach w celu zaprezentowania współdziałania z przepływami pracy analizy danych i analiz biznesowej.

Po zainstalowaniu programu PowerShell Core zaimportuj `InvokeNWChem.psm1`, aby polecenia NWChem były dostępne w bieżącej sesji:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Spowoduje to udostępnienie `Convert-NWChemToBroombridge` polecenia w bieżącej sesji programu PowerShell.
Aby pobrać zbędne obrazy z platformy Docker i użyć ich do uruchomienia pokładów wejściowych NWChem i przechwycić dane wyjściowe do Broombridge, uruchom następujące polecenie:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Spowoduje to utworzenie pliku Broombridge przez uruchomienie NWChem na `input.nw`.
Domyślnie dane wyjściowe Broombridge będą mieć taką samą nazwę i ścieżkę co pokład wejściowy z rozszerzeniem `.nw` zastąpione przez `.yaml`.
Tę wartość można zastąpić za pomocą parametru `-DestinationPath`, aby `Convert-NWChemToBroombridge`.
Więcej informacji można uzyskać przy użyciu wbudowanych funkcji pomocy programu PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
