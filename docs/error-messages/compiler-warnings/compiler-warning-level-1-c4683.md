---
title: コンパイラの警告 (レベル 1) C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: f86cf8f6d894d6efaa1b49977634956dc1979a98
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175430"
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
