---
title: インライン アセンブリの最適化
ms.date: 08/30/2018
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
ms.openlocfilehash: a558761ff49c2b508a5bad6172cda2283801e30e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191730"
---
# <a name="optimizing-inline-assembly"></a>インライン アセンブリの最適化

**Microsoft 固有の仕様**

関数にブロックが存在すると、 **`__asm`** いくつかの方法で最適化に影響します。 まず、コンパイラはブロック自体を最適化しようとしません **`__asm`** 。 アセンブリ言語で記述する内容は、厳密に取得したものです。 次に、ブロックが存在すると、 **`__asm`** レジスタ変数ストレージに影響します。 コンパイラは、 **`__asm`** レジスタの内容がブロックによって変更された場合に、ブロック全体での変数の登録を回避し **`__asm`** ます。 最後に、関数内でアセンブリ言語を含めることによって、関数全体の最適化が影響を受けます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インラインアセンブラー](../../assembler/inline/inline-assembler.md)<br/>
