---
title: TZNAME_MAX | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- TZNAME_MAX
dev_langs:
- C++
helpviewer_keywords:
- TZNAME_MAX constant
ms.assetid: e2286cb8-751d-4557-9650-5c4b98a8f7be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc44ff3178493132c1b8d5dc168cee6be4c5bc56
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990153"
---
# <a name="tznamemax"></a>TZNAME_MAX

**互換性のために残されています**。 タイム ゾーン名の変数に許容される文字列の最大長です。 このマクロは Visual Studio 2012 以前のバージョンで \<limits.h> に定義されています。 Visual Studio 2013 以降のバージョンでは定義されていません。 現在のタイム ゾーン名を保持するために必要な長さを取得するには、[_get_tzname](../c-runtime-library/reference/get-tzname.md) を使用します。

## <a name="syntax"></a>構文

```
#include <limits.h>
```

## <a name="see-also"></a>参照

[環境定数](../c-runtime-library/environmental-constants.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)
