---
title: ATL_URL_SCHEME 列挙型
ms.date: 11/04/2016
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
ms.openlocfilehash: 6d8307d6ea51c5ec7e63735360b8628a4c1ed782
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168580"
---
# <a name="atl_url_scheme"></a>ATL_URL_SCHEME

この列挙体のメンバーは、 [CUrl](curl-class.md)によって認識されるスキームの定数を提供します。

## <a name="syntax"></a>構文

```cpp
enum ATL_URL_SCHEME{
   ATL_URL_SCHEME_UNKNOWN = -1,
   ATL_URL_SCHEME_FTP     = 0,
   ATL_URL_SCHEME_GOPHER  = 1,
   ATL_URL_SCHEME_HTTP    = 2,
   ATL_URL_SCHEME_HTTPS   = 3,
   ATL_URL_SCHEME_FILE    = 4,
   ATL_URL_SCHEME_NEWS    = 5,
   ATL_URL_SCHEME_MAILTO  = 6,
   ATL_URL_SCHEME_SOCKS   = 7
};
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil. h

## <a name="see-also"></a>関連項目

[概念](../active-template-library-atl-concepts.md)<br/>
[CUrl:: SetScheme](curl-class.md#setscheme)<br/>
[CUrl:: GetScheme](curl-class.md#getscheme)
