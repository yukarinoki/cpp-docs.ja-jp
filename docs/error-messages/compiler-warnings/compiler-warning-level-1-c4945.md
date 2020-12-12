---
description: '詳細情報: コンパイラの警告 (レベル 1) C4945'
title: コンパイラの警告 (レベル 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: df05b0882b672f22428e9ddef0b195043cca7d2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327987"
---
# <a name="compiler-warning-level-1-c4945"></a>コンパイラの警告 (レベル 1) C4945

' symbol ': ' assembly2 ' からシンボルをインポートできません: ' symbol ' は既に別のアセンブリ ' assembly1 ' からインポートされています

参照アセンブリからシンボルがインポートされましたが、そのシンボルは既に別の参照アセンブリからインポートされています。 アセンブリのいずれかを参照しないか、いずれかのアセンブリでシンボル名が変更されています。

次のサンプルでは、C4945 が生成されます。

```csharp
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

それから

```csharp
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

それから

```cpp
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```
