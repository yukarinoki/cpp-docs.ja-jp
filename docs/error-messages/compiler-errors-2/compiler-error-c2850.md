---
title: コンパイラ エラー C2850
ms.date: 11/04/2016
f1_keywords:
- C2850
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
ms.openlocfilehash: 34c2054226ea452f76fdb15b87454677a6a6fe8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256858"
---
# <a name="compiler-error-c2850"></a>コンパイラ エラー C2850

'construct': ファイルのスコープにのみ使用できます入れ子になったコンストラクトではありません。

一部のプラグマなどの構造は、グローバル スコープでのみ表示できます。

次の例では、C2850 が生成されます。

```
// C2850.cpp
// compile with: /c /Yc
// try the following line instead
// #pragma hdrstop
namespace X {
   #pragma hdrstop   // C2850
};
```