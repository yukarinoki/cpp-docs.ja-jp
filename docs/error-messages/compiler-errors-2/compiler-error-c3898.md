---
description: 詳細については、「コンパイラエラー C3898」を参照してください。
title: コンパイラ エラー C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: 4b51683b13fa9328475ba09473ef1cae5663b009
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238961"
---
# <a name="compiler-error-c3898"></a>コンパイラ エラー C3898

' var ': 型データメンバーはマネージド型のメンバーにのみすることができます

[Initonly](../../dotnet/initonly-cpp-cli.md)データメンバーがネイティブクラスで宣言されました。  **`initonly`** データメンバーは CLR クラスでのみ宣言できます。

次の例では、C3898 が生成されます。

```cpp
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

考えられる解決策:

```cpp
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```
