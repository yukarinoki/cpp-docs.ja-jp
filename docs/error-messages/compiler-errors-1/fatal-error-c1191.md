---
title: 致命的なエラー C1191
ms.date: 11/04/2016
f1_keywords:
- C1191
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
ms.openlocfilehash: 89af73699120ee4d8af3cda746727d758ef6d22c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228885"
---
# <a name="fatal-error-c1191"></a>致命的なエラー C1191

'dll' はグローバル スコープでのみインポートできます。

/Clr プログラミングを使用するプログラムに mscorlib.dll をインポートする命令は、名前空間または関数では使用できませんが、グローバル スコープで表示する必要があります。

次の例では、C1191 が生成されます。

```
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

考えられる解決方法:

```
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```