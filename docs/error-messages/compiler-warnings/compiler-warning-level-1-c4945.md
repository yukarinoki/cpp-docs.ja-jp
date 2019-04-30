---
title: コンパイラの警告 (レベル 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: 62dfbaed28f1afcdedb41d83158dfe4e8e0f61b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384167"
---
# <a name="compiler-warning-level-1-c4945"></a>コンパイラの警告 (レベル 1) C4945

'symbol': 'assembly2' からシンボルをインポートできません: 'symbol' は、別のアセンブリ 'assembly1' から既にインポートされていますが、

シンボルが参照されたアセンブリからインポートされましたが、そのシンボルが別の参照されたアセンブリから既にインポートします。 アセンブリのいずれかを参照か、アセンブリのいずれかで変更のシンボル名を取得します。

次の例では、C4945 を生成します。

```
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

それから

```
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

それから

```
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```