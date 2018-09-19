---
title: コンパイラの警告 (レベル 1) C4530 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4530
dev_langs:
- C++
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbfbc67377dd48eeb692bdd4cac1f113fbdf7f6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110459"
---
# <a name="compiler-warning-level-1-c4530"></a>コンパイラの警告 (レベル 1) C4530

C++ 例外処理を使って、アンワインド セマンティクスは有効になりません。 /EHsc を指定します。

C++ 例外処理が使用されましたが、 [/EHsc](../../build/reference/eh-exception-handling-model.md)が選択されていません。

/EHsc オプションが有効になっていない場合、関数のスローを行うと、関数のスローをキャッチの間、フレームに自動ストレージを持つオブジェクトは破棄されません。 ただし、自動ストレージを持つオブジェクトで作成、**お試しください**または**キャッチ**ブロックは破棄されます。

次の例では、C4530 が生成されます。

```
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

/EHsc、警告を解決するのには、サンプルをコンパイルします。