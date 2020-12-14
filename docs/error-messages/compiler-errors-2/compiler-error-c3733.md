---
description: 詳細については、「コンパイラエラー C3733」を参照してください。
title: コンパイラ エラー C3733
ms.date: 11/04/2016
f1_keywords:
- C3733
helpviewer_keywords:
- C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
ms.openlocfilehash: 768586c760a06c502a08a8a11b8a1ad4e33c4e93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245019"
---
# <a name="compiler-error-c3733"></a>コンパイラ エラー C3733

' event ': COM イベントを指定する構文が正しくありません。' __interface ' を忘れましたか?

COM イベントに使用された構文が正しくありません。 このエラーを修正するには、イベントの種類を変更するか、COM イベントルールに準拠するように構文を修正します。

次の例では、C3733 が生成されます。

```
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[coclass, event_source(com), // change 'com' to 'native' to resolve
uuid("00000000-0000-0000-0000-000000000001")]
class A
{
   __event void func();   // C3733
};

int main()
{
}
```
