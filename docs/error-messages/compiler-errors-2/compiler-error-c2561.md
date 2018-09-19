---
title: コンパイラ エラー C2561 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2561
dev_langs:
- C++
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8611af23ab884a853fc751ae82c636753993495b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070705"
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