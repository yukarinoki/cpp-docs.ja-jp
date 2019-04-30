---
title: コンパイラの警告 (レベル 1) C4392
ms.date: 11/04/2016
f1_keywords:
- C4392
helpviewer_keywords:
- C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
ms.openlocfilehash: 1dc0c546509b17132358f432f6a781035a314a72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386422"
---
# <a name="compiler-warning-level-1-c4392"></a>コンパイラの警告 (レベル 1) C4392

'signature': 組み込み関数の引数の数が正しくないは、'number' 引数が必要です

コンパイラ組み込み関数の宣言には、間違った数の引数が必要があります。 結果のイメージは正しく動作しない可能性があります。

この警告を解決するか、宣言を修正してまたは宣言を削除して単に #include 適切なヘッダー ファイル。

次の例では、C4392 が生成されます。

```
// C4392.cpp
// compile with: /W1
// processor: x86
// uncomment the following line and delete the line that
// generated the warning to resolve
// #include "xmmintrin.h"

#ifdef  __cplusplus
extern "C" {
#endif

extern void _mm_stream_pd(double *dp);   // C4392

#ifdef  __cplusplus
}
#endif

int main()
{
}
```