---
title: Instalacja biblioteki liczb i walidacja | Microsoft Docs
description: Instalacja biblioteki liczb i walidacja
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: c41bb73ea484271689eea2ca1b59ce6639dc15a7
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036461"
---
# <a name="numerics-library-installation-and-validation"></a>Instalacja biblioteki liczb i walidacja

Zestaw Quantum Development Kit zapewnia obsługę funkcji liczbowych za pomocą pakietu NuGet [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .

**Program Visual Studio > = 2019:** Jeśli używasz programu Visual Studio 2019 lub nowszego, możesz dodać pakiet liczbowy przy użyciu Menedżera pakietów NuGet.
Aby to zrobić, wybierz pozycję "Zarządzaj pakietami NuGet..." z elementu menu "projekt" w programie Visual Studio.

Na karcie Przeglądaj Wyszukaj nazwę pakietu "Microsoft. Quantum. Numerics".

> [!NOTE]
> Upewnij się, że jest to znaczniki "Uwzględnij wersję wstępną"

Spowoduje to wyświetlenie listy pakietów dostępnych do pobrania.
Umieszczenie wskaźnika myszy na "Microsoft. Quantum. Numerics" powoduje wyświetlenie strzałki skierowanej w dół z prawej strony numeru wersji.
Kliknij strzałkę w celu zainstalowania pakietu liczbowego.

Aby uzyskać więcej informacji, zobacz [Przewodnik po interfejsie użytkownika Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternatywnie można użyć konsoli Menedżera pakietów, aby dodać bibliotekę liczbową do projektu za pomocą interfejsu wiersza polecenia.

![](../../media/vs2017-nuget-console-menu.png)

W konsoli Menedżera pakietów Uruchom następujące polecenie:

```
Install-Package Microsoft.Quantum.Numerics
```

Aby uzyskać więcej informacji, zobacz [Przewodnik po konsoli Menedżera pakietów](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Wiersz polecenia lub Visual Studio Code:** Przy użyciu wiersza polecenia lub z poziomu Visual Studio Code można użyć polecenia `dotnet`, aby dodać odwołanie do pakietu NuGet do projektu:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Weryfikowanie instalacji

Podobnie jak w przypadku reszty zestawu Quantum Development Kit, biblioteka liczbowa zawiera przykłady, które ułatwiają rozpoczęcie pracy jak najszybciej.
Aby przetestować instalację przy użyciu tych przykładów, Sklonuj [repozytorium głównych przykładów](https://github.com/Microsoft/Quantum) , a następnie uruchom jeden z przykładów.

Aby uruchomić przykład [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
