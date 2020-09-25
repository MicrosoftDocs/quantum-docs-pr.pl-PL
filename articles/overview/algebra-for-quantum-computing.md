---
title: Algebra liniowa na potrzeby obliczeń kwantowych
description: Dowiedz się, jakie podstawowe pojęcia algebry liniowej są potrzebne do zrozumienia obliczeń kwantowych
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
no-loc:
- Q#
- $$v
ms.openlocfilehash: bff1da475f87278bc9e769805b3fe0fe8704d47a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835132"
---
# <a name="linear-algebra-for-quantum-computing"></a>Algebra liniowa na potrzeby obliczeń kwantowych

Algebra liniowa jest językiem obliczeń kwantowych. Mimo że nie trzeba jej znać w celu implementowania lub pisania programów kwantowych, jest powszechnie używana do opisywania stanów kubitów, operacji kwantowych oraz do przewidywania działania komputera kwantowego w odpowiedzi na sekwencję instrukcji.

Podobnie jak znajomość [podstawowych pojęć dotyczących fizyki kwantowej](xref:microsoft.quantum.overview.understanding) może pomóc zrozumieć obliczenia kwantowe, znajomość podstawowej algebry liniowej może pomóc zrozumieć, jak działają algorytmy kwantowe. Warto zapoznać się przynajmniej z **wektorami** i **mnożeniem macierzy**. Jeśli chcesz odświeżyć wiedzę o tych pojęciach związanych z algebrą, oto kilka samouczków, które obejmują podstawowe informacje:

- [Samouczek w notesie Jupyter dotyczący algebry liniowej](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)
- [Samouczek w notesie Jupyter dotyczący arytmetyki zespolonej](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)
- [Algebra liniowa na potrzeby obliczeń kwantowych](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [Podstawy algebry liniowej](https://www.math.ubc.ca/~carrell/NB.pdf)
- [Podstawy obliczeń kwantowych](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>Wektory i macierze w obliczeniach kwantowych

W temacie [Informacje na temat obliczeń kwantowych](xref:microsoft.quantum.overview.understanding) pokazano, że kubit może być w stanie 1 lub 0 albo w obu tych stanach. Przy użyciu algebry liniowej stan kubitu jest opisany jako wektor i jest reprezentowany przez jedną kolumnę **matrix** $\begin{bmatrix} a \\\\ b \end{bmatrix}$. Jest on również znany jako **wektor stanu kwantowego** i musi spełniać wymaganie $|a|^2 + |b|^2 = 1$.  

Elementy macierzy przedstawiają prawdopodobieństwo, że kubit jest zwijany w jedną lub drugą stronę, gdzie $|a|^2$ jest prawdopodobieństwem zwinięcia do stanu 0, a $|b|^2$ jest prawdopodobieństwem zwinięcia do stanu 1. Następujące macierze reprezentują prawidłowe wektory stanu kwantowego:

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

W temacie [Komputery kwantowe i symulatory kwantowe](xref:microsoft.quantum.overview.simulators) również przedstawiono, że operacje kwantowe są używane do modyfikowania stanu kubitu.  Operacje kwantowe mogą być również reprezentowane przez macierz. Gdy operacja kwantowa jest stosowana do kubitu, dwie macierze reprezentujące je są mnożone i wynikowa odpowiedź reprezentuje nowy stan kubitu po zakończeniu operacji.  

Poniżej przedstawiono dwie typowe operacje kwantowe reprezentowane za pomocą mnożenia macierzy.


[Operacja `X`](xref:microsoft.quantum.intrinsic.x) jest reprezentowana przez macierz Pauliego $X$,

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
i służy do przerzucenia stanu kubitu z 0 do 1 (lub odwrotnie), na przykład

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

[Operacja „H”](xref:microsoft.quantum.intrinsic.h) jest reprezentowana przez transformację Hadamarda $H$,

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 i umieszcza kubit w stanie superpozycji, gdzie ma nawet prawdopodobieństwo zwinięcia w jedną ze stron, jak pokazano poniżej

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

Macierz, która reprezentuje operację kwantową ma jedno wymaganie — musi być macierzą **unitarną**. Macierz jest unitarna, jeśli **odwrócenie** macierzy jest równe **transponowaniu sprzężonemu** macierzy.

## <a name="representing-two-qubit-states"></a>Reprezentacja stanów dwóch kubitów

W powyższych przykładach stan jednego kubitu został opisany przy użyciu jednej kolumny matrix $\begin{bmatrix} a \\\\ b \end{bmatrix}$ i zastosowanie do niej operacji opisano przez pomnożenie dwóch macierzy. Jednak komputery kwantowe używają więcej niż jednego kubitu, więc w jaki sposób można opisać połączony stan dwóch kubitów? 

Należy pamiętać, że każdy kubit jest przestrzenią wektorową, więc nie można ich tylko przemnożyć. Zamiast tego należy użyć **iloczynu tensorowego**, który jest operacją powiązaną tworzącą nową przestrzeń wektorową z pojedynczych obszarów wektorowych i jest reprezentowany przez symbol $\otimes$. Na przykład jest obliczany iloczyn tensorowy stanów dwóch kubitów $\begin{bmatrix} a \\\\ b \end{bmatrix}$ i $\begin{bmatrix} c \\\\ d \end{bmatrix}$

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}. $$

Wynikiem jest czterowymiarowa macierz, której każdy element reprezentuje prawdopodobieństwo. Na przykład $ac$ to prawdopodobieństwo, że dwa kubity zostaną zwinięte do stanu 0 i 0, $ad$ jest prawdopodobieństwem stanów 0 i 1 itd. 

Podobnie jak stan 1 kubitu $\begin{bmatrix} a \\\\  b \end{bmatrix}$ musi spełniać wymaganie $|a|^2 + |b|^2 = 1$, aby reprezentować stan kwantowy, stan 2 kubitów $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ musi spełniać wymaganie $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.

## <a name="summary"></a>Podsumowanie

Algebra liniowa jest standardowym językiem do opisywania obliczeń kwantowych i fizyki kwantowej. Mimo że [biblioteki](xref:microsoft.quantum.libraries) dołączone do zestawu Microsoft Quantum Development Kit pomogą Ci uruchamiać zaawansowane algorytmy kwantowe bez szczegółowych zapisów matematycznych, zrozumienie podstaw pomoże Ci szybko rozpocząć pracę i zapewnić solidną podstawę do dalszego tworzenia.

## <a name="next-steps"></a>Następne kroki

[Instalowanie zestawu QDK](xref:microsoft.quantum.install)
