---
title: コンパイラの警告 (レベル 1) C4490
ms.date: 11/04/2016
f1_keywords:
- C4490
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
ms.openlocfilehash: bf51994c210bd751e0d29bec169dfc4366784486
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779184"
---
# <a name="compiler-warning-level-1-c4490"></a>コンパイラの警告 (レベル 1) C4490

'override': オーバーライド指定子の不適切な使用'function' は、基本 ref クラスのメソッドと一致しません

オーバーライド指定子が正しく使用されていません。 たとえば、インターフェイスの関数をオーバーライドしていない、実装します。

詳細については、次を参照してください。[オーバーライド指定子を](../../extensions/override-specifiers-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C4490 が生成されます。

```
// C4490.cpp
// compile with: /clr /c /W1

interface struct IFace {
   void Test();
};

ref struct Class1 : public IFace {
   virtual void Test() override {}   // C4490
   // try the following line instead
   // virtual void Test() {}
};
```