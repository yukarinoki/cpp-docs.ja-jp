---
title: _mbsbtype、_mbsbtype_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be098cb1fe53e1345f0c4f40212657f4bfd97f4f
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
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

**_mbsbtype**と **_mbsbtype_l**指定したバイトのテストの結果を示す整数値を返します。 次の表のマニフェスト定数は、Mbctype.h で定義されています。

|戻り値|バイトの種類|
|------------------|---------------|
|**_MBC_SINGLE** (0)|1 バイト文字。 たとえば、コード ページ 932 で **_mbsbtype**指定したバイト範囲は、0x20-0x7E または 0xA1 - 0 xdf 場合 0 を返します。|
|**_MBC_LEAD** (1)|マルチバイト文字の先行バイト。 たとえば、コード ページ 932 で **_mbsbtype**指定したバイト範囲は、0x81 から 0x9F または 0xE0 - - 0 xfc 場合 1 を返します。|
|**_MBC_TRAIL** (2)|マルチバイト文字の後続バイト。 たとえば、コード ページ 932 で **_mbsbtype**指定したバイト範囲は、0x40 ~ 0x7E または 0x80 ~ 0 xfc 2 を返します。|
|**継続**(-1)|**NULL**文字列、無効な文字、または null のバイト オフセット位置にバイトの前に見つかった*カウント*で*mbstr*です。|

## <a name="remarks"></a>コメント

**_Mbsbtype**関数はマルチバイト文字の文字列内のバイトの種類を決定します。 関数はオフセットでバイトしか*カウント*で*mbstr*、指定したバイトの前に無効な文字は無視されます。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 この関数のバージョン、 **_l**サフィックスがこのロケールに依存する動作に現在のロケールを使用のバージョン、 **_l**渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じ代わりにします。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合は、入力文字列が**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**継続**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 戻り値として使用されるマニフェスト定数の場合。

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
