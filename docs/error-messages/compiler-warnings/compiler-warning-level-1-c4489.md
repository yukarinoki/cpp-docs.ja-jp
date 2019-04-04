---
title: コンパイラの警告 (レベル 1) C4489
ms.date: 11/04/2016
f1_keywords:
- C4489
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
ms.openlocfilehash: dd150621ad3474444861982c095ae8a6addb52fa
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768238"
---
# <a name="compiler-warning-level-1-c4489"></a>コンパイラの警告 (レベル 1) C4489

'specifier': インターフェイス メソッド 'method'; で許可されていませんオーバーライド指定子は、ref クラスおよび値クラスのメソッドでのみ使用できます。

指定子のキーワードが、インターフェイス メソッドで正しく使用されていません。

詳細については、[オーバーライド指定子を](../../extensions/override-specifiers-cpp-component-extensions.md)を参照してください。

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