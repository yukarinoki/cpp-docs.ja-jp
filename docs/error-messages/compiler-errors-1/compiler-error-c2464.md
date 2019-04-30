---
title: コンパイラ エラー C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: a00ac997f73175eeab08a0132128e48e8fc58feb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338897"
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