---
title: コンパイラ エラー C3648
ms.date: 11/04/2016
f1_keywords:
- C3648
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
ms.openlocfilehash: f3ef949b2651631f30a9c614a0d21b2668b7239f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653766"
---
# <a name="compiler-error-c3648"></a>コンパイラ エラー C3648

この明示的なオーバーライド構文は/clr:oldSyntax が必要です。

コンパイル時に最新の管理対象の構文については、コンパイラによって明示的な検出されたがサポートされなくなった以前のバージョンの構文をオーバーライドします。

詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3648 が生成されます。

```
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