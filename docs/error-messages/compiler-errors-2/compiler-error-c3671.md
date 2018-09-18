---
title: コンパイラ エラー C3671 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3671
dev_langs:
- C++
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 455b9e2a6accbc98ee8bce49a35a672d9cd9c20d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017074"
---
# <a name="compiler-error-c3671"></a>コンパイラ エラー C3671

'function_1': 関数は 'function_2' をオーバーライドしません

明示的なオーバーライド構文を使用する場合、コンパイラは、関数がオーバーライドされていない場合、エラーを生成します。  参照してください[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)詳細についてはします。

## <a name="example"></a>例

次の例では、C3671 が生成されます。

```
// C3671.cpp
// compile with: /clr /c
ref struct S {
   virtual void f();
};

ref struct S1 : S {
   virtual void f(int) new sealed = S::f;   // C3671
   virtual void f() new sealed = S::f;
};
```