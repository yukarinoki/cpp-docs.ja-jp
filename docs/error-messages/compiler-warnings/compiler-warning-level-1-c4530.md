---
title: コンパイラの警告 (レベル 1) C4530
ms.date: 11/04/2016
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: 69ca60e2cba338bf1bd1ac3470e583739e72a68e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186453"
---
# <a name="compiler-warning-level-1-c4530"></a>コンパイラの警告 (レベル 1) C4530

C++例外ハンドラーが使用されていますが、アンワインドセマンティクスが有効になっていません。 /EHsc を指定する

C++例外処理が使用されましたが、 [/ehsc](../../build/reference/eh-exception-handling-model.md)は選択されていませんでした。

/EHsc オプションが有効になっていない場合、フレーム内の自動ストレージを持つオブジェクトは、スローを行う関数とスローをキャッチする関数の間に破棄されません。 ただし、 **try**ブロックまたは**catch**ブロックで作成された自動ストレージを持つオブジェクトは破棄されます。

次の例では、C4530 が生成されます。

```cpp
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

この警告を解決するには、/EHsc を使用してサンプルをコンパイルします。
