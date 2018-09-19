---
title: コンパイラ エラー C2466 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d43ee9d09fba77db022177a06c6ebe95c65ff79
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037841"
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