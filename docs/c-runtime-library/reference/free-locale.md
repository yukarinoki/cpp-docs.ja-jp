---
title: _free_locale
ms.date: 11/04/2016
apiname:
- _free_locale
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
- __free_locale
- free_locale
- _free_locale
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
ms.openlocfilehash: 92dc8cd711087e8e797b484d6c7e3c6c3b031b5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333041"
---
# <a name="freelocale"></a>_free_locale

ロケール オブジェクトを解放します。

## <a name="syntax"></a>構文

```C
void _free_locale(
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*locale*<br/>
解放するロケール オブジェクト。

## <a name="remarks"></a>Remarks

**_Free_locale**への呼び出しから取得したロケール オブジェクトを解放する関数が使用される **_get_current_locale**または **_create_locale**します。

この関数は、の以前の名前 **_ _free_locale** (先頭にアンダー スコア 2 つ) では推奨されていません。

## <a name="requirements"></a>必要条件

|**ルーチン**|必須ヘッダー|
|---------------|---------------------|
|**_free_locale**|\<locale.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_get_current_locale](get-current-locale.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
