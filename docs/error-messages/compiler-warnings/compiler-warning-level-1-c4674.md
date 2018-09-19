---
title: コンパイラの警告 (レベル 1) C4674 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4674
dev_langs:
- C++
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b2f945982e80b49403387241f29a50876274e66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024880"
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
