---
description: '詳細情報: コンパイラの警告 (レベル 1) C4683'
title: コンパイラの警告 (レベル 1) C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: e7f2c76e7f15bb7342e60b2aa390cf0bd1a8ce05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285241"
---
# <a name="compiler-warning-level-1-c4683"></a>コンパイラの警告 (レベル 1) C4683

> '*function*': イベントソースに ' out' パラメーターが指定されています。複数のイベントハンドラーをフックする場合は注意が必要です

## <a name="remarks"></a>解説

複数のイベントシンクが COM イベントソースをリッスンしている場合は、out パラメーターの値が無視されることがあります。

次の状況では、メモリリークが発生することに注意してください。

1. メソッドに内部で割り当てられた out パラメーター (BSTR * など) がある場合。

2. イベントに複数のハンドラー (がマルチキャストイベント) がある場合。

このリークの理由は、out パラメーターは複数のハンドラーによって設定されますが、呼び出しサイトに返されるのは最後のハンドラーだけです。

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
