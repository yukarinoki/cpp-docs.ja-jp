---
title: コンパイラ エラー C3115
ms.date: 11/04/2016
f1_keywords:
- C3115
helpviewer_keywords:
- C3115
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
ms.openlocfilehash: e334836986548d4f854dd9a5760bd8315b769d03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404092"
---
# <a name="compiler-error-c3115"></a>コンパイラ エラー C3115

'attribute': 'construct' でこの属性は許可されません

属性は、意図していないコンストラクトに適用されました。  参照してください[属性を使用して](../../windows/attributes/attributes-by-usage.md)詳細についてはします。

## <a name="example"></a>例

次の例では、C3115 が生成されます。

```
// C3115.cpp
// compile with: /c
#include <unknwn.h>
[module(name="xx")];

[object, helpstringdll(xx.dll), uuid("00000000-0000-0000-0000-000000000001")]   // C3115
// try the following line instead
// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI {
   HRESULT xx();
};
```