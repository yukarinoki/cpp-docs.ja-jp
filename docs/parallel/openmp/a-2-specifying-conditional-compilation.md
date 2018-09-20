---
title: A.2 条件付きコンパイルの指定 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d8b0f3df67313dbf03d40077a551fe64930199d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393699"
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