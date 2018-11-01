---
title: コンパイラの警告 (レベル 1) C4964
ms.date: 11/04/2016
f1_keywords:
- C4964
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
ms.openlocfilehash: 556c6e0963fc41d76cd123373cc4cd85edc66962
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492053"
---
# <a name="compiler-warning-level-1-c4964"></a>コンパイラの警告 (レベル 1) C4964

最適化オプションが指定されていません。プロファイル情報は収集されません。

[/GL](../../build/reference/gl-whole-program-optimization.md)と[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)最適化の無効化が、指定された要求されたため、.pgc ファイルを生成しないと、そのため、プロファイル ガイド付き最適化することはできません。

.Pgc ファイルをアプリケーションを実行するときに生成する場合は、いずれかを指定、 [/O](../../build/reference/o-options-optimize-code.md)コンパイラ オプション。

次の例では、C4964 が生成されます。

```
// C4964.cpp
// compile with: /W1 /GL /link /ltcg:pgi
// C4964 expected
// Add /O2, for example, to the command line to resolve this warning.
int main() {
   int i;
}
```