---
title: isspace、iswspace、_isspace_l、_iswspace_l
ms.date: 4/2/2020
api_name:
- iswspace
- _isspace_l
- _iswspace_l
- isspace
- _o_isspace
- _o_iswspace
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- iswspace
- _istspace
- isspace
helpviewer_keywords:
- iswspace function
- isspace function
- _iswspace_l function
- _isspace_l function
- iswspace_l function
- isspace_l function
- _istspace function
- istspace function
ms.assetid: b851e0c0-36bb-4dac-a1a3-533540939035
ms.openlocfilehash: 43d66a191427e886941fd3dcac5dc6b71146b68a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342763"
---
# <a name="isspace-iswspace-_isspace_l-_iswspace_l"></a>isspace、iswspace、_isspace_l、_iswspace_l

整数が空白文字を表すかどうかを決定します。

## <a name="syntax"></a>構文

```C
int isspace(
   int c
);
int iswspace(
   wint_t c
);
int _isspace_l(
   int c,
   _locale_t locale
);
int _iswspace_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*C*<br/>
テストする整数。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

*c*が特定のスペース文字の表現である場合、これらのルーチンはそれぞれ 0 以外を返します。 **isspace は***、c*が空白文字 (0x09 - 0x0D または 0x20) の場合、ゼロ以外の値を返します。 **isspace**関数のテスト条件の結果は、ロケールの**LC_CTYPE**カテゴリ設定によって異なります。詳細については[、setlocale を参照_wsetlocale。](setlocale-wsetlocale.md) **_l**サフィックスを持たないこれらの関数のバージョンでは、ロケールに依存する動作に対して現在のロケールが使用されます。**_l**サフィックスを持つバージョンは、代わりに渡されたロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*c*が標準の空白文字に対応するワイド文字である場合 **、iswspace**は 0 以外の値を返します。

**isspace**および **_isspace_l**の動作は *、c*が EOF でない場合、または 0 から 0xFF の範囲 (両端を含む) の場合は未定義です。 デバッグ CRT ライブラリが使用され *、c*がこれらの値の 1 つではない場合、関数はアサーションを発生させます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_****イストスペース**|**はスペースです**|[_ismbcspace](ismbcgraph-functions.md)|**イスwスペース**|

## <a name="remarks"></a>解説

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**はスペースです**|\<ctype.h>|
|**イスwスペース**|\<ctype.h> または \<wchar.h>|
|**_isspace_l**|\<ctype.h>|
|**_iswspace_l**|\<ctype.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[文字分類](../../c-runtime-library/character-classification.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)<br/>
