---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 1b769c58fd23b4ebc9d779cec3c47d8275822e5a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722693"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="c18cb-102">BlockEncoding typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="c18cb-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="c18cb-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c18cb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c18cb-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c18cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c18cb-105">Reprezentuje jednostkę, w której dowolny operator zainteresowań jest zakodowany w bloku znajdującym się w lewym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="c18cb-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="c18cb-106">Oznacza to, że `BlockEncoding` jest jednostkowym $U $, gdzie arbitralny operator $H $ interesu, który działa w rejestrze systemu, `s` jest zakodowany w bloku znajdującym się w lewym górnym rogu odpowiadającym stanowi pomocniczemu $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="c18cb-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="c18cb-107">Czyli</span><span class="sxs-lookup"><span data-stu-id="c18cb-107">That is,</span></span>

<span data-ttu-id="c18cb-108">$ $ \begin{align} (\bra {0} _A \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="c18cb-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

