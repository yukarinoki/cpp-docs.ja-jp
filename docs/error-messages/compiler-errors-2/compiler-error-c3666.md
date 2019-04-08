---
title: コンパイラ エラー C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: edca117da585fee731041d696e05af1baf6d3e5c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778677"
---
# <a name="compiler-error-c3666"></a>コンパイラ エラー C3666

'constructor': オーバーライド指定子 'keyword' コンス トラクターで許可されていません

オーバーライド指定子は、コンス トラクターで使用されていたし、は許可されていません。 詳細については、次を参照してください。[オーバーライド指定子を](../../extensions/override-specifiers-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3666 が生成されます。

```
// C3666.cpp
// compile with: /clr /c
ref struct R {
   R() new {}   // C3666
   R(int i) {}   // OK
};
```