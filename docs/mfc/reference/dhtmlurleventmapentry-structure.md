---
title: DHtmlUrlEventMapEntry 構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: d038fa188ac431f20b0b19ca8ad8bf675943954c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370059"
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
 `szUrl`  
 URL です。  
  
 *pEventMap*  
 URL に関連付けられているイベント マップします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdhtml.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

