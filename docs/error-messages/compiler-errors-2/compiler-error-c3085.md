---
title: コンパイラ エラー C3085
ms.date: 11/04/2016
f1_keywords:
- C3085
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
ms.openlocfilehash: 9e174d4f8e50864dd7b33b58786cce03d50c2295
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558380"
---
# <a name="compiler-error-c3085"></a>コンパイラ エラー C3085

'constructor': コンストラクターを 'keyword' にすることはできません

コンストラクターが正しく宣言されていません。 詳細については、「[Override Specifiers](../../windows/override-specifiers-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では C3085 が生成されます。

```
// C3085.cpp
// compile with: /c /clr
ref struct S {
   S() abstract;   // C3085
   S(S%) abstract;   // C3085
};

ref struct T {
   T() sealed {}   // C3085
   T(T%) sealed {}   // C3085
};
```