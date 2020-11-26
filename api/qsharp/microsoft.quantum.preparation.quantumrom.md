---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229889"
---
# <a name="quantumrom-function"></a>QuantumROM, funkcja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> QuantumROM jest przestarzała. Użyj <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> zamiast tego.

Używa techniki Quantum ROM do reprezentowania danej macierzy gęstości.

Po otrzymaniu listy $N $ współwydajnych $ \ alpha_j $, spowoduje to zwrócenie $U jednostkowej $, która używa metody Quantum-ROM do przygotowania przybliżenia $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ oczyszczania macierzy gęstości $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $. W tym przybliżeniu błąd $ \epsilon $ jest taki, że $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ i $ \| \tilde\rho-\rho \| \le \epsilon $. Innymi słowy, $ $ \begin{align} U\ket {0} ^ {\lceil\ Log_2 N\rceil} \ KET {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{garbage} _j}.
\end{align} $ $

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>Dane wejściowe

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Błąd elementu docelowego $ \epsilon $.


### <a name="coefficients--double"></a>współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]

Tablica współczynników $N $, określająca prawdopodobieństwo Stanów bazowych.
Liczby ujemne $-\ alpha_j $ będą traktowane jako dodatnie $ | \ alpha_j | $.



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a>Wynik: (([int](xref:microsoft.quantum.lang-ref.int)[, int,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> jest korektą i listą CTL)

## <a name="first-parameter"></a>Pierwszy parametr

Krotka `(x,(y,z))` `x = y + z` , gdzie jest łączna liczba przydzieloną qubits, `y` jest liczbą qubits dla `LittleEndian` rejestru i `z` jest liczbą qubits elementów bezużytecznych.

## <a name="second-parameter"></a>Drugi parametr

Jednostandardowa $ \ sum_j | \ alpha_j | $ tabeli współczynnika.

## <a name="third-parameter"></a>Trzeci parametr

$U jednostki $.

## <a name="references"></a>Odwołania

- Kodowanie elektronicznego spektrum w obwodach Quantum przy użyciu liniowej o złożoności T Babbush, Craig Gidney, Dominic W. Jagods, Nathana Wiebe, Jarrod McClean, Alexandru, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662