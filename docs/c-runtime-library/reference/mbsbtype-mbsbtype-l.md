---
title: _mbsbtype、_mbsbtype_l
ms.date: 11/04/2016
apiname:
- _mbsbtype_l
- _mbsbtype
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
ms.openlocfilehash: 5c2927b4e4b68b1284341fe7e767ec50feb21a44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566804"
---
# <a name="mbsbtype-mbsbtypel"></a>_mbsbtype、_mbsbtype_l

文字列内のバイトの種類を返します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _mbsbtype(
   const unsigned char *mbstr,
   size_t count
);
int _mbsbtype_l(
   const unsigned char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*mbstr*<br/>
マルチバイト文字のシーケンスのアドレス。

*count*<br/>
文字列の先頭からのバイト オフセット。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbsbtype**と **_mbsbtype_l**指定されたバイトに対するテストの結果を示す整数値を返します。 次の表のマニフェスト定数は、Mbctype.h で定義されています。

|戻り値|バイトの種類|
|------------------|---------------|
|**_MBC_SINGLE** (0)|1 バイト文字。 たとえば、コード ページ 932 で **_mbsbtype** 0 xdf の範囲 0x20-0x7E または 0xA1 - 指定したバイトがある場合は 0 を返します。|
|**_MBC_LEAD** (1)|マルチバイト文字の先行バイト。 たとえば、コード ページ 932 で **_mbsbtype**指定したバイトが 0x81-0x81-0x9f または 0xe0-0xfc の範囲内で 0 xfc 場合 1 を返します。|
|**_MBC_TRAIL** (2)|マルチバイト文字の後続バイト。 たとえば、コード ページ 932 で **_mbsbtype**指定したバイトが範囲 0x40 ~ 0x7E または 0x80 ~ 0 xfc 2 を返します。|
|**継続**(-1)|**NULL**文字列、無効な文字、または null のバイト オフセット位置にバイトの前に見つかった*カウント*で*mbstr*します。|

## <a name="remarks"></a>Remarks

**_Mbsbtype**関数は、マルチバイト文字の文字列のバイトの種類を決定します。 関数はオフセット位置にあるバイトだけ*カウント*で*mbstr*、指定したバイトの前に無効な文字は無視されます。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 この関数のバージョン、 **_l**サフィックスは、このロケールに依存する動作の現在のロケールを使用とバージョン、 **_l**サフィックスは、渡されたロケール パラメーターを使用する点を除いて同じです代わりにします。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

入力文字列が場合**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**継続**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 戻り値として使用されるマニフェスト定数の場合。

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
