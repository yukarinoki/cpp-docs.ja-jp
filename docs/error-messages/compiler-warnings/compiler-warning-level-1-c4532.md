---
title: コンパイラの警告 (レベル 1) C4532
ms.date: 11/04/2016
f1_keywords:
- C4532
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
ms.openlocfilehash: bcadf31eda079ebb8ea7a496efe4c945e16b1ab7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160758"
---
# <a name="compiler-warning-level-1-c4532"></a>コンパイラの警告 (レベル 1) C4532

'continue': _ _finally/finally にブロックからのジャンプでが終了処理中に、動作が定義されていません

コンパイラには、次のキーワードのいずれかが発生しました。

- [continue](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

ジャンプ先の原因を[_ _finally](../../cpp/try-finally-statement.md)または[最後に](../../dotnet/finally.md)異常終了時にブロックします。

終了ハンドラーの実行中に、スタックが展開されるときに例外が発生する場合、(、 `__finally` finally ブロックまたは)、コードは、の外部にジャンプし、`__finally`する前にブロック、`__finally`ブロックの終了動作が定義されていません。 例外は正しく処理されないように、コントロールは、アンワインド コードを返されません可能性があります。

場合の外部にジャンプする必要があります、 **_ _finally**ブロック、異常終了をまずチェックします。

次の例には、C4532; が生成されます。警告を解決するのには、ジャンプ ステートメントをコメントだけです。

```
// C4532.cpp
// compile with: /W1
// C4532 expected
int main() {
   int i;
   for (i = 0; i < 10; i++) {
      __try {
      } __finally {
         // Delete the following line to resolve.
         continue;
      }

      __try {
      } __finally {
         // Delete the following line to resolve.
         break;
      }
   }
}
```