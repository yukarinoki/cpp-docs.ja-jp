---
description: 詳細については、「コンパイラエラー C2466」を参照してください。
title: コンパイラ エラー C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: 68ff57de2c0287f24ac84466ac8053bf73f88a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333832"
---
# <a name="compiler-error-c2466"></a>コンパイラ エラー C2466

定数サイズ0の配列を割り当てることはできません。

配列が割り当てられているか、サイズが0で宣言されています。 配列のサイズの定数式には、0より大きい整数を指定してください。 添字がゼロの配列宣言は、クラス、構造体、または共用体のメンバーに対してのみ有効で、Microsoft の拡張機能 ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) でのみ有効です。

次の例では、C2466 が生成されます。

```cpp
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```
