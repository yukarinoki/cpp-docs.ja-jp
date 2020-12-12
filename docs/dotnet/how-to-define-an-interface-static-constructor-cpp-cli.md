---
description: '詳細については、「方法: インターフェイス静的コンストラクターを定義する (C++/CLI)」を参照してください。'
title: '方法: interface 静的コンストラクターを定義する (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [C++]
- static constructors, interface
- interface static constructor
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
ms.openlocfilehash: 2cc6eca19a26f9857c029fc01c500ed9f4691e8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245903"
---
# <a name="how-to-define-an-interface-static-constructor-ccli"></a>方法: interface 静的コンストラクターを定義する (C++/CLI)

インターフェイスは静的コンストラクターを持つことができ、これを使用して静的データメンバーを初期化できます。  静的コンストラクターは最大で1回呼び出され、静的インターフェイスメンバーに初めてアクセスするときに呼び出されます。

## <a name="example"></a>例

```cpp
// mcppv2_interface_class2.cpp
// compile with: /clr
using namespace System;

interface struct MyInterface {
   static int i;
   static void Test() {
      Console::WriteLine(i);
   }

   static MyInterface() {
      Console::WriteLine("in MyInterface static constructor");
      i = 99;
   }
};

ref class MyClass : public MyInterface {};

int main() {
   MyInterface::Test();
   MyClass::MyInterface::Test();

   MyInterface ^ mi = gcnew MyClass;
   mi->Test();
}
```

```Output
in MyInterface static constructor
99
99
99
```

## <a name="see-also"></a>関連項目

[interface クラス](../extensions/interface-class-cpp-component-extensions.md)
