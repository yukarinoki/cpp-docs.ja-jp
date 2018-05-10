---
title: tmpnam_s、_wtmpnam_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- tmpnam_s
- _wtmpnam_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
dev_langs:
- C++
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8c6298c7b66c8967a4e5e23a37c3614edcddf3d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s、_wtmpnam_s

一時ファイルの作成に使用できる名前を生成します。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) の説明にあるとおり、セキュリティが強化されたバージョンの [tmpnam および _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) です。

## <a name="syntax"></a>構文

```C
errno_t tmpnam_s(
   char * str,
   size_t sizeInChars
);
errno_t _wtmpnam_s(
   wchar_t *str,
   size_t sizeInChars
);
template <size_t size>
errno_t tmpnam_s(
   char (&str)[size]
); // C++ only
template <size_t size>
errno_t _wtmpnam_s(
   wchar_t (&str)[size]
); // C++ only
```

### <a name="parameters"></a>パラメーター

*str*<br/>
生成された名前を保持するポインター。

*sizeInChars*<br/>
バッファーのサイズ (文字単位)。

## <a name="return-value"></a>戻り値

これらの関数はどちらも、正常終了の場合は 0、エラーの場合はエラー番号を返します。

### <a name="error-conditions"></a>エラー条件

|||||
|-|-|-|-|
|*str*|*sizeInChars*|**戻り値**|**内容***str* |
|**NULL**|任意|**EINVAL**|変更されない|
|いない**NULL** (有効なメモリが指す)|短すぎる|**ERANGE**|変更されない|

場合*str*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**返す**EINVAL**です。

## <a name="remarks"></a>コメント

これらの各関数は、現在存在しないファイルの名前を返します。 **tmpnam_s**名を返します。 現在の作業ディレクトリ内で一意です。 ファイル名の前に円記号が付いていてパス情報がない場合 (\fname21 など)、その名前は現在の作業ディレクトリに対して有効なので注意してください。

**Tmpnam_s**でこの生成されたファイル名を格納する*str*です。 によって返される文字列の最大長**tmpnam_s**は**L_tmpnam_s**STDIO で定義されている。H. 場合*str*は**NULL**、し**tmpnam_s**内部の静的バッファーに、結果を残します。 したがって後続の呼び出しは、この値を破棄します。 によって生成された名前**tmpnam_s**プログラムで生成されたファイル名と後の最初の呼び出しで構成されています**tmpnam_s**、基本 32 の連続する番号のファイル拡張子 (.1 .1vvvvvu、when **TMP_MAX_S** STDIO にします。H は**INT_MAX**)。

**tmpnam_s** OEM コード ページに基づいてマルチバイト文字のシーケンスを認識し、必要に応じてハンドル マルチバイト文字の文字列の引数が、オペレーティング システムから自動的に取得します。 **_wtmpnam_s**のワイド文字バージョンは、 **tmpnam_s**; の引数と戻り値 **_wtmpnam_s**ワイド文字列です。 **_wtmpnam_s**と**tmpnam_s**という点以外の動作は同じ **_wtmpnam_s**マルチバイト文字の文字列を処理しません。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam_s**|**tmpnam_s**|**tmpnam_s**|**_wtmpnam_s**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**tmpnam_s**|\<stdio.h>|
|**_wtmpnam_s**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_tmpnam_s.c
// This program uses tmpnam_s to create a unique filename in the
// current working directory.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char name1[L_tmpnam_s];
   errno_t err;
   int i;

   for (i = 0; i < 15; i++)
   {
      err = tmpnam_s( name1, L_tmpnam_s );
      if (err)
      {
         printf("Error occurred creating unique filename.\n");
         exit(1);
      }
      else
      {
         printf( "%s is safe to use as a temporary file.\n", name1 );
      }
   }
}
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
