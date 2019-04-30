---
title: コンパイラの警告 (レベル 1) C4391
ms.date: 11/04/2016
f1_keywords:
- C4391
helpviewer_keywords:
- C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
ms.openlocfilehash: d9d1cebe08a6a163d76271ab001ec91b7cee82a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386461"
---
# <a name="compiler-warning-level-1-c4391"></a>コンパイラの警告 (レベル 1) C4391

'signature': 組み込み関数に対して正しくない戻り値の型は、'type' が必要です

コンパイラ組み込み関数の宣言には、正しくない戻り値の型が必要があります。 結果のイメージは正しく動作しない可能性があります。

この警告を解決するか、宣言を修正してまたは宣言を削除して単に #include 適切なヘッダー ファイル。

次の例では、C4391 が生成されます。

```
// C4391.cpp
// compile with: /W1
// processor: x86
// uncomment the following line and delete the line that
// generated the warning to resolve
// #include "xmmintrin.h"

#ifdef  __cplusplus
extern "C" {
#endif

extern void _mm_load_ss(float *p);   // C4391

#ifdef  __cplusplus
}
#endif

int main()
{
}
```