---
title: コンパイラ エラー C2464 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff74085364d6638772ab2376aace93fea741056b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103145"
---
# <a name="compiler-error-c2464"></a>コンパイラ エラー C2464

'identifier': 'new' の参照の割り当てに使用できません

参照識別子で割り当てられた、`new`演算子。 参照がそのため、メモリ オブジェクトされてない`new`それらへのポインターを返すことはできません。 標準の変数宣言の構文を使用して、参照を宣言します。

次の例では、C2464 が生成されます。

```
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```