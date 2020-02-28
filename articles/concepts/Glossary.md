---
title: Słownik przetwarzania Quantum
description: Słownik typowych warunków, akcji i obiektów używanych w ramach przetwarzania Quantum.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: f47d87f5bc9d677baa12a7ac1581af72894e8a4b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909895"
---
# <a name="quantum-computing-glossary"></a>Słownik przetwarzania Quantum

|Okres|Definicja|
|-------------|----------|
|Sąsiadująco|Złożone sprzężenie sprzężone operacji. W przypadku operacji implementujących operator jednostki sąsiednie jest odwrotność operacji.|
|Żądanie|Operacje i funkcje są nazywane zbiorczo jako *możliwymi*do przeniesień.|
|Standard|Operacje i funkcje zdefiniowane w Q # Kompilowanie w logice zdefiniowanej w Preludium. Implementacja biblioteki standardowej jest niezależny od w odniesieniu do komputerów docelowych.|
|Grupa Clifford|Zestaw operacji, które zajmują octants sfery Bloch. Należą do nich: `X`, `Y`, `Z`, `H` i `S`|
|Kontrolowane|Operacja Quantum, która przyjmuje co najmniej jeden qubits jako element do obsługi dla operacji docelowej.|
|Notacja Dirac|Skrócona reprezentacja stanu Quantum. Aby uzyskać więcej informacji, zobacz sekcję dotyczącą [notacji Dirac](xref:microsoft.quantum.concepts.dirac) .|
|Eigenvalues i Eigenvectors|Szczegółowe informacje znajdują się w [sekcji Advanced Matrix](xref:microsoft.quantum.concepts.matrix-advanced) .|
|Para EPR|Znany również jako [stan dzwonka](https://en.wikipedia.org/wiki/Bell_state)|
|Działanie|Jak zmienia się stan na czas. Zapoznaj się z sekcją <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials> na przykład. |
|Funkcja|Czysto klasyczne procedury w języku Q #|
| <a id="global-phase"></a>Faza globalna | Dwa stany, które są identyczne do wielokrotności liczby zespolonej $e ^ {i\phi} $, są określane jako różne fazy globalne. W przeciwieństwie do faz lokalnych, fazy globalne nie mogą być przestrzegane przez żadne pomiary. Aby uzyskać więcej informacji, zobacz [miary Pauli](xref:microsoft.quantum.concepts.pauli) . |
|Miara|Uzyskanie klasycznego bitu z qubit (lub zestawu qubits). Aby uzyskać więcej informacji, zobacz sekcję [pojęcia qubit](xref:microsoft.quantum.concepts.qubit) .|
|Modyfikowalny|Zmienna, której wartość może zostać zmieniona po utworzeniu.|
|Przestrzeń nazw|Etykieta kolekcji pokrewnych nazw (zazwyczaj operacje, funkcje i typy). Na przykład przestrzeń nazw [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) etykiety wszystkich symboli zdefiniowanych w standardowej bibliotece, która pomaga w przygotowywaniu Stanów początkowych.|
|Operacja|Podstawowa jednostka wykonywania Quantum w Q #. Jest ona w przybliżeniu odpowiednikiem funkcji w języku C, C++ lub Python albo metody statycznej w języku C# lub Java.|
|Aplikacja operatora|Wykonywanie operacji Quantum. Zwykle jest to stosowana macierz jednostkowa do bieżącego wektora stanu. Aby uzyskać więcej informacji [, zobacz Wprowadzenie do koncepcji Quantum](xref:microsoft.quantum.concepts.intro) .|
|Oracle|Podprocedura, która dostarcza informacje zależne od danych do algorytmu Quantum w czasie wykonywania. Zazwyczaj celem jest zapewnienie nadmiaru danych wyjściowych odpowiadających danym wejściowym, które znajdują się w położeniu.   |
|Aplikacja częściowa|Wywoływanie funkcji lub operacji bez wszystkich wymaganych parametrów. Zwraca nowe żądanie, które wymaga tylko brakujących parametrów dostarczonych podczas przyszłej aplikacji.|
|Operatory Pauli|`X`, `Y` i `Z` bram Quantum.|
|Preludium|Zestaw operacji pierwotnych i klasycznych zdefiniowanych przez poszczególne maszyny docelowe, a nie na poziomie Q #.|
|Obwód Quantum|Reprezentacja programu dla komputera Quantum. Aby uzyskać więcej informacji, zobacz sekcję <xref:microsoft.quantum.concepts.circuits>.|
|Stan Quantum|Reprezentacja qubits w systemie. Ta wartość jest zwykle oznaczona jako złożona wektor kolumn. Aby uzyskać więcej informacji, zobacz <xref:microsoft.quantum.concepts.vectors>. |
|Qubit|Jednostka magazynu Quantum. Aby uzyskać więcej informacji, zobacz sekcję <xref:microsoft.quantum.concepts.qubit>.|
|Powtarzaj-do-sukces|Algorytm Quantum, który probabilistically się pomyślnie. W przypadku niepowodzenia procedura zostanie ponowiona do momentu pomyślnego (lub limit został osiągnięty). |
|Maszyna docelowa|Element docelowy kompilacji, który obniża abstrakcyjny program Quantum do sprzętu lub symulacji. Obejmuje to zwykle ponowne zapisy w wielu celach, w tym zastępowanie bram, kodowanie dla korekcji błędów, układ geometryczny i inne.|
|Spoin|Rozdzielane przecinkami typy zgrupowane razem za pośrednictwem nawiasów. |
|Typ zdefiniowany przez użytkownika|Kolekcja wbudowanych lub wcześniej zdefiniowanych typów, które mogą być określane jako pojedyncza jednostka.|

