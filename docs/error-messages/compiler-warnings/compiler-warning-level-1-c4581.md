---
title: コンパイラの警告 (レベル 1) C4581
ms.date: 11/04/2016
f1_keywords:
- C4581
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
ms.openlocfilehash: 9e370bcff0c30fb508ebc22aaff1f6a56dd420a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625122"
---
# <a name="compiler-warning-level-1-c4581"></a>コンパイラの警告 (レベル 1) C4581

非推奨の動作: 'string2' 属性を処理"string1"に置き換え

このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成されることができます。 Visual c 属性のパラメーター チェックします。

以前のバージョンでは、属性値は引用符で囲まれているかどうかに受け入れられました。 値が列挙体の場合は、引用符で囲んでいない必要があります。

## <a name="example"></a>例

次の例では、C4581 が生成されます。

```
// C4581.cpp
// compile with: /c /W1
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {};

[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581
// try the following line instead
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]
class CSample : public IMyI {};
```