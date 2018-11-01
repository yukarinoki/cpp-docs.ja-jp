---
title: コンパイラ エラー C3868
ms.date: 11/04/2016
f1_keywords:
- C3868
helpviewer_keywords:
- C3868
ms.assetid: f0e45c2a-2149-4885-a03b-0d230069f03a
ms.openlocfilehash: 15152ee2e6535010b7045fe2d1362ba0064e3fbe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529195"
---
# <a name="compiler-error-c3868"></a>コンパイラ エラー C3868

'type': ジェネリック パラメーター 'parameter' に対する制約が宣言の内容と異なる

複数の宣言と同じジェネリック制約があります。  詳細については、「[ジェネリック](../../windows/generics-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3868 が生成されます。

```
// C3868.cpp
// compile with: /clr /c
interface struct I1;

generic <typename T> ref struct MyStruct;
generic <typename U> where U : I1 ref struct MyStruct;   // C3868

// OK
generic <typename T> ref struct MyStruct2;
generic <typename U> ref struct MyStruct2;

generic <typename T> where T : I1 ref struct MyStruct3;
generic <typename U> where U : I1 ref struct MyStruct3;
```