---
title: コンパイラ エラー C2117 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2117
dev_langs:
- C++
helpviewer_keywords:
- C2117
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5579a6f05e1de768aebd2e68b64d0b861688607
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030991"
---
# <a name="compiler-error-c2117"></a>コンパイラ エラー C2117

'identifier': 配列の境界オーバーフロー

配列は、初期化子が多すぎますがあります。

- 配列の要素と初期化子は、サイズと数は一致しません。

- 文字列内の null 終端文字用の領域がありません。

次の例では、C2117 が生成されます。

```
// C2117.cpp
int main() {
   char abc[4] = "abcd";   // C2117
   char def[4] = "abd";   // OK
}
```