---
description: '詳細情報: コンパイラの警告 (レベル 2) C4756'
title: コンパイラの警告 (レベル 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 3031a882feaba0d96adf588481de29431b337ad7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173455"
---
# <a name="compiler-warning-level-2-c4756"></a>コンパイラの警告 (レベル 2) C4756

定数演算でオーバーフローが発生しています

コンパイル中に定数演算を実行中に、コンパイラによって例外が生成されました。

次の例では、C4756 が生成されます。

```cpp
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```
