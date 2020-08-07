---
title: Korzystanie z dodatkowych Q# bibliotek
description: Dowiedz się, jak dodać dodatkowe Q# biblioteki do aplikacji Quantum.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: ef88ca765a394a7092eb0a60bf6f3615c082ef6a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869583"
---
# <a name="using-additional-no-locq-libraries"></a>Korzystanie z dodatkowych Q# bibliotek

Zestaw Quantum Development Kit udostępnia dodatkowe funkcje specyficzne dla domeny za pomocą _pakietów NuGet_ , które można dodać do Q# projektów.

| Q#Biblioteki  | Pakiet NuGet | Uwagi |
|---------|---------|--------|
| [Q#Biblioteka standardowa](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. Quantum. Standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Uwzględnione domyślnie |
| [Biblioteka dla chemii kwantowej](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Biblioteka dla liczb kwantowych](xref:microsoft.quantum.numerics.intro) | [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Biblioteka dla kwantowego uczenia maszynowego](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Po zainstalowaniu zestawu Quantum Development Kit do użycia z preferowanym środowiskiem i językiem hosta możesz łatwo dodać biblioteki do poszczególnych Q# projektów bez żadnej dalszej instalacji.

> [!NOTE]
> Niektóre Q# biblioteki mogą współpracować z dodatkowymi narzędziami, które działają razem z Q# programami lub które integrują się z aplikacjami hosta.
> Na przykład [instrukcje instalacji biblioteki chemicznej](xref:microsoft.quantum.chemistry.concepts.installation) opisują, jak używać pakietu [ **Microsoft. Quantum. chemii** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) wraz z NWChem obliczeniową, a także jak instalować `qdk-chem` narzędzia wiersza polecenia do pracy z danymi chemii Quantum.

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[Q#aplikacje wiersza polecenia lub współdziałanie z platformą .NET](#tab/tabid-csproj)

**Wiersz polecenia lub Visual Studio Code:** Przy użyciu wiersza polecenia lub z poziomu Visual Studio Code można użyć `dotnet` polecenia, aby dodać odwołanie do pakietu NuGet do projektu.
Aby na przykład dodać pakiet [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) , uruchom następujące polecenie:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Program Visual Studio:** Jeśli używasz programu Visual Studio 2019 lub nowszego, możesz dodać dodatkowe Q# pakiety przy użyciu Menedżera pakietów NuGet.
Aby załadować pakiet: 
1. Mając otwarty projekt w programie Visual Studio, wybierz pozycję **Zarządzaj pakietami NuGet...** z menu **projekt** .

2. Kliknij przycisk **Przeglądaj**, wybierz opcję **Uwzględnij wersję wstępną** i wyszukaj nazwę pakietu "Microsoft. Quantum. Numerics". Spowoduje to wyświetlenie listy pakietów dostępnych do pobrania.

3. Zatrzymaj wskaźnik myszy na **Microsoft. Quantum. Numerics** i kliknij strzałkę w dół znajdującą się po prawej stronie numeru wersji, aby zainstalować pakiet liczbowy.

Aby uzyskać więcej informacji, zobacz [Przewodnik po interfejsie użytkownika Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternatywnie można użyć konsoli Menedżera pakietów, aby dodać bibliotekę liczbową do projektu za pomocą interfejsu wiersza polecenia.

![Korzystanie z konsoli Menedżera pakietów z poziomu wiersza polecenia](~/media/vs2017-nuget-console-menu.png)

W konsoli Menedżera pakietów Uruchom następujące polecenie:

```
Install-Package Microsoft.Quantum.Numerics
```

Aby uzyskać więcej informacji, zobacz [Przewodnik po konsoli Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-console).

## <a name="ino-locq-notebooks"></a>[Q#Notesy I](#tab/tabid-notebook)

Można udostępnić dodatkowe pakiety do użycia w notesie I za Q# pomocą [ `%package` polecenia Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).
Aby na przykład dodać pakiet [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) do użycia w Q# notesie I, uruchom następujące polecenie w komórce notesu:

```
%package Microsoft.Quantum.Numerics
```

Po tym poleceniu pakiet jest dostępny dla wszystkich komórek w notesie.
Aby udostępnić pakiet z Q# kodu w bieżącym obszarze roboczym, Załaduj ponownie obszar roboczy po dodaniu pakietu:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Współdziałanie języka Python](#tab/tabid-python)


Dodatkowe pakiety mogą być dostępne do użycia w programie hosta Python przy użyciu [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) metody.
Aby na przykład dodać pakiet [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) do użycia w Q# notesie I, uruchom następujący kod w języku Python:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Po wykonaniu tego polecenia pakiet zostanie udostępniony dla dowolnego Q# kodu skompilowanego przy użyciu `qsharp.compile` .
Aby udostępnić pakiet z Q# kodu w bieżącym obszarze roboczym, Załaduj ponownie obszar roboczy po dodaniu pakietu:

```python
qsharp.reload()
```

***
