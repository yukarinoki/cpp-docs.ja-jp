---
title: SYSTEMTIME 構造体
ms.date: 11/04/2016
f1_keywords:
- SYSTEMTIME
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
ms.openlocfilehash: b46482a9f4eb0165b72d74cb7d69e96e2a15e953
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559050"
---
# <a name="systemtime-structure"></a>SYSTEMTIME 構造体

`SYSTEMTIME` 構造体は、月、日、年、曜日、時間、分、秒、およびミリ秒の各メンバーを使用して日付と時刻を表します。

## <a name="syntax"></a>構文

```
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME;
```

#### <a name="parameters"></a>パラメーター

*wYear*<br/>
現在の年です。

*wMonth*<br/>
現在の月です。1 月は 1 です。

*wDayOfWeek*<br/>
現在の曜日です。日曜日 は 0、月曜日 は 1 などのように指定します。

*wDay*<br/>
月の現在の日付です。

*wHour*<br/>
現在の時刻 (時間) です。

*wMinute*<br/>
現在の時刻 (分) です。

*wSecond*<br/>
現在の時刻 (秒) です。

*wMilliseconds*<br/>
現在の時刻 (ミリ秒) です。

## <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** winbase.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

