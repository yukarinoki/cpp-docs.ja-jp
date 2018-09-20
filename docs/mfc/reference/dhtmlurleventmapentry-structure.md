---
title: DHtmlUrlEventMapEntry 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DHtmlUrlEventMapEntry
dev_langs:
- C++
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbac4b372f06f288eede8c578372d45334a5d707
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427525"
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

## <a name="requirements"></a>要件

**ヘッダー:** afxdhtml.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

