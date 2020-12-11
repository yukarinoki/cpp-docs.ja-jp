---
description: '詳細については、次を参照してください: TZNAME_MAX'
title: TZNAME_MAX
ms.date: 10/22/2018
f1_keywords:
- TZNAME_MAX
helpviewer_keywords:
- TZNAME_MAX constant
ms.assetid: e2286cb8-751d-4557-9650-5c4b98a8f7be
ms.openlocfilehash: 1c426c82bd198998169c385366ae5188cabd02d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162151"
---
# <a name="tzname_max"></a>TZNAME_MAX

**廃止**。 タイム ゾーン名の変数に許容される文字列の最大長です。 このマクロは \<limits.h> 、Visual Studio 2012 以前のバージョンので定義されています。 Visual Studio 2013 以降のバージョンでは定義されていません。 現在のタイム ゾーン名を保持するために必要な長さを取得するには、[_get_tzname](../c-runtime-library/reference/get-tzname.md) を使用します。

## <a name="syntax"></a>構文

```
#include <limits.h>
```

## <a name="see-also"></a>関連項目

[環境定数](../c-runtime-library/environmental-constants.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)
