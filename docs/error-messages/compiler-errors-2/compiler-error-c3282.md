---
description: 詳細については、「コンパイラエラー C3282」を参照してください。
title: コンパイラ エラー C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: 9455f7e109da0efa87b215f0695eeeb41648c2b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311891"
---
# <a name="compiler-error-c3282"></a>コンパイラ エラー C3282

ジェネリックパラメーターリストは、マネージまたは WinRTclasses、構造体、または関数でのみ使用できます

ジェネリック パラメーター リストが正しく使用されていません。  詳細については、「[ジェネリック](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では C3282 を生成し、その修正方法を示しています。

```cpp
// C3282.cpp
// compile with: /clr /c
generic <typename T> int x;   // C3282

ref struct GC0 {
   generic <typename T> int x;   // C3282
};

// OK
generic <typename T>
ref class M {};
```
