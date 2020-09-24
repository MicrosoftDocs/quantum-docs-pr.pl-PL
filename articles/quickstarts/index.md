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
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834486"
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

|&nbsp; | **VS Code<br>(2019 lub nowszy)**| **Visual Studio<br>(2019 lub nowszy)** | **Notesy programu Jupyter** | **Wiersz polecenia**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**System operacyjny** |Windows, macOS, Linux |Tylko Windows |Windows, macOS, Linux |Windows, macOS, Linux |
|<br>**Autonomiczny język Q#** |<br>[Instalacja](xref:microsoft.quantum.install.standalone) |<br> [Instalacja](xref:microsoft.quantum.install.standalone)  |<br> [Instalacja](xref:microsoft.quantum.install.jupyter) |<br>[Instalacja](xref:microsoft.quantum.install.standalone)|
|**Język Q# i język Python** |[Instalacja](xref:microsoft.quantum.install.python) |[Instalacja](xref:microsoft.quantum.install.python) |[Instalacja](xref:microsoft.quantum.install.jupyter) |[Instalacja](xref:microsoft.quantum.install.python) |
|**Język Q# i platforma .NET (C#, F#)**|[Instalacja](xref:microsoft.quantum.install.cs) |[Instalacja](xref:microsoft.quantum.install.cs)|&#10006; |[Instalacja](xref:microsoft.quantum.install.cs) |

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
