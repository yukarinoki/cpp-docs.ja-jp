---
title: コンパイラ エラー C2561
ms.date: 11/04/2016
f1_keywords:
- C2561
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
ms.openlocfilehash: 8350c5baf129b88c178be280d2da7fe856c6cf57
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517612"
---
# <a name="compiler-error-c2561"></a>コンパイラ エラー C2561

'identifier': 関数は、値を返す必要があります

値を返すとして宣言された関数が関数定義が含まれない、`return`ステートメント。

このエラーは、間違った関数プロトタイプで発生することができます。

1. 関数が値を返さない場合は、戻り値の型と関数を宣言[void](../../cpp/void-cpp.md)します。

1. 関数のすべての分岐が、プロトタイプで宣言された型の値を返すことを確認します。

1. C++ の関数の戻り値を格納するインライン アセンブリ ルーチンを含む、`AX`レジスタに return ステートメントが必要があります。 値をコピーします`AX`一時変数に、関数からその変数を返すとします。

次の例では、C2561 が生成されます。

```
// C2561.cpp
int Test(int x) {
   if (x) {
      return;   // C2561
      // try the following line instead
      // return 1;
   }
   return 0;
}

int main() {
   Test(1);
}
```