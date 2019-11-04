---
title: Stos oprogramowania | Microsoft Docs
description: Stos oprogramowania
author: QuantumWriter
uid: microsoft.quantum.concepts.software-stack
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f97dfacf6cde5fa92e1f368efaae36554a5c944d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184733"
---
# <a name="software-stack-for-quantum-computing"></a>Stos oprogramowania dla przetwarzania Quantum
Zwykle gdy sądzimy, że komputer Envision pojedyncze urządzenie z działającą aplikacją, ale nowoczesne środowiska obliczeniowe są znacznie bardziej skomplikowane i zaawansowane. Aplikacja, z którą prowadzimy działania, zazwyczaj działa na wielu warstwach oprogramowania, które zapewniają wykonanie aplikacji na poziomie sprzętu. Te warstwy oprogramowania są niezbędne do podzielenia rozwoju rozwiązania aplikacji od podstawowej złożoności całego systemu obliczeniowego. Jeśli deweloper musiał myśleć o magistrali, architekturach pamięci podręcznej, protokołach komunikacyjnych i nie tylko podczas pisania prostej aplikacji Smartphone, zadanie stanie się znacznie bardziej skomplikowane.  Koncepcja *stosu oprogramowania* została opracowana w ramach klasycznego przetwarzania danych w celu rozwiązania tych problemów.  Po zażyczeniu od klasycznej koncepcji stos oprogramowania jest również kluczową częścią wizji związanej z przetwarzaniem w usłudze Quantum za pomocą Q #.

## <a name="conventional-stack"></a>Konwencjonalny stos
Najważniejszym pomysłem związanym ze stosem oprogramowania jest rekursja.  Składa się z kilku zagnieżdżonych warstw interfejsów, które dzielą szczegóły niższych poziomów urządzenia od dewelopera.  Na przykład często używany stos oprogramowania obejmuje uruchamianie ASP.NET (język programowania), w oparciu o program SQL Server (system zarządzania relacyjnymi bazami danych), który działa w oparciu o Internet Information Services (serwer sieci Web), który działa na górze systemu Windows Server (a system operacyjny), który jest dyskiem sprzętowym.  Oglądając oprogramowanie jako hierarchia, jeden może napisać oprogramowanie w ASP.NET bez konieczności zrozumienia szczegółów niskiego poziomu wszystkich programów znajdujących się poniżej.

## <a name="quantum-stack"></a>Stos Quantum

Stos oprogramowania w ramach przetwarzania Quantum nie różni się w zasadzie, a w szczególności działa na niższym poziomie niż tradycyjne stosy.  Jak wygląda stos Quantum?  Komputer Quantum nie zastępuje tradycyjnych (często nazywanych klasycznymi) komputerów.  W rzeczywistości komputery z usługą Quantum niemal z pewnością pracują wspólnie z klasycznymi komputerami w celu rozwiązywania problemów obliczeniowych.  W części wynika to z niewrażliwości danych Quantum.  Dane Quantum są takie same, jak w przypadku niemal poprawienia szkody zaobserwowanej informacji.  W związku z tym należy zastanowić się, że komputery Quantum muszą zostać zaprojektowane z uwzględnieniem korekcji błędów Quantum, tak aby niedziałające interakcje ze środowiska fizycznego nie uszkadzali informacji i obliczeń. Z tego powodu naturalny element docelowy dla Q # to komputer z systemem Quantum, który został skorygowany do błędów (często nazywany komputerem z systemem Quantum z *odpornością na uszkodzenia* ), który akceptuje listę instrukcji Quantum (nazywanych bramami lub operacjami bram) i stosuje te instrukcje do Quantum dane przechowywane w tym elemencie.  Należy pamiętać, że jeśli liczba operacji qubits i bram w algorytmie Quantum lub programie jest wystarczająco mała, Korekcja błędów może nie być absolutnie konieczna.  Jednak w miarę wzrostu liczby operacji qubits i bram będzie to konieczne, a tym idzie, że nasz stos oprogramowania i Q # to aptly i wydajnie obsłużą korekcję błędów oraz umożliwiają skalowalne, odporne na błędy przetwarzanie Quantum.

### <a name="error-correction"></a>Korekcja błędów
Korekcja błędów wymaga szybkiego i niezawodnego klasycznego komputera, który można uruchomić w połączeniu z komputerem Quantum w celu poprawienia błędów w miarę ich występowania w obliczeniach Quantum.  W ramach tej działalności mogą być konieczne takie składniki jak tablice bram (FPGA) lub szybkie procesory zamrażające, aby identyfikować i poprawiać błędy szybciej niż w naturalny sposób na komputerze Quantum.  W związku z tym komputer Quantum jest maszyną hybrydową składającą się z kilku różnych urządzeń obliczeniowych, które działają w szerokim zakresie temperatur.  Z tego powodu znacznie bardziej pomocne jest zaplanowanie programowania komputera z systemem Quantum przy użyciu soczewki stosu oprogramowania, ponieważ istnieje wiele warstw sprzętu i oprogramowania (klasycznych i Quantum) wymaganych do ostatecznego osiągnięcia implementacji Quantum algorytm na komputerze Quantum.

### <a name="quantum-conceptual-stack"></a>Stos koncepcji Quantum
Poniżej przedstawiono stos koncepcyjny, który ilustruje przepływ funkcjonalny fabryki 8704143553785700723 w środowisku obliczeniowym Quantum:

![Stos oprogramowania](~/media/concepts_stack.png)

### <a name="specification-and-algorithm"></a>Specyfikacja i algorytm
Istnieje kilka szerokich etapów programowania takich obliczeń Quantum.  Pierwsze, i raczej najbardziej trudnej fazy, określa problem, który chce rozwiązać jeden z nich.  W takim przypadku przyczyną problemu jest współczynnik liczby 8704143553785700723 w iloczynie dwóch liczb.  Następny krok polega na opracowaniu algorytmu rozwiązywania tego problemu obliczeniowego.  W takim przypadku można użyć algorytmu refaktoryzacji skró sławę Quantum, aby znaleźć czynniki.  Ten algorytm jest wyrażony w p #, a następnie sekwencja operacji Quantum to dane wyjściowe, które można uruchomić na nieidealnym, niezależnym z błędami komputerem Quantum.  

### <a name="physical-gates"></a>Bramy fizyczne
W tym przykładzie zakłada się, że charakter nie jest tak oznaczany, aby zapewnić niezależny od błędów komputer Quantum, więc kolejny krok przyjmuje operacje emitowane przez Q # i tłumaczy je przy użyciu szablonów określonych przez metodę korekty błędów Quantum wybranych do bram fizycznych, które podstawowy sprzęt można wykonać.  Ten proces obejmuje wymianę wszystkich qubit logicznych opisanych w poprzednim modelu z hostem fizycznej qubits, które są używane do przechowywania i ochrony informacji w ramach jednego qubit w sposób nadmiarowy, który może odporny na błędy lokalne w składniku fizycznym. qubits wystarczająco długo, aby błędy zostały wykryte i poprawione.  Podobnie jak qubits logiczny opisany przez kod Q # musi zostać zastąpiony przez wiele fizycznych qubits, podobnie każda Brama Quantum opisana w danych wyjściowych musi być przetłumaczona na sekwencję fizycznych bram, które działają na fizycznym qubits.  Z tego powodu dane wyjściowe Q # najprawdopodobniej są ostatnim miejscem docelowym dla obliczeń opartych na systemie Quantum i dalsze poziomy abstrakcji są konieczne do wykonania kodu na sprzęcie w Oblivious sposób.

### <a name="control-computer"></a>Komputer kontrolny
Sekwencja bramy fizycznej jest następnie ładowana do zwykłego komputera, który wysyła te instrukcje w dół do komputera sterującego, który jest interfejsem bezpośrednio z komputerem Quantum.  Ta warstwa w stosie oprogramowania jest często obsługiwana przez eksperymentalne oprogramowanie sterujące, takie jak [QCoDeS](http://qcodes.github.io/Qcodes/).

### <a name="interface-computer"></a>Komputer interfejsu
Ostatni krok w tym procesie polega na tym, aby komputer interfejsu najpierw przesyłał strumieniowo bramy zgodnie z wymaganiami komputera szybkiego sterowania. Następnie komputer szybkiej kontroli stosuje napięcia wymagane (nazywane pulsami) w celu zaimplementowania wymaganych bram w systemie qubits. Należy to zrobić przy korygowaniu błędów, które są obserwowane poprzez korekcję błędów Quantum.  Aby wykonać te kroki w rygorystycznych wymaganiach czasowych narzuconych przez szybkość, z jaką błędy pojawiają się na komputerze Quantum, może być konieczne przeprowadzenie procedury zamrażania FPGA lub innego egzotycznego sprzętu.  Język docelowy na tym poziomie jest często [VHDL](https://en.wikipedia.org/wiki/VHDL), który wymaga odrębnego sposobu, aby zastanawiać się, który jest używany w górnym końcu stosu w celu przeanalizowania opisu algorytmu Quantum.

### <a name="the-q-quantum-programming-language"></a>Język programowania Q # Quantum
Celem pytania Q # jest zapewnienie prostego języka, który umożliwia deweloperom pisanie kodu, który jest przeznaczony dla bogactwa platform i interfejsów przetwarzania Quantum, za pomocą pośredniczących warstw oprogramowania, które są między użytkownikiem a urządzeniem Quantum.  Język ten ułatwia to poprzez uwzględnienie koncepcji stosu oprogramowania i abstrakcję wielu szczegółów podstawowego komputera z systemem Quantum, a jednocześnie pozwala na inne poziomy stosu udostępniane za pomocą języka, takiego jak C#, do wykonywania niezbędnych tłumaczenie z kodu Q # na operacje podstawowe.  Pozwala to deweloperom skupić się na tym, co robi najlepiej: projektowanie algorytmów i rozwiązywanie problemów.
