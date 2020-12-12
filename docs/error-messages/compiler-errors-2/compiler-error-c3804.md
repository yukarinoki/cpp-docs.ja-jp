---
description: 詳細については、「コンパイラエラー C3804」を参照してください。
title: コンパイラ エラー C3804
ms.date: 11/04/2016
f1_keywords:
- C3804
helpviewer_keywords:
- C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
ms.openlocfilehash: b033acefd9a583b1659755f63fdbd3781fc95ccd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291507"
---
# <a name="compiler-error-c3804"></a>コンパイラ エラー C3804

' property_accessor ': プロパティのアクセサーメソッドは、すべてスタティックであるか、またはすべてスタティックでない必要があります

自明でないプロパティを定義する場合、アクセサー関数は静的またはインスタンスのどちらでもかまいませんが、両方を指定することはできません。

詳細については、「 [property](../../extensions/property-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C3804 が生成されます。

```cpp
// C3804.cpp
// compile with: /c /clr
ref struct A {

   property int i {
      static int get() {}
      void set(int i) {}
   }   // C3804 error

   // OK
   property int j {
      int get() { return 0; }
      void set(int i) {}
   }

   property int k {
      static int get() { return 0; }
      static void set(int i) {}
   }
};
```
