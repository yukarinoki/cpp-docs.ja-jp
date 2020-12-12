---
description: 詳細については、「コンパイラエラー C2959」を参照してください。
title: コンパイラ エラー C2959
ms.date: 11/04/2016
f1_keywords:
- C2959
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
ms.openlocfilehash: aa5da1db36ce8544e95ad509402b066e664faf18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210427"
---
# <a name="compiler-error-c2959"></a>コンパイラ エラー C2959

ジェネリッククラスまたはジェネリック関数は、テンプレートのメンバーではない可能性があります

詳細については、「 [Windows ランタイムとマネージテンプレート](../../extensions/windows-runtime-and-managed-templates-cpp-component-extensions.md) と [ジェネリック](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2959 が生成されます。

```cpp
// C2959.cpp
// compile with: /clr /c
template <class T> ref struct S {
   generic <class U> ref struct GR1;   // C2959
};
```
