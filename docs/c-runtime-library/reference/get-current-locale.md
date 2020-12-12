---
description: '詳細については、次を参照してください: _get_current_locale'
title: _get_current_locale
ms.date: 11/04/2016
api_name:
- _get_current_locale
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 672914875aebbe020fbfab0c4958ce2963958432
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341491"
---
# <a name="_get_current_locale"></a>_get_current_locale

現在のロケールを表すロケール オブジェクトを取得します。

## <a name="syntax"></a>構文

```C
_locale_t _get_current_locale(void);
```

## <a name="return-value"></a>戻り値

現在のロケールを表すロケール オブジェクト。

## <a name="remarks"></a>解説

**_Get_current_locale** 関数は、スレッドに対して現在設定されているロケールを取得し、そのロケールを表すロケールオブジェクトを返します。

この関数の以前の名前 (2 つの先頭のアンダースコア) は非推奨となりました。 **__get_current_locale** 。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_current_locale**|\<locale.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
