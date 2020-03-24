---
title: コンパイラの警告 (レベル 1) C4964
ms.date: 11/04/2016
f1_keywords:
- C4964
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
ms.openlocfilehash: 7852340bc056e126238a2d9c7493887ef3caf93e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174493"
---
# <a name="compiler-warning-level-1-c4964"></a>コンパイラの警告 (レベル 1) C4964

最適化オプションが指定されていません。プロファイル情報は収集されません

[/Gl](../../build/reference/gl-whole-program-optimization.md)と[/ltcg](../../build/reference/ltcg-link-time-code-generation.md)が指定されましたが、最適化が要求されていないため、.pgc ファイルは生成されないため、ガイド付き最適化のプロファイルは使用できません。

アプリケーションの実行時に .pgc ファイルを生成する場合は、 [/o](../../build/reference/o-options-optimize-code.md)コンパイラオプションのいずれかを指定します。

次の例では、C4964 が生成されます。

```cpp
// C4964.cpp
// compile with: /W1 /GL /link /ltcg:pgi
// C4964 expected
// Add /O2, for example, to the command line to resolve this warning.
int main() {
   int i;
}
```
