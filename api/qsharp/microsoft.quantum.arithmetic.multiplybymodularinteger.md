---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719793"
---
# <a name="multiplybymodularinteger-operation"></a>MultiplyByModularInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Wykonuje mnożenie modularne przez stałą całkowitą w rejestrze qubit.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Opis

Poinformuj nas `modulus` o $N $ i `constMultiplier` $a $.
Następnie ta operacja implementuje operacje jednostkowe zdefiniowane przez następującą mapę w oparciu o obliczenia: $ $ \begin{align} \ket{y} \mapsto \ket{(\cdot y) \operatorname{mod} N} \end{align} $ $ dla wszystkich $y $ między $0 $ i $N – $1.

## <a name="input"></a>Dane wejściowe

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Stała, przez którą mnożnik jest mnożony. Musi być współdzielone z modułem.


### <a name="modulus--int"></a>Moduł: [int](xref:microsoft.quantum.lang-ref.int)

Operacja mnożenia jest wykonywana modulo `modulus` .


### <a name="multiplier--littleendian"></a>mnożnik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Liczba pomnożona przez stałą.
Jest to tablica qubits kodowania liczby całkowitej w formacie little-endian.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

- Aby zapoznać się ze schematem obwodu i wyjaśnieniem, zobacz rysunek 7 na [stronie 8 ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- Ta operacja odnosi się do p ₐ w [ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)