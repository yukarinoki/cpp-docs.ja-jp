---
title: コンパイラ エラー C2231
ms.date: 11/04/2016
f1_keywords:
- C2231
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
ms.openlocfilehash: 0d6519bd12cdb5ee5a86fa4a6915b51b0dc59fc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383309"
---
# <a name="compiler-error-c2231"></a>コンパイラ エラー C2231

'.':'->' を使用してポイントのオペランドを左 'クラス キー' から、

メンバー選択演算子 (.) の左側のオペランドは、クラス、構造体または共用体ではなくポインターです。

次の例では C2231 が生成されます。

```
// C2231.c
struct S {
   int member;
} s, *ps = &s;
int main() {
   ps.member = 0;   // C2231

   // OK
   ps->member = 0;   // crash
   s.member = 0;
}
```