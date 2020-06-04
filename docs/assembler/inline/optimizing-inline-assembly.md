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
ms.openlocfilehash: 0051b16ddc19e233cfac2688c0b77e1e023f0833
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169267"
---
# <a name="optimizing-inline-assembly"></a>インライン アセンブリの最適化

**Microsoft 固有の仕様**

関数に `__asm` ブロックが存在すると、いくつかの方法で最適化に影響します。 まず、コンパイラは `__asm` ブロック自体を最適化しようとしません。 アセンブリ言語で記述する内容は、厳密に取得したものです。 2つ目の方法として、`__asm` ブロックが存在すると、レジスタ変数のストレージに影響します。 コンパイラは、レジスタの内容が `__asm` ブロックによって変更された場合に、`__asm` ブロック全体での変数の登録を回避します。 最後に、関数内でアセンブリ言語を含めることによって、関数全体の最適化が影響を受けます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>
