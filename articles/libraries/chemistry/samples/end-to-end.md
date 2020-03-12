---
title: Przykładowy program NWChem Quantum
description: Za pomocą pokładu wejściowego NWChem należy zapoznać się z przykładem uzyskiwania liczby bram dla symulacji chemicznej Quantum.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 7605676e05ee352e47791657eeaafceef5dbb493
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022490"
---
# <a name="end-to-end-with-nwchem"></a>Kompleksowe rozwiązanie z NWChem #

W tym artykule przedstawiono przykład uzyskiwania liczby bram dla symulacji chemicznej Quantum, rozpoczynając od pokładu wejściowego [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .
Przed kontynuowaniem tego przykładu upewnij się, że zainstalowano platformę Docker, postępując zgodnie z [przewodnikiem instalacji i weryfikacji](xref:microsoft.quantum.chemistry.concepts.installation).

Więcej informacji:
- [Struktura pokładów wejściowych NWChem](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Polecenia dotyczące pokładu wejściowego do użycia z zestawem Quantum Development Kit](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [Instalowanie biblioteki i zależności chemii](xref:microsoft.quantum.chemistry.concepts.installation)
- [Zliczanie zasobów](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Ten przykład wymaga uruchomienia środowiska Windows PowerShell Core.
> Pobierz rdzeń programu PowerShell dla systemu Windows, macOS lub Linux w https://github.com/PowerShell/PowerShell.

## <a name="importing-required-powershell-modules"></a>Importowanie wymaganych modułów programu PowerShell ##

Jeśli jeszcze tego nie zrobiono, Sklonuj [repozytorium Microsoft/Quantum](https://github.com/Microsoft/Quantum), które zawiera przykłady i narzędzia do pracy z zestawem Quantum Development Kit:

```powershell
git clone https://github.com/Microsoft/Quantum
```

Po sklonowaniu `Microsoft/Quantum`wykonaj `cd` do folderu `utilities/` i zaimportuj moduł programu PowerShell do pracy z platformą Docker i NWChem:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Domyślnie system Windows zapobiega wykonywaniu skryptów lub modułów jako miary zabezpieczeń.
> Aby zezwolić na uruchamianie modułów takich jak `Invoke-NWChem.psm1` w systemie Windows, może być konieczne zmiana zasad wykonywania.
> Aby to zrobić, uruchom polecenie `Set-ExecutionPolicy`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> Zasady wykonywania zostaną następnie przywrócone po zakończeniu działania programu PowerShell.
> Jeśli chcesz zapisać zasady wykonywania, użyj innej wartości dla `-Scope`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Teraz powinno być dostępne `Convert-NWChemToBroombridge` polecenie:

```powershell
Get-Command -Module InvokeNWChem
```

Następnie zaimportujemy polecenie `Get-GateCount` dostarczone z przykładem **GetGateCount** .
Aby uzyskać szczegółowe informacje, zobacz [instrukcje dostarczone z przykładem](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/GetGateCount).
Następnie uruchom następujące polecenie, podstawiając `<runtime>` z `win10-x64`, `osx-x64`lub `linux-x64`, w zależności od systemu operacyjnego:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Teraz powinno być dostępne `Get-GateCount` polecenie:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Pokłady wejściowe ##

Pakiet NWChem przyjmuje plik tekstowy o nazwie _pokład wejściowy_ , który określa problem z chemią Quantum, który ma zostać rozwiązany, wraz z innymi parametrami, takimi jak ustawienia alokacji pamięci.
Na potrzeby tego przykładu użyjemy jednego z wstępnie utworzonych pokładów wejściowych, które są dostarczane z NWChem.
Najpierw Sklonuj [repozytorium nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):

> [!NOTE]
> Ponieważ jest to bardzo duże repozytorium, możemy wykonać płytki klonowania, aby zaoszczędzić pewną przepustowość i miejsce na dysku przy użyciu argumentu `--depth 1`.
> Jest to jednak opcjonalne.
> Klonowanie będzie działać prawidłowo, bez `--depth 1`.

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

Repozytorium `nwchemgit/nwchem` obejmuje różne pokłady wejściowe przeznaczone do użycia z zestawem SDK usługi Quantum, które znajdują się w [folderze`QA/chem_library_tests`](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).
W tym przykładzie użyjemy `H4`owego pokładu:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

Dana cząsteczka to system 4 atomów wodoru, które są ułożone w pewnej geometrii, która zależy od jednego kąta, parametr `alpha` jak wskazano w nazwie `h4_sto6g_alpha.nw` talii. H4 jest znanym [wzorcem molekularnym](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) dla chemii obliczeniowej od 1970s. Parametr `sto6g` ma charakter wskazujący, że pokład implementuje reprezentację w odniesieniu do typu "Slater", w związku z czym, w odniesieniu do [Ustawienia podstawy konie-ng](https://en.wikipedia.org/wiki/STO-nG_basis_sets) z 6 funkcjami bazowymi. Ten pokład wejściowy zawiera kilka instrukcji dotyczących aparatu wykonawcy NWChem (TCE), który kieruje NWChem w celu utworzenia informacji niezbędnych do współdziałania z zestawem Quantum Development Kit:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Produkowanie i zużywanie danych wyjściowych Broombridge z NWChem ##

Masz teraz wszystko, czego potrzebujesz, aby tworzyć i korzystać z dokumentów Broombridge.
Aby uruchomić program NWChem i utworzyć dokument Broombridge dla `h4_sto6g_0.000.nw` wejściowego, uruchom `Convert-NWChemToBroombridge`:

> [!NOTE]
> Przy pierwszym uruchomieniu tego polecenia program Docker pobierze obraz `nwchemorg/nwchem-qc`.
> Może to potrwać trochę czasu, w zależności od szybkości połączenia, dzięki czemu można uzyskać dostęp do filiżanki kawy.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Spowoduje to wygenerowanie dokumentu Broombridge o nazwie `h4_sto6g_0.000.yaml`, którego można użyć z `Get-GateCount`:

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Teraz powinny być widoczne dane wyjściowe konsoli zawierające oszacowanie zasobów, takie jak T-Count, liczba obrotów, liczba CNOT itp. dla różnych metod symulacji Quantum:

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

Istnieje wiele rzeczy, które należy wykonać w tym miejscu: 
- Wypróbuj różne wstępnie zdefiniowane talie wejściowe, np. przez zmianę parametru `alpha` w `h4_sto6g_alpha.nw`, 
- Spróbuj zmodyfikować talie, edytując talie NWChem bezpośrednio, np. Eksplorowanie modeli `STO-nG` w różnych wyborach n, 
- Wypróbuj inne wstępnie zdefiniowane pokłady wejściowe NWChem, które są dostępne w `nwchem/qa/chem_library_tests`,
- Wypróbuj pakiet wstępnie zdefiniowanych testów porównawczych Broombridge YAML, które zostały wygenerowane z NWChem i są dostępne jako część [repozytorium Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML). Te testy porównawcze obejmują: 
    - małe cząsteczek, takie jak wodór wodoru (H2), beryl (hydride), litu (LiH),
    - większe cząsteczek, takie jak ozon (O3), beta-karoten, cytosine i wiele innych. 
- Wypróbuj graficzną [strzałkę EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) frontonu, która oferuje interfejs do Microsoft Quantum Development Kit. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Tworzenie danych wyjściowych Broombridge z strzałek EMSL ##

Aby rozpocząć pracę z EMSL strzałkami frontonu opartymi na sieci Web, w [tym miejscu](https://arrows.emsl.pnnl.gov/api/qsharp_chem)przejdź do przeglądarki. 

> [!NOTE]
> Uruchamianie strzałek EMSL w przeglądarce internetowej wymaga włączenia języka JavaScript. Zapoznaj się z tymi [instrukcjami](https://www.enable-javascript.com/) dotyczącymi sposobu włączania języka JavaScript w przeglądarce. 

Najpierw wprowadź cząsteczkę w polu zapytania, które mówi ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Można wprowadzić wiele cząsteczek według ich nazwy Colloquial, na przykład "kofeiny" zamiast "1, 3, 7-trimethylxanthine". 

Następnie kliknij przycisk, który ma ``theory{qsharp_chem}``. Spowoduje to zapełnienie pola zapytania instrukcją, która będzie informować o przebiegu eksportowania danych wyjściowych w formacie Broombridge YAML. 

Teraz zegar ``Run Arrows``. W zależności od rozmiaru danych wejściowych może to chwilę potrwać. Lub, na wypadek, gdyby określony model został już wcześniej obliczony, można to zrobić bardzo szybko, ponieważ będzie to miało miejsce tylko w odniesieniu do wyszukiwania w bazie danych. W obu przypadkach nastąpi przekierowanie do nowej strony, która zawiera mnóstwo informacji o konkretnym przebiegu NWChem na pokładzie określonym przez dane wejściowe. 

Plik Broombridge YAML można pobrać i zapisać z sekcji, która rozpoczyna się od następującego nagłówka: 
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

Kliknij ``download``, co spowoduje zapisanie kopii lokalnej z unikatową nazwą pliku, taką jak ``qsharp_chem48443.yaml`` (określona nazwa będzie inna dla każdego przebiegu). Następnie można przetworzyć ten plik jak powyżej, np., z 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
Aby uzyskać liczbę zasobów. 

Można korzystać z konstruktora cząsteczkowego 3D, do którego można uzyskać dostęp z karty ``Arrows Entry - 3D Builder`` na stronie początkowej strzałek EMSL. Kliknięcie obrazu 3D [JSMol](http://wiki.jmol.org/index.php/JSmol) pokazanej cząsteczki umożliwi jego edytowanie. Można przenieść atomy dookoła, a następnie przeciągnąć atomy, tak aby ich odległości między cząsteczkami były zmieniane, dodawać i usuwać atomy itp. Dla każdej z tych opcji, po dodaniu ``theory{qsharp_chem}`` w polu zapytania, można wygenerować wystąpienie schematu Broombridge YAML i przeanalizować je przy użyciu biblioteki chemii Quantum. 
