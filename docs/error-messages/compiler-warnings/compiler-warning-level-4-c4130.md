---
title: コンパイラの警告 (レベル 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: b55594608eccc5d1e5e764bffb73ecb3787af1e4
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541596"
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

**if** ステートメントは、ポインター `pc` に格納されている値と、コード内に出現するたびに個別に割り当てられる文字列 "Hello" のアドレスを比較しています。 **if** ステートメントは、 `pc` が指す文字列と、文字列 "Hello" については比較しません。

文字列を比較するには、 `strcmp` 関数を使用します。