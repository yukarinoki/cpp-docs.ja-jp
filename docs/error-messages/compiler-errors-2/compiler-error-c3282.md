---
title: コンパイラ エラー C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: 7092ddc3bf6859212cbb143572de1ef3604a13d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491508"
---
# <a name="compiler-error-c3282"></a>コンパイラ エラー C3282

ジェネリック パラメーターのリストにのみ表示できる管理または WinRTclasses、構造体、または関数

ジェネリック パラメーター リストが正しく使用されていません。  詳細については、「[ジェネリック](../../windows/generics-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では C3282 を生成し、その修正方法を示しています。

```
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