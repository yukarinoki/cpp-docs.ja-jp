---
description: '詳細情報: コンパイラの警告 (レベル 1) C4393'
title: コンパイラの警告 (レベル 1) C4393
ms.date: 11/04/2016
f1_keywords:
- C4393
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
ms.openlocfilehash: e68829b7e41cbc1720ceb4dced374a53e97fe8d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212715"
---
# <a name="compiler-warning-level-1-c4393"></a>コンパイラの警告 (レベル 1) C4393

' var ': const はリテラルデータメンバーに影響しません。無効

[リテラル](../../extensions/literal-cpp-component-extensions.md)データメンバーも const として指定されました。  リテラルデータメンバーは const を意味するため、宣言に const を追加する必要はありません。

次の例では、C4393 が生成されます。

```cpp
// C4393.cpp
// compile with: /clr /W1 /c
ref struct Y1 {
   literal const int staticConst = 10;   // C4393
   literal int staticConst2 = 10;   // OK
};
```
