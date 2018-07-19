---
title: HSE_VERSION_INFO 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- HSE_VERSION_INFO
dev_langs:
- C++
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: daf1565c2fe2d7a4620f83b765671fea80502102
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335816"
---
# <a name="hseversioninfo-structure"></a>HSE_VERSION_INFO 構造体
この構造体を指す、 *pVer*パラメーター、`CHttpServer::GetExtensionVersion`メンバー関数。 ISA のバージョン番号と、ISA の説明テキストを提供します  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _HSE_VERSION_INFO {  
    DWORD dwExtensionVersion;  
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *dwExtensionVersion*  
 ISA のバージョン番号  
  
 *lpszExtensionDesc*  
 ISA のテキストの説明 既定の実装は、プレース ホルダー テキストを提供します。オーバーライド`CHttpServer::GetExtensionVersion`を独自の説明を提供します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** httpext.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

