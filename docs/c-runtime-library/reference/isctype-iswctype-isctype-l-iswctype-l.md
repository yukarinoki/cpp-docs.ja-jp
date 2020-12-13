---
description: '詳細については、次を参照してください: _isctype、iswctype、_isctype_l、_iswctype_l'
title: _isctype、iswctype、_isctype_l、_iswctype_l
ms.date: 4/2/2020
api_name:
- _isctype_l
- iswctype
- _iswctype_l
- _isctype
- _o__isctype
- _o__isctype_l
- _o__iswctype_l
- _o_iswctype
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- iswctype
- _isctype
- _isctype_l
- _iswctype
- isctype
- iswctype_l
- isctype_l
- _iswctype_l
helpviewer_keywords:
- isctype_l function
- iswctype_l function
- iswctype function
- _isctype function
- _isctype_l function
- _iswctype_l function
- isctype function
- _iswctype function
ms.assetid: cf7509b7-12fc-4d95-8140-ad2eb98173d3
ms.openlocfilehash: 2b8bd10cd4240e4382d17cb8028589ddf4dd8b2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332669"
---
# <a name="_isctype-iswctype-_isctype_l-_iswctype_l"></a>_isctype、iswctype、_isctype_l、_iswctype_l

*Desc* 引数で指定された ctype プロパティについて *c* をテストします。 *Desc* の有効な値ごとに、同等のワイド文字分類ルーチンがあります。

## <a name="syntax"></a>構文

```C
int _isctype(
   int c,
   _ctype_t desc
);
int _isctype_l(
   int c,
   _ctype_t desc,
   _locale_t locale
);
int iswctype(
   wint_t c,
   wctype_t desc
);
int _iswctype_l(
   wint_t c,
   wctype_t desc,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする整数。

*順*<br/>
テストするプロパティ。 これは通常、ctype または [wctype](wctype.md) を使用して取得されます。

*locale*<br/>
任意のロケール依存テストで使用されるロケール。

## <a name="return-value"></a>戻り値

現在のロケールで *desc* によって指定されたプロパティが *c* にある場合、 **_isctype** と **iswctype** は0以外の値を返します。それ以外の場合は0を返します。 **_L** サフィックスを持つこれらの関数のバージョンは同じですが、ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用する点が異なります。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*C* が EOF でない場合、または 0 ~ 0xff の範囲内にある場合、 **_isctype** と **_isctype_l** の動作は未定義です。 デバッグ CRT ライブラリが使用され、 *c* がこれらの値のいずれでもない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|該当なし|**_isctype**|該当なし|**_iswctype**|
|該当なし|**_isctype_l**|該当なし|**_iswctype_l**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_isctype**|\<ctype.h>|
|**iswctype**|\<ctype.h> または \<wchar.h>|
|**_isctype_l**|\<ctype.h>|
|**_iswctype_l**|\<ctype.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
