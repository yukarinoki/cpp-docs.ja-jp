---
title: _getche_nolock、_getwche_nolock
ms.date: 4/2/2020
api_name:
- _getche_nolock
- _getwche_nolock
- _o__getche_nolock
- _o__getwche_nolock
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getche_nolock
- _gettche_nolock
- _getwche_nolock
- getche_nolock
- getwche_nolock
- gettche_nolock
helpviewer_keywords:
- characters, getting from console
- _gettche_nolock function
- getwche_nolock function
- _getche_nolock function
- getche_nolock function
- console, reading from
- _getwche_nolock function
- gettche_nolock function
ms.assetid: 9e853ad4-4d8a-4442-9ae5-da4b434f0b8c
ms.openlocfilehash: 901c823d2e6539d7c07e3521c5d372b7816eb9b8
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910758"
---
# <a name="_getche_nolock-_getwche_nolock"></a>_getche_nolock、_getwche_nolock

エコーありで、スレッドはロックしないで、コンソールから文字を取得します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _getche_nolock( void );
wint_t _getwche_nolock( void );
```

## <a name="return-value"></a>戻り値

読み取られた文字を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

**_getche_nolock**と **_getwche_nolock**は **_getche**および **_getwche**と同じですが、他のスレッドによる干渉から保護されていない点が異なります。 他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettche_nolock**|**_getche_nolock**|**_getch_nolock**|**_getwche_nolock**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_getche_nolock**|\<conio.h>|
|**_getwche_nolock**|\<conio.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_getche_nolock.c
// compile with: /c
// This program reads characters from
// the keyboard until it receives a 'Y' or 'y'.

#include <conio.h>
#include <ctype.h>

int main( void )
{
   int ch;

   _cputs( "Type 'Y' when finished typing keys: " );
   do
   {
      ch = _getche_nolock();
      ch = toupper( ch );
   } while( ch != 'Y' );

   _putch_nolock( ch );
   _putch_nolock( '\r' );    // Carriage return
   _putch_nolock( '\n' );    // Line feed
}
```

```Input
abcdefy
```

```Output
Type 'Y' when finished typing keys: abcdefyY
```

## <a name="see-also"></a>関連項目

[コンソール入出力とポート入出力](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cgets、_cgetws](../../c-runtime-library/cgets-cgetws.md)<br/>
[getc、getwc](getc-getwc.md)<br/>
[_ungetch、_ungetwch、_ungetch_nolock、_ungetwch_nolock](ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
