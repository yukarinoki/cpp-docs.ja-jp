---
description: '詳細情報: 致命的なエラー C1022'
title: 致命的なエラー C1022
ms.date: 11/04/2016
f1_keywords:
- C1022
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
ms.openlocfilehash: cd608aded29b4f3ebf329586ebc03ce2e325c970
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249764"
---
# <a name="fatal-error-c1022"></a>致命的なエラー C1022

#endif が必要です。

`#if`、 `#ifdef`、 `#ifndef` の各ディレクティブに対応する `#endif` ディレクティブがありません。 各 `#if`、 `#ifdef`、 `#ifndef` に対応する `#endif`を指定してください。

次の例では C1022 が生成されます。

```cpp
// C1022.cpp
#define true 1

#if (true)
#else
#else    // C1022
```

考えられる解決策:

```cpp
// C1022b.cpp
// compile with: /c
#define true 1

#if (true)
#else
#endif
```
