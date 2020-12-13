---
description: 詳細については、「コンパイラエラー C2255」を参照してください。
title: コンパイラ エラー C2255
ms.date: 11/04/2016
f1_keywords:
- C2255
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
ms.openlocfilehash: 9c7898ede43c9c25175854faeab5ee279a9c5635
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333861"
---
# <a name="compiler-error-c2255"></a>コンパイラ エラー C2255

'element' : クラス定義外では使用できません

たとえば、非メンバー関数がとして宣言されていると **`friend`** します。

次の例では、C2255 が生成されます。

```cpp
// C2255.cpp
// compile with: /c
class A {
private:
   void func1();
   friend void func2();
};

friend void func1() {}   // C2255
void func2(){}
```
