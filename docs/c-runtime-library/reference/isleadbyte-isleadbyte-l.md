---
title: isleadbyte、_isleadbyte_l
ms.date: 11/04/2016
apiname:
- _isleadbyte_l
- isleadbyte
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 1a3f427e49e53bb553020da100b0e713350fab3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286919"
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte、_isleadbyte_l

文字がマルチバイト文字の先行バイトかどうかを判定します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>パラメーター

*c*<br/>
テストする整数。

## <a name="return-value"></a>戻り値

**isleadbyte**そうでない場合、テスト条件または 0 を引数が満たしている場合は、0 以外の値を返します。 文字セット (SBCS) のロケールの"C"ロケールでは 1 バイトで**isleadbyte**常に 0 を返します。

## <a name="remarks"></a>Remarks

**Isleadbyte**マクロが、引数がマルチバイト文字の最初のバイトの場合、0 以外の値を返します。 **isleadbyte** -1 から任意の整数引数に対して意味のある結果が生成されます (**EOF**) に**UCHAR_MAX** (0 xff) まで。

予想される引数の型の**isleadbyte**は**int**符号付き文字が渡された場合は、コンパイラが整数に変換が符号拡張、予期しない結果を生成しています。

この関数のバージョン、 **_l**サフィックスは、そのロケールに依存する動作の現在のロケールではなく渡されたロケールを使用すると同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|常に false を返します|**_isleadbyte**|常に false を返します|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**isleadbyte**|\<ctype.h>|
|**_isleadbyte_l**|\<ctype.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[バイト分類](../../c-runtime-library/byte-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)<br/>
