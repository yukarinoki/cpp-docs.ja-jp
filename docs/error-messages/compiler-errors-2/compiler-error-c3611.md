---
title: コンパイラ エラー C3611
ms.date: 11/04/2016
f1_keywords:
- C3611
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
ms.openlocfilehash: 2d4c5cb02b1b8c5472502380fe7c74ff4a91954a
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345440"
---
# <a name="compiler-error-c3611"></a>コンパイラ エラー C3611

'function': シールド関数は、純粋指定子を含めることはできません

封印された関数の宣言が正しくありません。  詳細については、次を参照してください。[シール](../../extensions/sealed-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3611 が生成されます。

```
// C3611.cpp
// compile with: /clr /c

ref struct V {
   virtual void Test() sealed = 0;   // C3611
   virtual void Test2() sealed;   // OK
   virtual void Test3() = 0;   // OK
};
```