---
title: コンパイラの警告 (レベル 1) C4167
ms.date: 11/04/2016
f1_keywords:
- C4167
helpviewer_keywords:
- C4167
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
ms.openlocfilehash: 8155fabacef4c9c9acc97b315f7267c23d032f12
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391713"
---
# <a name="compiler-warning-level-1-c4167"></a>コンパイラの警告 (レベル 1) C4167

function : 組み込み関数としてのみ使用可能です

**#pragma function** が、組み込み形式で使用する必要がある関数に対して従来の呼び出しを使用するよう、コンパイラを強制しようとしています。 このプラグマは無視されます。

この警告を回避するには、 **#pragma function**を削除します。

## <a name="example"></a>例

```
// C4167.cpp
// compile with: /W1
#include <malloc.h>
#pragma function(_alloca )   // C4167: _alloca() is intrinsic only
int main(){}
```