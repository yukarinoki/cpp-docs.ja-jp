---
title: _mbsbtype、_mbsbtype_l
ms.date: 4/2/2020
api_name:
- _mbsbtype_l
- _mbsbtype
- _o__mbsbtype
- _o__mbsbtype_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: d71a061d9af5028c9bc6b4008f9904606a233592
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340873"
---
# <a name="_mbsbtype-_mbsbtype_l"></a>_mbsbtype、_mbsbtype_l

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

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbsbtype**と **_mbsbtype_l**は、指定されたバイトのテストの結果を示す整数値を返します。 次の表のマニフェスト定数は、Mbctype.h で定義されています。

|戻り値|バイトの種類|
|------------------|---------------|
|**_MBC_SINGLE** (0)|1 バイト文字。 たとえば、コード・ページ 932 では、指定したバイトが 0x20 から 0x7E または 0xA1 から 0xDF の範囲内にある場合 **、_mbsbtype**は 0 を戻します。|
|**_MBC_LEAD** (1)|マルチバイト文字の先行バイト。 例えば、コード・ページ 932 では、指定したバイトが 0x81 から 0x9F または 0xE0 から 0xFC の範囲内にある場合 **、_mbsbtype**は 1 を戻します。|
|**_MBC_TRAIL** (2)|マルチバイト文字の後続バイト。 たとえば、コード・ページ 932 では、指定したバイトが 0x40 から 0x7E または 0x80 から 0xFC の範囲内にある場合 **、_mbsbtype**は 2 を戻します。|
|**_MBC_ILLEGAL** (-1)|*mbstr*のオフセット*カウント*のバイトの前に NULL**文字列、** 無効な文字、または NULL バイトが見つかりました。|

## <a name="remarks"></a>解説

**_mbsbtype**関数は、マルチバイト文字列のバイトの型を決定します。 この関数は、指定されたバイトの前に無効な文字を無視して *、mbstr*のオフセット*カウント*のバイトだけを検査します。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細については、「[setlocale](setlocale-wsetlocale.md)」を参照してください。 **_l**サフィックスを持たないこの関数のバージョンでは、このロケール依存の動作に現在のロケールが使用されます。**サフィックスが_l**のバージョンは、代わりに渡された locale パラメーターを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

入力文字列が**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合 **、errno**は**EINVAL**に設定され、関数は **_MBC_ILLEGAL**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 戻り値として使用されるマニフェスト定数の場合。

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
