---
description: '詳細情報: コンパイラの警告 (レベル 4) C4130'
title: コンパイラの警告 (レベル 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: e7096f471405b0b22bcb0a825dd9ccd0de4e3510
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261815"
---
# <a name="compiler-warning-level-4-c4130"></a>コンパイラの警告 (レベル 4) C4130

'operator': 文字列定数のアドレスで論理演算が行われました

文字列リテラルのアドレスで演算子が使用されると、不要なコードが生成されます。

次の例では C4130 が生成されます。

```cpp
// C4130.cpp
// compile with: /W4
int main()
{
   char *pc;
   pc = "Hello";
   if (pc == "Hello") // C4130
   {
   }
}
```

ステートメントは、 **`if`** ポインターに格納されている値と `pc` 文字列 "Hello" のアドレスを比較します。このアドレスは、コード内で文字列が出現するたびに個別に割り当てられます。 ステートメントでは、が **`if`** 指す文字列と、 `pc` 文字列 "Hello" は比較されません。

文字列を比較するには、 `strcmp` 関数を使用します。
