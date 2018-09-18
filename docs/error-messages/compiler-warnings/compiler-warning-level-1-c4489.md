---
title: コンパイラの警告 (レベル 1) C4489 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4489
dev_langs:
- C++
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc019c618a5e4b8a453652573f6f407279792d56
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023255"
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