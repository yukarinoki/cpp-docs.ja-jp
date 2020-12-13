---
description: 詳細については、「コンパイラエラー C3753」を参照してください。
title: コンパイラ エラー C3753
ms.date: 11/04/2016
f1_keywords:
- C3753
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
ms.openlocfilehash: a6a427001d1d9f0cfbcb1994e996208ee9ef2e2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340165"
---
# <a name="compiler-error-c3753"></a>コンパイラ エラー C3753

ジェネリックプロパティは使用できません

ジェネリックパラメーターリストは、マネージクラス、構造体、または関数でのみ使用できます。

詳細については、「 [ジェネリック](../../extensions/generics-cpp-component-extensions.md) と [プロパティ](../../extensions/property-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3753 が生成されます。

```cpp
// C3753.cpp
// compile with: /clr /c
ref struct A {
   generic <typename T>
   property int i;   // C3753 error
};
```
