---
title: _ismbcl0、_ismbcl0_l、_ismbcl1、_ismbcl1_l、_ismbcl2、_ismbcl2_l
ms.date: 4/2/2020
api_name:
- _ismbcl2
- _ismbcl1
- _ismbcl0
- _ismbcl2_l
- _ismbcl1_l
- _ismbcl0_l
- _o__ismbcl0
- _o__ismbcl0_l
- _o__ismbcl1
- _o__ismbcl1_l
- _o__ismbcl2
- _o__ismbcl2_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ismbcl0
- _ismbcl1_l
- _ismbcl0
- ismbcl1
- ismbcl0_l
- _ismbcl2_l
- ismbcl2
- ismbcl1_l
- _ismbcl1
- _ismbcl0_l
- _ismbcl2
- ismbcl2_l
helpviewer_keywords:
- _ismbcl0_l function
- _ismbcl2 function
- _ismbcl1_l function
- ismbcl2 function
- _ismbcl1 function
- ismbcl0_l function
- ismbcl2_l function
- ismbcl1_l function
- ismbcl0 function
- ismbcl1 function
- _ismbcl2_l function
- _ismbcl0 function
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
ms.openlocfilehash: 813e6359d17f2ea4c6c0ded87a97c2afda243642
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919738"
---
# <a name="_ismbcl0-_ismbcl0_l-_ismbcl1-_ismbcl1_l-_ismbcl2-_ismbcl2_l"></a>_ismbcl0、_ismbcl0_l、_ismbcl1、_ismbcl1_l、_ismbcl2、_ismbcl2_l

現在のロケールまたは指定された LC_CTYPE 変換状態カテゴリを使用する、**コード ページ 932 固有の関数**。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _ismbcl0(
   unsigned int c
);
int _ismbcl0_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcl1(
   unsigned int c
);
int _ismbcl1_l(
   unsigned int c ,
   _locale_t locale
);
int _ismbcl2(
   unsigned int c
);
int _ismbcl2_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*40u-c*<br/>
テストする文字。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。 *C* <= 255 で、対応する **_ismbb**ルーチン (たとえば、 **_ismbcalnum**が **_ismbbalnum**に対応する) がある場合、結果は対応する **_ismbb**ルーチンの戻り値になります。

## <a name="remarks"></a>解説

これらの各関数は特定の条件で特定のマルチバイト文字をテストします。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 **_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

|ルーチン|テスト条件 (コード ページ 932 のみ)|
|-------------|-------------------------------------------|
|**_ismbcl0**|JIS 非漢字: 0x8140<=*c*<= 0x889E。|
|**_ismbcl0_l**|JIS 非漢字: 0x8140<=*c*<= 0x889E。|
|**_ismbcl1**|JIS レベル-1: 0x889F<=*c*<= 0x9872。|
|**_ismbcl1_l**|JIS レベル-1: 0x889F<=*c*<= 0x9872。|
|**_ismbcl2**|JIS レベル 2: 0x989F<=*c*<= 0xEAA4。|
|**_ismbcl2_l**|JIS レベル 2: 0x989F<=*c*<= 0xEAA4。|

関数は、指定された値*c*が上で説明したテスト条件に一致することを確認しますが、 *c*が有効なマルチバイト文字であることを確認しません。 下位バイトが範囲 0x00 - 0x3F、0x7F、または 0xFD - 0xFF にある場合、これらの関数は 0 以外の値を返し、文字がテスト条件を満たすことを示します。 マルチバイト文字が定義されているかどうかをテストするために [_ismbbtrail](ismbbtrail-ismbbtrail-l.md) を使用します。

**終了コードページ932固有**

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_ismbcl0**|\<mbstring.h>|
|**_ismbcl0_l**|\<mbstring.h>|
|**_ismbcl1**|\<mbstring.h>|
|**_ismbcl1_l**|\<mbstring.h>|
|**_ismbcl2**|\<mbstring.h>|
|**_ismbcl2_l**|\<mbstring.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
