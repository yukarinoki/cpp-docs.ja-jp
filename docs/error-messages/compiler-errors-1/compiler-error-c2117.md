---
title: コンパイラ エラー C2117
ms.date: 11/04/2016
f1_keywords:
- C2117
helpviewer_keywords:
- C2117
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
ms.openlocfilehash: 2f6a1e26972f093e50c5e655935f750195ab7d3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338572"
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