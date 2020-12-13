---
description: '詳細情報: コンパイラの警告 (レベル 1) C4392'
title: コンパイラの警告 (レベル 1) C4392
ms.date: 11/04/2016
f1_keywords:
- C4392
helpviewer_keywords:
- C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
ms.openlocfilehash: d10b966f6727ec3461255d3789a6e9a7aed78c22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339892"
---
# <a name="compiler-warning-level-1-c4392"></a>コンパイラの警告 (レベル 1) C4392

' signature ': 組み込み関数の引数の数が正しくありません。 ' number ' 個の引数が必要です

コンパイラ組み込みの関数宣言に、間違った数の引数が含まれていました。 結果のイメージが正常に実行されない可能性があります。

この警告を修正するには、宣言を修正するか、宣言を削除して、適切なヘッダーファイルを #include します。

次の例では、C4392 が生成されます。

```cpp
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
