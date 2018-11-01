---
title: コンパイラ エラー C2959
ms.date: 11/04/2016
f1_keywords:
- C2959
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
ms.openlocfilehash: c45466fdf8d0c4bec67779943a5868299f05cf79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535734"
---
# <a name="compiler-error-c2959"></a>コンパイラ エラー C2959

テンプレートのメンバーはジェネリック クラスまたは関数ではない可能性があります。

詳細については、次を参照してください。 [Windows ランタイムおよびマネージ テンプレート](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)と[ジェネリック](../../windows/generics-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C2959 が生成されます。

```
// C2959.cpp
// compile with: /clr /c
template <class T> ref struct S {
   generic <class U> ref struct GR1;   // C2959
};
```