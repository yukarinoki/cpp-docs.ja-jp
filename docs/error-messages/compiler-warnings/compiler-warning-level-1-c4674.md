---
title: コンパイラの警告 (レベル 1) C4674
ms.date: 11/04/2016
f1_keywords:
- C4674
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
ms.openlocfilehash: f7db2f37224a8defffb545b0cfaf018fd4654227
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374548"
---
# <a name="compiler-warning-level-1-c4674"></a>コンパイラの警告 (レベル 1) C4674

'method' は宣言された 'static' であり、パラメーターを 1 つだけ持たなければなりません。

変換演算子の署名が正しくありません。 メソッドは、ユーザー定義の変換とは見なされません。 演算子の定義の詳細については、次を参照してください。[ユーザー定義演算子 (C +/cli CLI)](../../dotnet/user-defined-operators-cpp-cli.md)と[ユーザー定義の変換 (C +/cli CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)します。

## <a name="example"></a>例

次の例では C4674 が生成されます。

```
// C4674.cpp
// compile with: /clr /WX /W1 /LD
ref class G {
   int op_Implicit(int i) {   // C4674
      return 0;
   }
};
```
