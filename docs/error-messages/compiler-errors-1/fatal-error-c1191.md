---
description: '詳細情報: 致命的なエラー C1191'
title: 致命的なエラー C1191
ms.date: 11/04/2016
f1_keywords:
- C1191
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
ms.openlocfilehash: ef7f9ec6554daf0d83f3e597877509025512a6d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123579"
---
# <a name="fatal-error-c1191"></a>致命的なエラー C1191

' dll ' はグローバルスコープでのみインポートできます

/Clr プログラミングを使用するプログラムに mscorlib.dll をインポートする手順は、名前空間または関数には記述できませんが、グローバルスコープでは指定する必要があります。

次の例では、C1191 が生成されます。

```cpp
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

考えられる解決策:

```cpp
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```
