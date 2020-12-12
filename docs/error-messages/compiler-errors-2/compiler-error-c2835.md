---
description: 詳細については、「コンパイラエラー C2835」を参照してください。
title: コンパイラ エラー C2835
ms.date: 11/04/2016
f1_keywords:
- C2835
helpviewer_keywords:
- C2835
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
ms.openlocfilehash: f5fa04e6c34ce4bcad99022bd1a5e0f20bba41be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194424"
---
# <a name="compiler-error-c2835"></a>コンパイラ エラー C2835

ユーザー定義の変換 ' type ' に仮引数を指定することはできません

ユーザー定義型の変換は、仮パラメーターを受け取ることはできません。

次の例では、C2835 が生成されます。

```cpp
// C2835.cpp
class A {
public:
   char v_char;

   A() {
      v_char = 'A';
   };
   operator char(char a) {   // C2835
   // try the following line instead
   // operator char() {
      return v_char + 1;
   };
};

int main() {
   A a;
}
```
