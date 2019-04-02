---
title: コンパイラ エラー C3085
ms.date: 11/04/2016
f1_keywords:
- C3085
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
ms.openlocfilehash: 01ebfa0007b9acc08742c57cc0528216eabb0441
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774751"
---
# <a name="compiler-error-c3085"></a>コンパイラ エラー C3085

'constructor': コンストラクターを 'keyword' にすることはできません

コンストラクターが正しく宣言されていません。 詳細については、「[Override Specifiers](../../extensions/override-specifiers-cpp-component-extensions.md)」を参照してください。

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