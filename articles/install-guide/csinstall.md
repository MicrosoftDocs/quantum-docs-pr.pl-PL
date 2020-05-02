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
# <a name="using-q-with-c-and-f"></a>Używanie Q # z C\# i F\#

Program Q # jest zbudowany z użyciem języków .NET, takich jak C# i F #.
W tym przewodniku pokazano, jak używać Q # z programem hosta zapisaną w języku .NET.

## <a name="prerequisites"></a>Wymagania wstępne

- Zainstaluj zestaw Quantum Development Kit [do użycia z projektami wiersza polecenia Q #](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Tworzenie biblioteki Q # i hosta .NET

Pierwszym krokiem jest utworzenie projektów dla biblioteki Q # oraz dla hosta .NET, który będzie wywoływał operacje i funkcje zdefiniowane w bibliotece Q #.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Utwórz nową bibliotekę Q #
  - Przejdź do **pliku** -> **Nowy** -> **projekt**
  - Wpisz "Q #" w polu wyszukiwania
  - Wybierz **bibliotekę Q #**
  - Wybierz pozycję **dalej**
  - Wybierz nazwę i lokalizację biblioteki
  - Upewnij się, że pole "Umieść projekt i rozwiązanie w tym samym katalogu" nie jest **zaznaczone**
  - Wybierz pozycję **Utwórz**
- Tworzenie nowego programu hosta C# lub F #
  - Przejdź do **pliku** → **Nowy** → **projekt**
  - Wybierz pozycję "Aplikacja konsolowa (.NET Core") dla języka C# lub F #
  - Wybierz pozycję **dalej**
  - W obszarze *rozwiązanie*wybierz pozycję "Dodaj do rozwiązania".
  - Wybierz nazwę programu hosta
  - Wybierz pozycję **Utwórz**

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code lub wiersz polecenia](#tab/tabid-cmdline)

- Utwórz nową bibliotekę Q #

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Utwórz nowy projekt konsoli języka C# lub języka F #

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Dodaj bibliotekę Q # jako odwołanie z programu hosta

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- Obowiązkowe Utwórz rozwiązanie dla obu projektów

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>Wywoływanie funkcji Q # z platformy .NET

Po skonfigurowaniu projektów zgodnie z powyższymi instrukcjami można wywołać polecenie Q # z aplikacji konsolowej platformy .NET.
Kompilator Q # utworzy klasy .NET dla każdej operacji Q # i funkcji, która pozwala na uruchamianie programów Quantum w symulatorze.

Na przykład przykład [współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) obejmuje następujący przykład operacji Q #:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Aby wywołać tę operację z platformy .NET w symulatorze Quantum, można użyć `Run` metody klasy `RunAlgorithm` .NET wygenerowanej przez kompilator Q #:

### <a name="c"></a>[S #](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a>Co dalej?

Teraz, gdy zestaw Quantum Development Kit jest skonfigurowany dla programów wiersza polecenia Q # i dla współdziałania z platformą .NET można napisać i uruchomić [pierwszy program Quantum](xref:microsoft.quantum.write-program).
