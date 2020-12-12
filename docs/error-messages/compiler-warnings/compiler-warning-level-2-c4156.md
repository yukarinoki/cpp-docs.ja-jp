---
description: '詳細情報: コンパイラの警告 (レベル 2) C4156'
title: コンパイラの警告 (レベル 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: 243652ec191e315d7ad06a571c78a1dedce0f032
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326492"
---
# <a name="compiler-warning-level-2-c4156"></a>コンパイラの警告 (レベル 2) C4156

' delete ' の配列形式を使用せずに配列式を削除しています。配列形式の置換

の非配列形式は、 **`delete`** 配列を削除できません。 コンパイラが配列形式に変換されました **`delete`** 。

この警告は、Microsoft 拡張機能 (/Ze) でのみ発生します。

## <a name="example"></a>例

```cpp
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```
