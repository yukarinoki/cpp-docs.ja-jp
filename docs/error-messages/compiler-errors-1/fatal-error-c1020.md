---
description: '詳細情報: 致命的なエラー C1020'
title: 致命的なエラー C1020
ms.date: 11/04/2016
f1_keywords:
- C1020
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
ms.openlocfilehash: 444da85bddf65533eb5ae37278085664efeae7ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316363"
---
# <a name="fatal-error-c1020"></a>致命的なエラー C1020

予期しない #endif です。

`#endif` ディレクティブに対応する `#if`、 `#ifdef`、または `#ifndef` のディレクティブがありません。 各 `#endif` には対応するディレクティブを指定してください。

次の例では C1020 が生成されます。

```cpp
// C1020.cpp
#endif     // C1020
```

考えられる解決策:

```cpp
// C1020b.cpp
// compile with: /c
#if 1
#endif
```
