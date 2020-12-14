---
description: 詳細については、「コンパイラエラー C3648」を参照してください。
title: コンパイラ エラー C3648
ms.date: 11/04/2016
f1_keywords:
- C3648
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
ms.openlocfilehash: 532c65896ae5c3707c86735c661a095698417288
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203745"
---
# <a name="compiler-error-c3648"></a>コンパイラ エラー C3648

この明示的なオーバーライド構文には/clr: oldSyntax が必要です

最新のマネージ構文に対してコンパイルする場合、サポートされなくなった以前のバージョンの明示的なオーバーライド構文がコンパイラによって検出されました。

詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3648 が生成されます。

```cpp
// C3648.cpp
// compile with: /clr
public interface struct I {
   void f();
};

public ref struct R : I {
   virtual void I::f() {}   // C3648
   // try the following line instead
   // virtual void f() = I::f{}
};
```
