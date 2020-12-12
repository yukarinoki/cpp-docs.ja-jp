---
description: '詳細については、次を参照してください: ATL_URL_SCHEME'
title: ATL_URL_SCHEME 列挙型
ms.date: 11/04/2016
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
ms.openlocfilehash: 72c149345a0e1edd41bfc9b32d1e94ab6477d488
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165135"
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
