---
title: Programowanie przy użyciu języka Q# i narzędzia Binder
description: Dowiedz się, jak utworzyć aplikację Q# przy użyciu narzędzia Binder.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836557"
---
# <a name="develop-with-no-locq-and-binder"></a>Programowanie przy użyciu języka Q# i narzędzia Binder

Narzędzie Binder pozwala uruchamiać i udostępniać notesy Jupyter w trybie online.

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>Używanie narzędzia Binder z przykładami w zestawie QDK firmy Microsoft

Aby automatycznie skonfigurować narzędzie Binder do korzystania z przykładów w zestawie QDK firmy Microsoft:

1. Otwórz przeglądarkę i przejdź pod adres https://aka.ms/try-qsharp.
1. Na stronie docelowej **przykładów zestawu Quantum Development Kit** kliknij **notes Q#** , aby dowiedzieć się, jak używać jądra IQ# do pisania własnych notesów aplikacji kwantowych.

![Strona docelowa zestawu QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>Używanie narzędzia Binder z własnymi notesami i repozytorium

Jeśli masz już notesy w repozytorium GitHub, możesz skonfigurować narzędzie Binder do pracy z tym repozytorium:

1. Upewnij się, że w katalogu głównym repozytorium istnieje plik o nazwie *Dockerfile*. Ten plik musi zawierać co najmniej następujące wiersze:

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > Najnowszą wersję jądra IQ# można sprawdzić w [informacjach o wersji](xref:microsoft.quantum.relnotes).

    Aby uzyskać więcej informacji o tworzeniu pliku Dockerfile, zobacz [dokumentację pliku Dockerfile](https://docs.docker.com/engine/reference/builder/).

2. W przeglądarce otwórz witrynę [mybinder.org](https://mybinder.org).
3. Wprowadź nazwę swojego repozytorium (na przykład *MojaNazwa/MojeRepozytorium*) jako wartość **GitHub URL** (Adres URL serwisu GitHub), a następnie kliknij pozycję **launch** (uruchom).

![Formularz witryny MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a>Następne kroki

Po skonfigurowaniu środowiska narzędzia Binder możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).
