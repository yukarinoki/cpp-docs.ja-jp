---
title: HSE_VERSION_INFO 構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: acdf63e062aab1407daee461e22f00f5d3c59cee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hseversioninfo-structure"></a>HSE_VERSION_INFO 構造体
この構造体を指す、`pVer`内のパラメーター、`CHttpServer::GetExtensionVersion`メンバー関数。 ISA のバージョン番号と、ISA のテキストの説明を提供します。  
  
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
 ISA のテキストの説明 既定の実装は、プレース ホルダー テキストです。オーバーライド`CHttpServer::GetExtensionVersion`に独自の説明を提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** httpext.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

