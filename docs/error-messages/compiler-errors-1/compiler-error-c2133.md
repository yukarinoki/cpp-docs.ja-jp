---
title: コンパイラ エラー C2133 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2133
dev_langs:
- C++
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 169b24787f1b180c7ba70c5d779e341e60ea2150
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025192"
---
# <a name="compiler-error-c2133"></a>コンパイラ エラー C2133

'identifier': サイズが不明です

可変長配列は、クラス、構造体、共用体、または列挙体のメンバーとして宣言されます。 /Za (ANSI C) オプションでは、メンバーを可変長配列は許可されません。

次の例では、C2133 が生成されます。

```
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

考えられる解決方法:

```
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```