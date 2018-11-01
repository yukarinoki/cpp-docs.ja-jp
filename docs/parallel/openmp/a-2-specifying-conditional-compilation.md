---
title: A.2 条件付きコンパイルの指定
ms.date: 11/04/2016
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
ms.openlocfilehash: 92ae22ffac1b1a1c3fc45a9a7a883203ff6d251e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491222"
---
# <a name="a2---specifying-conditional-compilation"></a>A.2 条件付きコンパイルの指定

次の例では、OpenMP マクロを使用して条件付きコンパイルの使用方法を示します`_OPENMP`([Section 2.2](../../parallel/openmp/2-2-conditional-compilation.md) [8] ページ)。 OpenMP のコンパイルと、`_OPENMP`マクロが定義されています。

```
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

定義済みプリプロセッサ演算子には、1 つのディレクティブでテストする 1 つ以上のマクロができます。

```
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```