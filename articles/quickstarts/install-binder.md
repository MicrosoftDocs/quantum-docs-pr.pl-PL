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
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="87f23-103">Programowanie przy użyciu języka Q# i narzędzia Binder</span><span class="sxs-lookup"><span data-stu-id="87f23-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="87f23-104">Narzędzie Binder pozwala uruchamiać i udostępniać notesy Jupyter w trybie online.</span><span class="sxs-lookup"><span data-stu-id="87f23-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="87f23-105">Używanie narzędzia Binder z przykładami w zestawie QDK firmy Microsoft</span><span class="sxs-lookup"><span data-stu-id="87f23-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="87f23-106">Aby automatycznie skonfigurować narzędzie Binder do korzystania z przykładów w zestawie QDK firmy Microsoft:</span><span class="sxs-lookup"><span data-stu-id="87f23-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="87f23-107">Otwórz przeglądarkę i przejdź pod adres https://aka.ms/try-qsharp.</span><span class="sxs-lookup"><span data-stu-id="87f23-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="87f23-108">Na stronie docelowej **przykładów zestawu Quantum Development Kit** kliknij **notes Q#** , aby dowiedzieć się, jak używać jądra IQ# do pisania własnych notesów aplikacji kwantowych.</span><span class="sxs-lookup"><span data-stu-id="87f23-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![Strona docelowa zestawu QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="87f23-110">Używanie narzędzia Binder z własnymi notesami i repozytorium</span><span class="sxs-lookup"><span data-stu-id="87f23-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="87f23-111">Jeśli masz już notesy w repozytorium GitHub, możesz skonfigurować narzędzie Binder do pracy z tym repozytorium:</span><span class="sxs-lookup"><span data-stu-id="87f23-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="87f23-112">Upewnij się, że w katalogu głównym repozytorium istnieje plik o nazwie *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="87f23-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="87f23-113">Ten plik musi zawierać co najmniej następujące wiersze:</span><span class="sxs-lookup"><span data-stu-id="87f23-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="87f23-114">Najnowszą wersję jądra IQ# można sprawdzić w [informacjach o wersji](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="87f23-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="87f23-115">Aby uzyskać więcej informacji o tworzeniu pliku Dockerfile, zobacz [dokumentację pliku Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="87f23-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="87f23-116">W przeglądarce otwórz witrynę [mybinder.org](https://mybinder.org).</span><span class="sxs-lookup"><span data-stu-id="87f23-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="87f23-117">Wprowadź nazwę swojego repozytorium (na przykład *MojaNazwa/MojeRepozytorium*) jako wartość **GitHub URL** (Adres URL serwisu GitHub), a następnie kliknij pozycję **launch** (uruchom).</span><span class="sxs-lookup"><span data-stu-id="87f23-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![Formularz witryny MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="87f23-119">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="87f23-119">Next steps</span></span>

<span data-ttu-id="87f23-120">Po skonfigurowaniu środowiska narzędzia Binder możesz napisać i uruchomić [swój pierwszy program kwantowy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="87f23-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
