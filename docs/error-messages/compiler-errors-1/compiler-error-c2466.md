---
title: コンパイラ エラー C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: 516f9b024947e0100a753e4e010a5b51b1fb24a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230530"
---
# <a name="compiler-error-c2466"></a>コンパイラ エラー C2466

サイズが 0 の配列を割り当てることができません。

配列が割り当てられているか、サイズがゼロで宣言されています。 配列のサイズの定数式は、0 より大きい整数である必要があります。 0 個の下付き文字の配列宣言はクラス、構造体または共用体のメンバーに対してのみ、Microsoft の拡張機能でのみ ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。

次の例では、C2466 が生成されます。

```
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```