---
title: コンパイラ エラー C3764 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3764
dev_langs:
- C++
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b57b9005eacc6e4a59adecc38b40027fffb5bcf1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097004"
---
# <a name="compiler-error-c3764"></a>コンパイラ エラー C3764

'override_function': 基底クラス メソッド 'base_class_function' をオーバーライドすることはできません

正しくない形式のオーバーライドが検出されました。 たとえば、基底クラスの関数が`virtual`します。 詳細については、次を参照してください。[オーバーライド](../../windows/override-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3764 が生成されます。

```
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>例

C3764 基底クラスのメソッドは、両方を明示的にはときも発生し、という名前をオーバーライドします。 次の例では、C3764 が生成されます。

```
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```