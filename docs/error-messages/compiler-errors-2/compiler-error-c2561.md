---
title: コンパイラ エラー C2561
ms.date: 11/04/2016
f1_keywords:
- C2561
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
ms.openlocfilehash: 9c42a2da662a286f3e6887f6a1dba381687136bf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206966"
---
# <a name="compiler-error-c2561"></a>コンパイラ エラー C2561

' identifier ': 関数は値を返す必要があります

関数は値を返すように宣言されていますが、関数定義にはステートメントが含まれていません **`return`** 。

このエラーは、関数プロトタイプが正しくないことが原因で発生する可能性があります。

1. 関数が値を返さない場合は、戻り値の型が[void](../../cpp/void-cpp.md)である関数を宣言します。

1. 関数のすべての可能な分岐が、プロトタイプで宣言された型の値を返すことを確認します。

1. レジスタに戻り値を格納するインラインアセンブリルーチンを含む C++ 関数 `AX` には、return ステートメントが必要になる場合があります。 の値を `AX` 一時変数にコピーし、関数からその変数を返します。

次の例では、C2561 が生成されます。

```cpp
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
