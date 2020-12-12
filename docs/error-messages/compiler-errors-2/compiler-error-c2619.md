---
description: 詳細については、「コンパイラエラー C2619」を参照してください。
title: コンパイラエラー C2619
ms.date: 11/04/2016
f1_keywords:
- C2619
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
ms.openlocfilehash: 2ca9a8379901703299e89e71671ec0270c1ff1e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123548"
---
# <a name="compiler-error-c2619"></a>コンパイラエラー C2619

'identifier' : 静的データ メンバー宣言は匿名の構造体または共用体では使用できません

匿名構造体または共用体のメンバーがとして宣言されて **`static`** います。

次の例では C2619 を生成し、static キーワードの削除による修正方法を示しています。

```cpp
// C2619.cpp
int main() {
   union { static int j; };  // C2619
   union { int j; };  // OK
}
```
