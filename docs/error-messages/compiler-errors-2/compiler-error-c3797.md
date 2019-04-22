---
title: コンパイラ エラー C3797
ms.date: 11/04/2016
f1_keywords:
- C3797
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
ms.openlocfilehash: 76206cdffce3f551ff472cbd83df486eb41ae80b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776173"
---
# <a name="compiler-error-c3797"></a>コンパイラ エラー C3797

'override': イベントの宣言 (トライブを配置イベントの追加/削除/raise メソッド代わりに) オーバーライド指定子を含めることはできません

もう 1 つの単純なイベントでは、単純なイベント (明示的に定義されたアクセサー メソッドなしイベント) をオーバーライドすることはできません。 イベントをオーバーライドするには、アクセサー関数でその動作を定義する必要があります。

詳細については、次を参照してください。[イベント](../../extensions/event-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3797 が生成されます。

```
// C3797.cpp
// compile with: /clr /c
delegate void MyDel();

ref class Class1 {
public:
   virtual event MyDel ^ E;
};

ref class Class2 : public Class1 {
public:
   virtual event MyDel ^ E override;   // C3797
};

// OK
ref class Class3 : public Class1 {
public:
   virtual event MyDel ^ E {
      void add(MyDel ^ d) override {}
      void remove(MyDel ^ d) override {}
   }
};
```