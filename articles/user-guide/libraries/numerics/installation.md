---
title: Biblioteka liczb Quantum firmy Microsoft — instalacja i weryfikacja
description: Dowiedz się, jak dodać bibliotekę numeryczną Quantum firmy Microsoft do instalacji programu Visual Studio 2019 lub nowszej.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276126"
---
# <a name="numerics-library-installation-and-validation"></a>Instalacja biblioteki liczb i walidacja

Zestaw Quantum Development Kit zapewnia obsługę funkcji liczbowych za pomocą [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) pakietu NuGet.

**Program Visual Studio >= 2019:** Jeśli używasz programu Visual Studio 2019 lub nowszego, możesz dodać pakiet liczbowy przy użyciu Menedżera pakietów NuGet.
Aby to zrobić, wybierz pozycję "Zarządzaj pakietami NuGet..." z elementu menu "projekt" w programie Visual Studio.

Na karcie Przeglądaj Wyszukaj nazwę pakietu "Microsoft. Quantum. Numerics".

> [!NOTE]
> Upewnij się, że jest to znaczniki "Uwzględnij wersję wstępną"

Spowoduje to wyświetlenie listy pakietów dostępnych do pobrania.
Umieszczenie wskaźnika myszy na "Microsoft. Quantum. Numerics" powoduje wyświetlenie strzałki skierowanej w dół z prawej strony numeru wersji.
Kliknij strzałkę w celu zainstalowania pakietu liczbowego.

Aby uzyskać więcej informacji, zobacz [Przewodnik po interfejsie użytkownika Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternatywnie można użyć konsoli Menedżera pakietów, aby dodać bibliotekę liczbową do projektu za pomocą interfejsu wiersza polecenia.

![Korzystanie z konsoli Menedżera pakietów z poziomu wiersza polecenia](~/media/vs2017-nuget-console-menu.png)

W konsoli Menedżera pakietów Uruchom następujące polecenie:

```
Install-Package Microsoft.Quantum.Numerics
```

Aby uzyskać więcej informacji, zobacz [Przewodnik po konsoli Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Wiersz polecenia lub Visual Studio Code:** Przy użyciu wiersza polecenia lub z poziomu Visual Studio Code można użyć `dotnet` polecenia, aby dodać odwołanie do pakietu NuGet do projektu:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Weryfikowanie instalacji

Podobnie jak w przypadku reszty zestawu Quantum Development Kit, biblioteka liczbowa zawiera przykłady, które ułatwiają rozpoczęcie pracy jak najszybciej.
Aby przetestować instalację przy użyciu tych przykładów, Sklonuj [repozytorium głównych przykładów](https://github.com/Microsoft/Quantum) , a następnie uruchom jeden z przykładów.

Aby uruchomić [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) przykład:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
