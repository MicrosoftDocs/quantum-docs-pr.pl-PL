---
title: Programowanie przy użyciu języka Q# i platformy .NET
description: Dowiedz się, jak utworzyć aplikację Q# przy użyciu języków platformy .NET.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: de79c361331766572f5608c341be766e071e01b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844306"
---
# <a name="develop-with-no-locq-and-net"></a>Programowanie przy użyciu języka Q# i platformy .NET

Język Q# został opracowany z myślą o współdziałaniu z językami platformy .NET, takimi jak C# i F#.
W tym przewodniku pokazujemy, jak używać języka Q# z programem hosta napisanym w języku platformy .NET.

Najpierw tworzymy aplikację w języku Q# i hosta na platformie .NET, a następnie pokazujemy, jak wywoływać język Q# z hosta.

## <a name="prerequisites"></a>Wymagania wstępne

- Zainstaluj zestaw Quantum Development Kit [do użycia z projektami w języku Q#](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-no-locq-library-and-a-net-host"></a>Tworzenie biblioteki języka Q# i hosta platformy .NET

Pierwszym krokiem jest utworzenie projektów biblioteki języka Q# oraz hosta platformy .NET, który będzie wywoływał operacje i funkcje zdefiniowane w bibliotece języka Q#.

Postępuj zgodnie z instrukcjami na karcie odpowiadającej Twojemu środowisku programistycznemu.
Jeśli używasz edytora innego niż Visual Studio lub VS Code, po prostu postępuj zgodnie z krokami wiersza polecenia.

### <a name="visual-studio-code-or-command-prompt"></a>[Program Visual Studio Code lub wiersz polecenia](#tab/tabid-cmdline)

- Utwórz nową bibliotekę języka Q#

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Utwórz nowy projekt konsolowy języka C# lub F#

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Dodaj bibliotekę języka Q# jako odwołanie w programie hosta

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [Opcjonalnie] Utwórz rozwiązanie dla obu projektów

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Utwórz nową bibliotekę języka Q#
  - Przejdź do pozycji **Plik** -> **Nowy** -> **Projekt**
  - Wpisz „Q#” w polu wyszukiwania
  - Wybierz pozycję **Biblioteka języka Q#**
  - Wybierz pozycję **Dalej**
  - Wybierz nazwę i lokalizację biblioteki
  - Upewnij się, że pole „Umieść projekt i rozwiązanie w tym samym katalogu” jest **niezaznaczone**
  - Wybierz pozycję **Utwórz**
- Utwórz nowy program hosta w języku C# lub F#
  - Przejdź do pozycji **Plik** → **Nowy** → **Projekt**
  - Wybierz pozycję „Aplikacja konsolowa (.NET Core)” dla języka C# lub F#
  - Wybierz pozycję **Dalej**
  - W obszarze *Rozwiązanie* wybierz pozycję „Dodaj do rozwiązania”
  - Wybierz nazwę programu hosta
  - Wybierz pozycję **Utwórz**

**_

## <a name="calling-into-no-locq-from-net"></a>Wywoływanie funkcji języka Q# z aplikacji platformy .NET

Po skonfigurowaniu projektów zgodnie z powyższymi instrukcjami można wywoływać funkcje języka Q# z aplikacji konsolowej platformy .NET.
Kompilator języka Q# utworzy klasy platformy .NET dla wszystkich operacji i funkcji języka Q#, co umożliwi uruchamianie programów kwantowych w symulatorze.

[Przykład współdziałania z platformą .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) zawiera następującą przykładową operację języka Q#:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Aby wywołać tę operację z poziomu aplikacji platformy .NET w symulatorze kwantowym, możesz użyć metody `Run` w klasie platformy .NET `RunAlgorithm` wygenerowanej przez kompilator języka Q#:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

_**
    
## <a name="next-steps"></a>Następne kroki

Po skonfigurowaniu zestawu Quantum Development Kit zarówno na potrzeby aplikacji w języku Q#, jak i współdziałania z platformą .NET, możesz napisać i uruchomić swój [pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).
