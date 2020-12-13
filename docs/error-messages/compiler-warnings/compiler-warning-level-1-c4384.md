---
description: '詳細情報: コンパイラの警告 (レベル 1) C4384'
title: コンパイラの警告 (レベル 1) C4384
ms.date: 11/04/2016
f1_keywords:
- C4384
helpviewer_keywords:
- C4384
ms.assetid: fafa8eb2-cbfc-4edb-8b0f-511ff5d37ac0
ms.openlocfilehash: 1db448de2cfafe684d2d9d366db001848c67c432
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339913"
---
# <a name="compiler-warning-level-1-c4384"></a>コンパイラの警告 (レベル 1) C4384

\#プラグマ ' make_public ' はグローバルスコープでのみ使用する必要があります

[Make_public](../../preprocessor/make-public.md)プラグマが正しく適用されませんでした。

## <a name="example"></a>例

次の例では、C4384 が生成されます。

```cpp
// C4384.cpp
// compile with: /c /W1
namespace n {
   #pragma make_public(N::C)   // C4384
   namespace N {
      class C {};
   }
}
```
