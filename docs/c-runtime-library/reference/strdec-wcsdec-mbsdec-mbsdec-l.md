---
description: '詳細については、次を参照してください: _strdec、_wcsdec、_mbsdec、_mbsdec_l'
title: _strdec、_wcsdec、_mbsdec、_mbsdec_l
ms.date: 4/2/2020
api_name:
- _wcsdec
- _strdec
- _mbsdec
- _mbsdec_l
- _o__mbsdec
- _o__mbsdec_l
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
- _strdec
- mbsdec_l
- strdec
- _mbsdec
- _mbsdec_l
- mbsdec
- wcsdec
- _wcsdec
helpviewer_keywords:
- mbsdec_l function
- mbsdec function
- tcsdec function
- _tcsdec function
- _strdec function
- _wcsdec function
- _mbsdec_l function
- strdec function
- wcsdec function
- _mbsdec function
ms.assetid: ae37c223-800f-48a9-ae8e-38c8d20af2dd
ms.openlocfilehash: 85001258baea9e7c6509bfdd33a74f9a0eccd80f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340555"
---
# <a name="_strdec-_wcsdec-_mbsdec-_mbsdec_l"></a>_strdec、_wcsdec、_mbsdec、_mbsdec_l

文字列ポインターを 1 文字前へ移動します。

> [!IMPORTANT]
> **mbsdec** と **mbsdec_l** は、Windows ランタイムで実行されるアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned char *_strdec(
   const unsigned char *start,
   const unsigned char *current
);
unsigned wchar_t *_wcsdec(
   const unsigned wchar_t *start,
   const unsigned wchar_t *current
);
unsigned char *_mbsdec(
   const unsigned char *start,
   const unsigned char *current
);
unsigned char *_mbsdec_l(
   const unsigned char *start,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*start*<br/>
ソース文字列内の任意の文字 (または、 **_mbsdec** と **_mbsdec_l** の場合は、マルチバイト文字の最初のバイト) へのポインター。ソース *文字列の先頭の前に**開始* する必要があります。

*現在の*<br/>
ソース文字列内の任意の文字 (または、 **_mbsdec** と **_mbsdec_l** の場合は、マルチバイト文字の最初のバイト) へのポインター。 *現在* の位置は、ソース文字列の *先頭* に続く必要があります。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_mbsdec**、 **_mbsdec_l**、 **_strdec**、および **_wcsdec** はそれぞれ、*現在の* 直前の文字へのポインターを返します。*start* の値が *現在* のの値以上の場合、 **_mbsdec** は **NULL** を返します。 **_tcsdec** は、これらの関数のいずれかにマップされ、戻り値はマッピングによって異なります。

## <a name="remarks"></a>解説

**_Mbsdec** 関数と **_mbsdec_l** 関数は、 *start* を含む文字列の *現在* の直前にあるマルチバイト文字の最初のバイトへのポインターを返します。

出力値は、ロケールの **LC_CTYPE** カテゴリの設定に影響されます。詳細について [は、「setlocale、_wsetlocale](setlocale-wsetlocale.md) 」を参照してください。  **_mbsdec** は、現在使用されているロケールに従ってマルチバイト文字のシーケンスを認識しますが、 **_mbsdec_l** は、渡されたロケールパラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*Start* または *current* が **NULL** の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は **einval** を返し、 **errno** を **einval** に設定します。

> [!IMPORTANT]
> これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。 バッファー オーバーランは、認められていない特権の昇格の原因となるため、システムの攻撃に使用される可能性があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsdec**|**_strdec**|**_mbsdec**|**_wcsdec**|

**_strdec** と **_wcsdec** は、 **_mbsdec** と **_mbsdec_l** の1バイト文字とワイド文字バージョンです。 **_strdec** と **_wcsdec** はこのマッピングに対してのみ提供され、それ以外の場合は使用できません。

詳細については、「[Using Generic-Text Mappings](../../c-runtime-library/using-generic-text-mappings.md)」(汎用テキスト マップの使用) および「[Generic-Text Mappings](../../c-runtime-library/generic-text-mappings.md)」(汎用テキスト マップ) をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_mbsdec**|\<mbstring.h>|\<mbctype.h>|
|**_mbsdec_l**|\<mbstring.h>|\<mbctype.h>|
|**_strdec**|\<tchar.h>||
|**_wcsdec**|\<tchar.h>||

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

次の例は、 **_tcsdec** の使用方法を示しています。

```cpp
// crt_tcsdec.cpp
// Compile by using: cl /EHsc crt_tcsdec.cpp
#include <iostream>
#include <tchar.h>
using namespace std;

int main()
{
   const TCHAR *str = _T("12345");
   cout << "str: " << str << endl;

   const TCHAR *str2;
   str2 = str + 2;
   cout << "str2: " << str2 << endl;

   TCHAR *answer;
   answer = _tcsdec( str, str2 );
   cout << "answer: " << answer << endl;

   return (0);
}
```

次の例は、 **_mbsdec** の使用方法を示しています。

```cpp
// crt_mbsdec.cpp
// Compile by using: cl /EHsc crt_mbsdec.c
#include <iostream>
#include <mbstring.h>
using namespace std;

int main()
{
   char *str = "12345";
   cout << "str: " << str << endl;

   char *str2;
   str2 = str + 2;
   cout << "str2: " << str2 << endl;

   unsigned char *answer;
   answer = _mbsdec( reinterpret_cast<unsigned char *>( str ), reinterpret_cast<unsigned char *>( str2 ));

   cout << "answer: " << answer << endl;

   return (0);
}
```

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strinc、_wcsinc、_mbsinc、_mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strnextc、_wcsnextc、_mbsnextc、_mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc、_wcsninc、_mbsninc、_mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
