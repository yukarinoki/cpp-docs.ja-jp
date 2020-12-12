---
description: 詳細については、「コンパイラエラー C3382」を参照してください。
title: コンパイラ エラー C3382
ms.date: 11/04/2016
f1_keywords:
- C3382
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
ms.openlocfilehash: 582a807ac43d6110fb0f19aef5806e4118516db2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285657"
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

```cpp
// C3382.cpp
// compile with: /clr:safe
int main() {
   sizeof( char );   // C3382
}
```
