---
title: コンパイラの警告 (レベル 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: c68e84daa2ca1aa023123203bb851e92758f9e40
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447684"
---
# <a name="compiler-warning-level-1-c4237"></a>コンパイラの警告 (レベル 1) C4237

'keyword' キーワードがサポートされていませんが、将来使用するために予約されています

キーワード、C++仕様は、Microsoft で実装されていませんC++、コンパイラが、キーワードは、ユーザー定義の記号として使用できません。

次の例では、C4237 が生成されます。

```
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```