---
title: コンパイラの警告 (レベル 1) C4683 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a157d3beb7c2efa7f1144a961973652e2ce384f7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194198"
---
# <a name="compiler-warning-level-1-c4683"></a>コンパイラの警告 (レベル 1) C4683

> '*関数*': イベント ソースが 'out' のパラメーターは複数のイベント ハンドラーをフックするときに注意

## <a name="remarks"></a>Remarks

1 つ以上のイベント シンクが COM イベント ソースをリッスンしている、out パラメーターの値が無視される場合があります。

次の状況で、メモリ リークが発生する注意。

1. メソッドに内部的に割り当てられている、たとえば BSTR out パラメーターがあるかどうかは * です。

2. イベントには、複数のハンドラー (はマルチキャスト イベント)。

メモリ リークの理由は、out パラメーターは 1 つ以上のハンドラーによって設定されますが、最後のハンドラーによってのみ、呼び出しサイトに返されることです。

## <a name="example"></a>例

次の例では、C4683 を生成し、その修正方法を示しています。

```cpp
// C4683.cpp
// compile with: /W1 /LD
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="xx") ];

[ object ]
__interface I {
   HRESULT f([out] int* pi);
   // try the following line instead
   // HRESULT f(int* pi);
};

[ coclass, event_source(com) ]
struct E {
   __event __interface I;   // C4683
};
```