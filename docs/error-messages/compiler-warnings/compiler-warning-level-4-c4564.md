---
title: コンパイラの警告 (レベル 4) C4564 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4564
dev_langs:
- C++
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea8d392251c8168490d7841ad590731b5a08e7f5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031835"
---
# <a name="compiler-warning-level-4-c4564"></a>コンパイラの警告 (レベル 4) C4564

メソッド 'method' のクラス 'class' はサポートされていない既定のパラメーター 'parameter' を定義します。

既定値を持つ 1 つまたは複数のパラメーターを持つメソッドが検出されました。 メソッドが呼び出される; パラメーターの既定値は無視されます。これらのパラメーターの値を明示的に指定します。 これらのパラメーターの値を明示的に指定しないと、C++ コンパイラでエラーが生成されます。

特定の Visual Basic で作成された次の .dll は、メソッドの引数に対して既定のパラメーターを許可します。

```
' C4564.vb
' compile with: vbc /t:library C4564.vb
Public class TestClass
   Public Sub MyMethod (a as Integer, _
                        Optional c as Integer=1)
   End Sub
End class
```

Visual Basic で作成された .dll を使用して次の C++ のサンプル

```
// C4564.cpp
// compile with: /clr /W4 /WX
#using <C4564.dll>

int main() {
   TestClass ^ myx = gcnew TestClass();   // C4564
   myx->MyMethod(9);
   // try the following line instead, to avoid an error
   // myx->MyMethod(9, 1);
}
```