---
title: Konfigurowanie zestawu Microsoft Quantum Development Kit (QDK)
description: Dowiedz się, jak skonfigurować zestaw Microsoft Quantum Development Kit dla różnych środowisk.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: f0c3df1998f9b64ff6544867b83a7afe52b6f46d
ms.sourcegitcommit: fd57a845d013ae4578715d04b1ed1edc1c8ff6b4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94870825"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>Konfigurowanie zestawu Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak skonfigurować zestaw Microsoft Quantum Development Kit (QDK) dla swojego środowiska, aby rozpocząć pracę z programowaniem kwantowym. Zestaw QDK składa się z:

- Język programowania Q#
- Zestaw bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#
- Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#
- Narzędzia ułatwiające programowanie

Programy w języku Q# mogą działać jako aplikacje autonomiczne przy użyciu programu Visual Studio Code lub Visual Studio albo za pośrednictwem notesów Jupyter Notebook za pomocą jądra Jupyter IQ# lub sparowane z programem nadrzędnym napisanym w języku Python lub języku platformy .NET (C#, F#). Możesz również uruchamiać programy w języku Q# w trybie online, używając platform [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) lub [Docker](#use-the-qdk-with-docker). 

## <a name="options-for-setting-up-the-qdk"></a>Opcje konfigurowania zestawu QDK

Zestawu QDK można używać na trzy sposoby:

- [Instalowanie zestawu QDK lokalnie](#install-the-qdk-locally)
- [Używanie zestawu QDK online](#use-the-qdk-online)
- [Używanie obrazu platformy Docker zestawu QDK](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>Instalowanie zestawu QDK lokalnie

Możesz opracowywać kod w języku Q# w większości ulubionych środowisk IDE, a także integrować język Q# z innymi językami, takimi jak język Python i języki platformy .NET (C#, F#).

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>VS Code<br>(2019 lub nowsza wersja)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="VS Studio" width="50"/><br><b>VS Studio<br>(2019 lub nowsza wersja)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Notesy programu Jupyter</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>Wiersz polecenia</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>Obsługa systemu operacyjnego:</b></td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Tylko Windows</td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Windows, macOS, Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>Autonomiczny język Q#</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalacja</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalacja</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">Instalacja</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalacja</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Język Q# i język Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalacja</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalacja</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">Instalacja</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalacja</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Język Q# i platforma .NET (C#, F#)</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalacja</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalacja</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalacja</a></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a>Używanie zestawu QDK online

Możesz również opracowywać kod w języku Q# bez instalowania czegokolwiek lokalnie, używając tych opcji:

|Zasób|Zalety|Ograniczenia|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|Zaawansowane środowisko deweloperskie online  |Wymaga planu i subskrypcji platformy Azure |
|[**Binder**](xref:microsoft.quantum.install.binder) | Bezpłatne środowisko notesu online |Bez trwałości |

## <a name="use-the-qdk-with-docker"></a>Używanie zestawu QDK z platformą Docker

Można użyć naszego obrazu platformy Docker zestawu QDK w lokalnej instalacji platformy Docker lub w chmurze za pośrednictwem dowolnej usługi, która obsługuje obrazy platformy Docker, takiej jak ACI.

Obraz platformy Docker języka IQ# można pobrać z witryny https://github.com/microsoft/iqsharp/#using-iq-as-a-container. 

Możesz również używać platformy Docker z kontenerem programowania zdalnego programu Visual Studio Code, aby szybko definiować środowiska deweloperskie. Aby uzyskać więcej informacji o kontenerach programowania VS Code, zobacz https://github.com/microsoft/Quantum/tree/master/.devcontainer.

## <a name="next-steps"></a>Następne kroki

Przepływy pracy dla każdej z tych konfiguracji są opisane i porównane w sekcji [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs).
