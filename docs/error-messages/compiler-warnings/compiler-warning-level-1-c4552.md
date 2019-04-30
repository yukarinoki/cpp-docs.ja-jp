---
title: コンパイラの警告 (レベル 1) C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: 1fb2dc7fd4bc685e457898b47c513c21009146ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410357"
---
# <a name="compiler-warning-level-1-c4552"></a>コンパイラの警告 (レベル 1) C4552

'operator': 演算子も何も起こりません。予想される演算子の副作用

式ステートメントは、式の先頭として副作用を持たない演算子を持つ場合、は、おそらく間違いです。

この警告を無効にするには、かっこで囲まれた式を配置します。

次の例では、C4552 が生成されます。

```
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```