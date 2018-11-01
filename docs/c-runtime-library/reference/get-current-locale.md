---
title: _get_current_locale
ms.date: 11/04/2016
apiname:
- _get_current_locale
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_current_locale
- __get_current_locale
- _get_current_locale
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
ms.openlocfilehash: 87c30ee701d8f7d3a89a0aa61ba18a7f854bc9b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511892"
---
# <a name="getcurrentlocale"></a>_get_current_locale

現在のロケールを表すロケール オブジェクトを取得します。

## <a name="syntax"></a>構文

```C
_locale_t _get_current_locale(void);
```

## <a name="return-value"></a>戻り値

現在のロケールを表すロケール オブジェクト。

## <a name="remarks"></a>Remarks

**_Get_current_locale**関数は、現在設定されている取得のスレッドのロケールと、そのロケールを表すロケール オブジェクトを返します。

この関数は、の以前の名前 **_ _get_current_locale** (先頭にアンダー スコア 2 つ) では推奨されていません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_current_locale**|\<locale.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
