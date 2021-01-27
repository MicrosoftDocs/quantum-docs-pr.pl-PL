---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 70cd18f04cbd449f4818ba3b40580303137f84db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857629"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="688fa-102">BlockEncoding typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="688fa-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="688fa-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="688fa-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="688fa-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="688fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="688fa-105">Reprezentuje jednostkę, w której dowolny operator zainteresowań jest zakodowany w bloku znajdującym się w lewym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="688fa-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="688fa-106">Oznacza to, że `BlockEncoding` jest jednostkowym $U $, gdzie arbitralny operator $H $ interesu, który działa w rejestrze systemu, `s` jest zakodowany w bloku znajdującym się w lewym górnym rogu odpowiadającym stanowi pomocniczemu $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="688fa-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="688fa-107">Czyli</span><span class="sxs-lookup"><span data-stu-id="688fa-107">That is,</span></span>

<span data-ttu-id="688fa-108">$ $ \begin{align} (\bra {0} _A \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="688fa-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

