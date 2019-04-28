---
title: コンパイラ エラー C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: c665c4ed82fefaf0ee724defb8c205f86fc06dd0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228892"
---
# <a name="compiler-error-c2562"></a>コンパイラ エラー C2562

'identifier': 'void' 関数の値を返す

関数として`void`が値を返します。

このエラーは、間違った関数プロトタイプで発生することができます。

このエラーは、関数の宣言で戻り値の型を指定する場合に解決される可能性があります。

次の例では、C2562 が生成されます。

```
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```