---
title: コンパイラの警告 (レベル 1) C4489
ms.date: 11/04/2016
f1_keywords:
- C4489
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
ms.openlocfilehash: 4da96fd13fe9ba03c19808d32d3cdd9c73ec2b18
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584731"
---
# <a name="compiler-warning-level-1-c4489"></a>コンパイラの警告 (レベル 1) C4489

'specifier': インターフェイス メソッド 'method'; で許可されていませんオーバーライド指定子は、ref クラスおよび値クラスのメソッドでのみ使用できます。

指定子のキーワードが、インターフェイス メソッドで正しく使用されていません。

詳細については、次を参照してください。[オーバーライド指定子を](../../windows/override-specifiers-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C4489 が生成されます。

```
// C4489.cpp
// compile with: /clr /c /W1
public interface class I {
   void f() new;   // C4489
   virtual void b() override;   // C4489

   void g();   // OK
};
```