---
description: '詳細情報: HSE_VERSION_INFO 構造'
title: HSE_VERSION_INFO 構造体
ms.date: 11/04/2016
f1_keywords:
- HSE_VERSION_INFO
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
ms.openlocfilehash: fe03f3c4e00f9af62398993838927ce75410f17b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219630"
---
# <a name="hse_version_info-structure"></a>HSE_VERSION_INFO 構造体

この構造体は、メンバー関数の *Pver* パラメーターによってポイントされ `CHttpServer::GetExtensionVersion` ます。 Isa のバージョン番号と説明テキストを提供します。

## <a name="syntax"></a>構文

```
typedef struct _HSE_VERSION_INFO {
    DWORD dwExtensionVersion;
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;
```

#### <a name="parameters"></a>パラメーター

*dwExtensionVersion*<br/>
ISA のバージョン番号。

*lpszExtensionDesc*<br/>
ISA の説明テキスト。 既定の実装は、プレースホルダーテキストを提供します。をオーバーライドし `CHttpServer::GetExtensionVersion` て、独自の説明を指定します。

## <a name="requirements"></a>要件

**ヘッダー:** httpext. h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
