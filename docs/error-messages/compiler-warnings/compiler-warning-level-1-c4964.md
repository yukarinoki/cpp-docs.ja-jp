---
title: コンパイラの警告 (レベル 1) C4964 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4964
dev_langs:
- C++
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f1644e4603bae36ec9d407294dea78a27e60539
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086669"
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