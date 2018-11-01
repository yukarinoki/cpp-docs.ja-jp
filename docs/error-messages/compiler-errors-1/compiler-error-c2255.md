---
title: コンパイラ エラー C2255
ms.date: 11/04/2016
f1_keywords:
- C2255
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
ms.openlocfilehash: ae2c61257af3e1aca2d26ce5f8801999f7bb77c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429394"
---
# <a name="compiler-error-c2255"></a>コンパイラ エラー C2255

'element' : クラス定義外では使用できません

たとえば、非メンバー関数が `friend`として宣言されているとします。

次の例では、C2255 が生成されます。

```
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