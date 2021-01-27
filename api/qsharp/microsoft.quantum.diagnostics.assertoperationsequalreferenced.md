---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853462"
---
# <a name="assertoperationsequalreferenced-operation"></a>AssertOperationsEqualReferenced, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dwie operacje, potwierdzają, że działają identycznie dla wszystkich stanów wejściowych.

To potwierdzenie jest implementowane za pomocą Choi – Jamiołkowski isomorphism, aby ograniczyć potwierdzenie do jednego z potwierdzeń stanu qubit na dwóch rejestrach Entangled.
W rezultacie ta operacja wymaga tylko jednego wywołania dla każdej testowanej operacji, ale wymaga dwukrotnego przydzielenia qubits.
To potwierdzenie może służyć do upewnienia się, że na przykład, że zoptymalizowana wersja operacji działa identycznie z implementacją algorytmie, lub że operacja, która działa w zakresie danych wejściowych innych niż Quantum, zgadza się ze znanymi przypadkami.

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits do przekazania do każdej operacji.


### <a name="actual--qubit--unit"></a>rzeczywista: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja do przetestowania.


### <a name="expected--qubit--unit--is-adj"></a>Oczekiwano: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja definiująca oczekiwane zachowanie testowanej operacji.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Ta operacja wymaga, aby model operacji modelował oczekiwane zachowanie, tak aby można było wykonać operację odwrotną dla samego rejestru docelowego.
Jeden z nich może określać transpozycję operacji, która powoduje, że to wymaganie, ale operacja transpozycji nie jest ogólnie obsługiwana w przypadku dowolnych operacji Quantum i w tym przypadku nie jest uwzględniona w tym miejscu jako opcja.