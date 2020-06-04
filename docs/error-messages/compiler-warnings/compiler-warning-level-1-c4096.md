---
title: コンパイラの警告 (レベル 1) C4096
ms.date: 11/04/2016
f1_keywords:
- C4096
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
ms.openlocfilehash: 4f5a45339673b57f946f206e1eaff0d23ec6fee9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163937"
---
# <a name="compiler-warning-level-1-c4096"></a>コンパイラの警告 (レベル 1) C4096

' a ': インターフェイスは COM インターフェイスではありません。IDL には出力されません

COM インターフェイスとして指定したインターフェイス定義は COM インターフェイスとして定義されていないため、IDL ファイルには出力されません。

インターフェイスが COM インターフェイスであることを示すリスト属性については、「[インターフェイス属性](../../windows/attributes/interface-attributes.md)」を参照してください。

次の例では、C4096 が生成されます。

```cpp
// C4096.cpp
// compile with: /W1 /LD
#include "windows.h"
[module(name="xx")];

// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct b : a
{
};   // C4096, remove coclass or uncomment object
```
