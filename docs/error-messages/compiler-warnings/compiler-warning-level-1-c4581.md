---
description: '詳細情報: コンパイラの警告 (レベル 1) C4581'
title: コンパイラの警告 (レベル 1) C4581
ms.date: 11/04/2016
f1_keywords:
- C4581
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
ms.openlocfilehash: 6fffa3f7ea74cb17eae7fe4af2575e1d574084fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332212"
---
# <a name="compiler-warning-level-1-c4581"></a>コンパイラの警告 (レベル 1) C4581

非推奨の動作: 属性を処理するために ' string2 ' ' が ' string2 ' に置き換えられました

このエラーは、Visual Studio 2005 で実行されたコンパイラ準拠作業の結果として生成される場合があります。 Visual C++ の属性を確認するには、パラメーターをチェックします。

以前のバージョンでは、属性値は引用符で囲まれているかどうかにかかわらず受け入れられていました。 値が列挙型の場合は、引用符で囲まないでください。

## <a name="example"></a>例

次の例では、C4581 が生成されます。

```cpp
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
