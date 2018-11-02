---
title: コンパイラの警告 (レベル 1) C4079
ms.date: 11/04/2016
f1_keywords:
- C4079
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
ms.openlocfilehash: 8f9a9e05ab2a65ad954f9928f7b9fab0e7fee9cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564568"
---
# <a name="compiler-warning-level-1-c4079"></a>コンパイラの警告 (レベル 1) C4079

不要なトークン 'token' が見つかりました

プラグマの引数リストで、区切り記号の予期しないトークンが発生します。 プラグマの残りの部分は無視されました。

次の例では、C4079 が生成されます。

```
// C4079.cpp
// compile with: /W1
#pragma warning(disable : 4081)
#pragma pack(c,16)   // C4079

int main() {
}
```