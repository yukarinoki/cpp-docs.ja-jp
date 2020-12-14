---
description: 詳細については、「コンパイラエラー C3374」を参照してください。
title: コンパイラ エラー C3374
ms.date: 11/04/2016
f1_keywords:
- C3374
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
ms.openlocfilehash: b3ec1a18433c41f8c1e1a4b704b6ab03dae7572d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245175"
---
# <a name="compiler-error-c3374"></a>コンパイラ エラー C3374

delegate インスタンスを作成する場合以外に、'関数' のアドレスを指定できません

delegate インスタンスを作成する以外のコンテキストで、関数のアドレスが取得されました。

次の例では警告 C3374 が生成されます。

```cpp
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
