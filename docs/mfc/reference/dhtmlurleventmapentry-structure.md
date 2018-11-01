---
title: DHtmlUrlEventMapEntry 構造体
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: 0a1dc86080c094a7ac89940cd43a8edac973e10c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431630"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry 構造体

`DHtmlUrlEventMapEntry`構造はマルチ URL イベント マップのサポートを提供します。

## <a name="syntax"></a>構文

```
struct DHtmlUrlEventMapEntry
{
LPCTSTR szUrl;
const DHtmlEventMapEntry *pEventMap;
};
```

#### <a name="parameters"></a>パラメーター

*szUrl*<br/>
URL。

*pEventMap*<br/>
URL に関連付けられているイベントのマップ。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdhtml.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

