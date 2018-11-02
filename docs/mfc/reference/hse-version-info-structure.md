---
title: HSE_VERSION_INFO 構造体
ms.date: 11/04/2016
f1_keywords:
- HSE_VERSION_INFO
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
ms.openlocfilehash: 6bdb668be037dfaa07e1121e4b61ea332e430e31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577290"
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

*dwExtensionVersion*<br/>
ISA のバージョン番号

*lpszExtensionDesc*<br/>
ISA のテキストの説明 既定の実装は、プレース ホルダー テキストを提供します。オーバーライド`CHttpServer::GetExtensionVersion`を独自の説明を提供します。

## <a name="requirements"></a>必要条件

**ヘッダー:** httpext.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

