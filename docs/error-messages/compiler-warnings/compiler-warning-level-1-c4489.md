---
description: '詳細情報: コンパイラの警告 (レベル 1) C4489'
title: コンパイラの警告 (レベル 1) C4489
ms.date: 11/04/2016
f1_keywords:
- C4489
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
ms.openlocfilehash: d2865f7f2eba4db72fa4cbf622609b319197f942
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212416"
---
# <a name="compiler-warning-level-1-c4489"></a>コンパイラの警告 (レベル 1) C4489

' 指定子 ': インターフェイスメソッド ' method ' では許可されていません。オーバーライド指定子は、ref クラスおよび値クラスメソッドでのみ使用できます

指定子キーワードがインターフェイスメソッドで正しく使用されませんでした。

詳細については、「 [オーバーライド指定子](../../extensions/override-specifiers-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4489 が生成されます。

```cpp
// C4489.cpp
// compile with: /clr /c /W1
public interface class I {
   void f() new;   // C4489
   virtual void b() override;   // C4489

   void g();   // OK
};
```
