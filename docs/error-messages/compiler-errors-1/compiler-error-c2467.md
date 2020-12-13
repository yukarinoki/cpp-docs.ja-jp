---
description: 詳細については、「コンパイラエラー C2467」を参照してください。
title: コンパイラエラー C2467
ms.date: 11/04/2016
f1_keywords:
- C2467
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
ms.openlocfilehash: fd5227e451208d848d631550da33999a4ebae8dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333818"
---
# <a name="compiler-error-c2467"></a>コンパイラエラー C2467

匿名の ' ユーザー定義型 ' の宣言が無効です。

入れ子になったユーザー定義型が宣言されました。 これは、ANSI 互換オプション ([/za](../../build/reference/za-ze-disable-language-extensions.md)) が有効になっている C ソースコードをコンパイルするときにエラーになります。

次の例では、C2467 が生成されます。

```c
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```
