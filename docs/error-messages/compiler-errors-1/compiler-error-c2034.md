---
title: コンパイラ エラー C2034 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2034
dev_langs:
- C++
helpviewer_keywords:
- C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1dadc3249b7e58410eb153f8d298fca06a44ea7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034422"
---
# <a name="compiler-error-c2034"></a>コンパイラ エラー C2034

'identifier': 型のビット フィールドのビット数には小さすぎます

ビット フィールドの宣言内のビット数は、基本型のサイズを超えています。

次の例では、C2034 が生成されます。

```
// C2034.cpp
struct A {
   char test : 9;   // C2034, char has 8 bits
};
```

考えられる解決方法:

```
// C2034b.cpp
// compile with: /c
struct A {
   char test : 8;
};
```