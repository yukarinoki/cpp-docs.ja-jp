---
title: isleadbyte、_isleadbyte_l
ms.date: 4/2/2020
api_name:
- _isleadbyte_l
- isleadbyte
- _o__isleadbyte_l
- _o_isleadbyte
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _istleadbyte
- _isleadbyte_l
- isleadbyte
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
ms.openlocfilehash: dddf1d669f77805df8e00f506b6427603ac8fd9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343836"
---
# <a name="isleadbyte-_isleadbyte_l"></a>isleadbyte、_isleadbyte_l

文字がマルチバイト文字の先行バイトかどうかを判定します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>パラメーター

*C*<br/>
テストする整数。

## <a name="return-value"></a>戻り値

**引数**がテスト条件を満たす場合は 0 以外の値を返し、満たない場合は 0 を返します。 "C" ロケールおよび 1 バイト文字セット (SBCS) ロケールでは **、isleadbyte**は常に 0 を返します。

## <a name="remarks"></a>解説

引数がマルチバイト文字の最初のバイトの場合 **、isleadbyte**マクロは 0 以外の値を返します。 **isleadbyte は**、-1 (**EOF**) から**UCHAR_MAX** (0xFF) までの整数引数に対して意味のある結果を生成します。

想定される引数の型**は** **int**です。符号付き文字が渡されると、コンパイラは符号拡張によって整数に変換し、予測できない結果を生じる可能性があります。

**_l**サフィックスを持つこの関数のバージョンは、ロケール依存の動作に現在のロケールの代わりに渡されたロケールを使用する点を除いて同じです。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|常に false を返します|**_isleadbyte**|常に false を返します|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**isleadbyte**|\<ctype.h>|
|**_isleadbyte_l**|\<ctype.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[_ismbbルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
