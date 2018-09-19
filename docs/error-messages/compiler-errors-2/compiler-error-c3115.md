---
title: コンパイラ エラー C3115 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3115
dev_langs:
- C++
helpviewer_keywords:
- C3115
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da47a6987a1b540dc42b154c1a181c67e1524043
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090686"
---
# <a name="compiler-error-c3115"></a>コンパイラ エラー C3115

'attribute': 'construct' でこの属性は許可されません

属性は、意図していないコンストラクトに適用されました。  参照してください[属性を使用して](../../windows/attributes-by-usage.md)詳細についてはします。

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