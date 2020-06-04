---
title: _mbccpy、_mbccpy_l
ms.date: 4/2/2020
api_name:
- _mbccpy
- _mbccpy_l
- _o__mbccpy
- _o__mbccpy_l
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
- _mbccpy
- tccpy
- ftccpy
- mbccpy
- _tccpy
- _ftccpy
helpviewer_keywords:
- _tccpy function
- _tccpy_l function
- tccpy_l function
- tccpy function
- mbccpy function
- _mbccpy_l function
- _mbccpy function
- mbccpy_l function
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
ms.openlocfilehash: a265a37ba4c16dd15e6b50035dcc65bc8afbe7c7
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919579"
---
# <a name="_mbccpy-_mbccpy_l"></a>_mbccpy、_mbccpy_l

文字列のマルチバイト文字を他の文字列にコピーします。 これらの関数にはセキュリティが強化されたバージョンがあります。「[_mbccpy_s、_mbccpy_s_l](mbccpy-s-mbccpy-s-l.md)」をご覧ください。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
void _mbccpy(
   unsigned char *dest,
   const unsigned char *src
);
void _mbccpy_l(
   unsigned char *dest,
   const unsigned char *src,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*dest*<br/>
コピー先。

*src*<br/>
コピーするマルチバイト文字。

*locale*<br/>
使用するロケール。

## <a name="remarks"></a>解説

**_Mbccpy**関数は、 *src*から*dest*に1つのマルチバイト文字をコピーします。

この関数は、パラメーターを検証します。 **_Mbccpy**に*dest*または*src*の null ポインターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 **errno**は**EINVAL**に設定されます。

**_mbccpy**は、ロケールに依存する動作に現在のロケールを使用します。 **_mbccpy_l**は **_mbccpy**と同じですが、 **_mbccpy_l**はロケールに依存する動作に渡されたロケールを使用する点が異なります。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**セキュリティに関するメモ** null で終わる文字列を使用してください。 null で終わる文字列はターゲット バッファーのサイズを超えないようにしてください。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。 バッファー オーバーランは、システムを攻撃するときによく使用される方法であり、その結果、認められていない権限が昇格されます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|マクロまたはインライン関数にマップされます|**_mbccpy**|マクロまたはインライン関数にマップされます|
|**_tccpy_l**|該当なし|**_mbccpy_l**|該当なし|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mbccpy**|\<mbctype.h>|
|**_mbccpy_l**|\<mbctype.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[国](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
