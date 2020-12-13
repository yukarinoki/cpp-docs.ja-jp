---
description: '詳細情報: コンパイラの警告 (レベル 1) C4674'
title: コンパイラの警告 (レベル 1) C4674
ms.date: 11/04/2016
f1_keywords:
- C4674
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
ms.openlocfilehash: 1df7dd982f52a6987e06e888130953c1a9deb330
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334973"
---
# <a name="compiler-warning-level-1-c4674"></a>コンパイラの警告 (レベル 1) C4674

'method' は宣言された 'static' であり、パラメーターを 1 つだけ持たなければなりません。

変換演算子の署名が正しくありません。 メソッドは、ユーザー定義の変換とは見なされません。 演算子の定義の詳細については、「 [ユーザー定義の演算子 (c++/cli)](../../dotnet/user-defined-operators-cpp-cli.md) 」および「 [ユーザー定義の変換 (c++/cli)](../../dotnet/user-defined-conversions-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では C4674 が生成されます。

```cpp
// C4674.cpp
// compile with: /clr /WX /W1 /LD
ref class G {
   int op_Implicit(int i) {   // C4674
      return 0;
   }
};
```
