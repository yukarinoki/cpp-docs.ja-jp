---
title: _cgets_s、_cgetws_s
ms.date: 4/2/2020
api_name:
- _cgetws_s
- _cgets_s
- _o__cgets_s
- _o__cgetws_s
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
- api-ms-win-crt-conio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cgets_s
- cgets_s
- cgetws_s
- _cgetws_s
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
ms.openlocfilehash: b4871ff2c362e2c6cbe37be6a31bde4e6e258709
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333544"
---
# <a name="_cgets_s-_cgetws_s"></a>_cgets_s、_cgetws_s

コンソールから文字列を取得します。 これらのバージョンの [_cgets および _cgetws](../../c-runtime-library/cgets-cgetws.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t _cgets_s(
   char *buffer,
   size_t numberOfElements,
   size_t *pSizeRead
);
errno_t _cgetws_s(
   wchar_t *buffer
   size_t numberOfElements,
   size_t *pSizeRead
);
template <size_t size>
errno_t _cgets_s(
   char (&buffer)[size],
   size_t *pSizeRead
); // C++ only
template <size_t size>
errno_t _cgetws_s(
   wchar_t (&buffer)[size],
   size_t *pSizeRead
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
データの格納場所。

*要素の数*<br/>
バッファーのサイズです。単位はバイト数またワイド文字数です。これは、読み取る最大の文字数でもあります。

*を読み取る*<br/>
実際に読み取った文字数。

## <a name="return-value"></a>戻り値

成功した場合の戻り値は 0 です。それ以外の場合 (エラー発生時) は、エラー コードです。

### <a name="error-conditions"></a>エラー条件

|*バッファー*|*要素の数*|*を読み取る*|戻り値|*バッファ*の内容|
|--------------|------------------------|-----------------|------------|--------------------------|
|**NULL**|any|any|**Einval**|該当なし|
|**NULL**ではありません|ゼロ|any|**Einval**|変更されない|
|**NULL**ではありません|any|**NULL**|**Einval**|長さゼロの文字列|

## <a name="remarks"></a>解説

**_cgets_s**し、コンソールから文字列を読み取 **_cgetws_s、** 文字列を (null 終端文字で) *buffer*にコピーします。 **_cgetws_s**関数のワイド文字バージョンです。文字サイズ以外の場合、これら 2 つの関数の動作は同じです。 読み取る文字列の最大サイズは *、numberOfElements*パラメーターとして渡されます。 このサイズには、終端の null に対応する追加の文字を含める必要があります。 実際に読み取られた文字数は *、pSizeRead*に格納されます。

操作中に、またはパラメーターを検証する際にエラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」の説明にあるとおり無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合 **、errno**は**EINVAL**に設定され **、EINVAL**が戻されます。

C++ では、テンプレートのオーバーロードを利用すると、これらの関数の使用が簡素化されます。オーバーロードでは、バッファー長が自動的に推論されるのでサイズ引数を指定する必要がなくなるだけでなく、古くてセキュリティが万全ではない関数を新しくてセキュリティが強化された関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ ライブラリ バージョンは、まずバッファーに 0xFE を設定します。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_cgetts_s**|**_cgets_s**|**_cgets_s**|**_cgetws_s**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_cgets_s**|\<conio.h>|
|**_cgetws_s**|\<conio.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch、_getwch](getch-getwch.md)<br/>
