---
title: コンパイラ エラー C3898 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3898
dev_langs:
- C++
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39fe816c2637df5e5a474718d70b404bbc0c2df6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030030"
---
# <a name="compiler-error-c3898"></a>コンパイラ エラー C3898

'var': 型のデータ メンバーのマネージ型のメンバーであることができますのみ

[Initonly](../../dotnet/initonly-cpp-cli.md)データ メンバーは、ネイティブ クラスで宣言されました。  `initonly`データ メンバーは、CLR クラスでのみ宣言できます。

次の例では、C3898 が生成されます。

```
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

考えられる解決方法:

```
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```