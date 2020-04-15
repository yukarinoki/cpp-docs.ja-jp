---
title: _free_locale
ms.date: 4/2/2020
api_name:
- _free_locale
- _o__free_locale
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 568e44d731f384a0503420339d716fdfdc81e13a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346053"
---
# <a name="_free_locale"></a>_free_locale

ロケール オブジェクトを解放します。

## <a name="syntax"></a>構文

```C
void _free_locale(
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*ロケール*<br/>
解放するロケール オブジェクト。

## <a name="remarks"></a>解説

**_free_locale**関数は **、_get_current_locale**または **_create_locale**の呼び出しから取得したロケール オブジェクトを解放するために使用されます。

この関数の以前の名前**は、__free_locale** (先頭に 2 つのアンダースコアを付けた) は非推奨になりました。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|**ルーチン**|必須ヘッダー|
|---------------|---------------------|
|**_free_locale**|\<locale.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[_get_current_locale](get-current-locale.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
