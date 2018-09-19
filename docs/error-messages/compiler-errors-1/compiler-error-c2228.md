---
title: コンパイラ エラー C2228 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2228
dev_langs:
- C++
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70ea4fcdf2647264550b32ce941a3551664a6b94
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082880"
---
# <a name="compiler-error-c2228"></a>コンパイラ エラー C2228

'.identifier' の左側はクラス、構造体、共用体でなければなりません

ピリオド (.) の左側のオペランドがクラス、構造体または共用体。

次の例では C2228 が生成されます。

```
// C2228.cpp
int i;
struct S {
public:
    int member;
} s, *ps = &s;

int main() {
   i.member = 0;   // C2228 i is not a class type
   ps.member = 0;  // C2228 ps is a pointer to a structure

   s.member = 0;   // s is a structure type
   ps->member = 0; // ps points to a structure S
}
```

マネージド拡張を使用する際に、間違った構文を使用した場合も、このエラーが表示されます。 他の Visual Studio の言語ではドット演算子を使用してマネージド クラスのメンバーにアクセスできますが、C++ でのオブジェクトへのポインターは、-&gt; 演算子を使用してメンバーにアクセスする必要があることを意味します。

誤: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`

正: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`