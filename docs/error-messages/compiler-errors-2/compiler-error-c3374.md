---
title: コンパイラ エラー C3374
ms.date: 11/04/2016
f1_keywords:
- C3374
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
ms.openlocfilehash: c9ee9130d77e844ab435ecc34dcf53e12449abba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474933"
---
# <a name="compiler-error-c3374"></a>コンパイラ エラー C3374

delegate インスタンスを作成する場合以外に、'関数' のアドレスを指定できません

delegate インスタンスを作成する以外のコンテキストで、関数のアドレスが取得されました。

次の例では警告 C3374 が生成されます。

```
// C3374.cpp
// compile with: /clr
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      System::Console::WriteLine("in func1 {0}", i);
   }
};

int main() {
   &A::func1;   // C3374

   // OK
   A ^ a = gcnew A;
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);
}
```

## <a name="see-also"></a>関連項目

[方法: デリゲートを定義および使用する (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)