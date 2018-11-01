---
title: コンパイラ エラー C3753
ms.date: 11/04/2016
f1_keywords:
- C3753
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
ms.openlocfilehash: b6b1e8c3241a778b29045e734fffebb663554e62
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498372"
---
# <a name="compiler-error-c3753"></a>コンパイラ エラー C3753

汎用プロパティは許可されていません

ジェネリック パラメーター リストは、マネージ クラス、構造体、または関数でのみ表示できます。

詳細については、次を参照してください。[ジェネリック](../../windows/generics-cpp-component-extensions.md)と[プロパティ](../../windows/property-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3753 が生成されます。

```
// C3753.cpp
// compile with: /clr /c
ref struct A {
   generic <typename T>
   property int i;   // C3753 error
};
```