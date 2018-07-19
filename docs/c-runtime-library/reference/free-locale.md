---
title: _free_locale | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b74725ddd7884bcc714e1048b28c53f201ebe4e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397133"
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

*ロケール*ロケール オブジェクトを解放します。

## <a name="remarks"></a>コメント

**_Free_locale**への呼び出しから取得したロケール オブジェクトを解放する関数が使用される **_get_current_locale**または **_create_locale**です。

この関数の以前の名前 **_ _free_locale** (2 つのアンダー) は推奨されていません。

## <a name="requirements"></a>要件

|**ルーチン**|必須ヘッダー|
|---------------|---------------------|
|**_free_locale**|\<locale.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_get_current_locale](get-current-locale.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
