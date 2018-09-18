---
title: コンパイラ エラー C3650 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3650
dev_langs:
- C++
helpviewer_keywords:
- C3650
ms.assetid: ca4d8de4-b027-4d13-9b9f-03ca62905c33
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee7477acc26621a13a1a1d3b4f2d0d0f563c665
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016547"
---
# <a name="compiler-error-c3650"></a>コンパイラ エラー C3650

'interface_method': 明示的なオーバーライドとして使用することはできません、基底クラスの仮想メンバー関数でなければなりません

仮想でないメンバーに明示的なオーバーライドの実行が試行されました。

詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)します。

次の例では、C3650 が生成されます。

```
// C3650.cpp
// compile with: /clr
public interface struct I {
   void a();
};

public ref class S {
public:
   static int f() { return 0; }
   static int g() { return 0; }
};

public ref struct T1 : public S, I {
   virtual int f() new sealed = S::f;   // C3650
   virtual int g() { return 0; }   // OK does not override S::g
   virtual void a() new sealed = I::a {}   // OK
};
```