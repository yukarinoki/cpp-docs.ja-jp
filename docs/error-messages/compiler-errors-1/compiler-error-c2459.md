---
description: 詳細については、「コンパイラエラー C2459」を参照してください。
title: コンパイラ エラー C2459
ms.date: 11/04/2016
f1_keywords:
- C2459
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
ms.openlocfilehash: 35cd97b93a7095aedc0015e2e7d9910172425263
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341868"
---
# <a name="compiler-error-c2459"></a>コンパイラ エラー C2459

' identifier ': が定義されています。を匿名メンバーとして追加することはできません

クラス、構造体、または共用体は、匿名共用体のメンバーによって独自のスコープ内で再定義されます。

次の例では、C2459 が生成されます。

```cpp
// C2459.cpp
// compile with: /c
class C {
   union { int C; };   // C2459
   union { int D; };
};
```
