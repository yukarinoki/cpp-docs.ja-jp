---
title: コンパイラ エラー C3382
ms.date: 11/04/2016
f1_keywords:
- C3382
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
ms.openlocfilehash: c262ea963ae739fbb76211aae2622e98d5a9b6f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328784"
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