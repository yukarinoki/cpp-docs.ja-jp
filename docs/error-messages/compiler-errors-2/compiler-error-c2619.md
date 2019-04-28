---
title: コンパイラ エラー C2619
ms.date: 11/04/2016
f1_keywords:
- C2619
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
ms.openlocfilehash: f82b315a3e7ae4bb1f6d281e1d80ddc2c7fb0dea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208429"
---
# <a name="compiler-error-c2619"></a>コンパイラ エラー C2619

'identifier' : 静的データ メンバー宣言は匿名の構造体または共用体では使用できません

匿名の構造体または共用体のメンバーは、`static` として宣言されます。

次の例では C2619 を生成し、static キーワードの削除による修正方法を示しています。

```
// C2619.cpp
int main() {
   union { static int j; };  // C2619
   union { int j; };  // OK
}
```