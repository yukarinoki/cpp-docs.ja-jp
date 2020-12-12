---
description: '詳細については、次を参照してください: DHtmlUrlEventMapEntry 構造体'
title: DHtmlUrlEventMapEntry 構造体
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: c35e3ac70d8530042ca73397b0f7c6df13501497
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220059"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry 構造体

この `DHtmlUrlEventMapEntry` 構造体は、複数 URL のイベントマップをサポートします。

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
URL に関連付けられているイベントマップ。

## <a name="requirements"></a>要件

**ヘッダー:** afxdhtml

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
