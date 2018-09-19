---
title: コンパイラ エラー C3382 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3382
dev_langs:
- C++
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6da27531b95950a12cb9aa95e8e89da94c556d2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035962"
---
# <a name="compiler-error-c3382"></a>コンパイラ エラー C3382

'sizeof' は /clr:safe でサポートされていません

**/clr:safe** コンパイルの出力ファイルは検証可能なタイプ セーフのファイルです。sizeof 演算子の戻り値は size_t であり、そのサイズはオペレーティング システムによって異なるため、sizeof はサポートされていません。

詳細については、次のトピックを参照してください。

- [sizeof 演算子](../../cpp/sizeof-operator.md)

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Visual C++ の 64 ビットへの移行に関する一般的な問題](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>例

次の例では C3382 が生成されます。

```
// C3382.cpp
// compile with: /clr:safe
int main() {
   sizeof( char );   // C3382
}
```