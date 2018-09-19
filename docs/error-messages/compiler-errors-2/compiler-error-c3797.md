---
title: コンパイラ エラー C3797 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3797
dev_langs:
- C++
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ac1ded1c95f7e8bea9598e468010c75d8bd917a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033421"
---
# <a name="compiler-error-c3797"></a>コンパイラ エラー C3797

'override': イベントの宣言 (トライブを配置イベントの追加/削除/raise メソッド代わりに) オーバーライド指定子を含めることはできません

もう 1 つの単純なイベントでは、単純なイベント (明示的に定義されたアクセサー メソッドなしイベント) をオーバーライドすることはできません。 イベントをオーバーライドするには、アクセサー関数でその動作を定義する必要があります。

詳細については、次を参照してください。[イベント](../../windows/event-cpp-component-extensions.md)します。

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