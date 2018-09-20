---
title: FILETIME 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- FILETIME
dev_langs:
- C++
helpviewer_keywords:
- FILETIME structure [MFC]
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4377daa0b8a1420e4f1b5afe1f36fa0fd18d581d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384599"
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

## <a name="requirements"></a>要件

**ヘッダー:** windef.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

