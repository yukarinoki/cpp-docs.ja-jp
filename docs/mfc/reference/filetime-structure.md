---
title: FILETIME 構造体
ms.date: 11/04/2016
f1_keywords:
- FILETIME
helpviewer_keywords:
- FILETIME structure [MFC]
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
ms.openlocfilehash: f70792b83637018e707b6ee48d1b169f28d46d71
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514934"
---
# <a name="filetime-structure"></a>FILETIME 構造体

`FILETIME`構造体は 1601 年 1 月 1 日から 100 ナノ秒間隔の数を表す 64 ビット値。

## <a name="syntax"></a>構文

```
typedef struct _FILETIME {
    DWORD dwLowDateTime;   /* low 32 bits */
    DWORD dwHighDateTime;  /* high 32 bits */
} FILETIME, *PFILETIME, *LPFILETIME;
```

#### <a name="parameters"></a>パラメーター

*dwLowDateTime*<br/>
32 ビット ファイルの期間の下限を指定します。

*dwHighDateTime*<br/>
32 ビット ファイルの期間の高値を指定します。

## <a name="requirements"></a>必要条件

**ヘッダー:** windef.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

