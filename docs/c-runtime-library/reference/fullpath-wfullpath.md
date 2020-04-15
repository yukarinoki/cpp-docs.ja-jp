---
title: _fullpath、_wfullpath
ms.date: 4/2/2020
api_name:
- _fullpath
- _wfullpath
- _o__fullpath
- _o__wfullpath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wfullpath
- fullpath
- _wfullpath
- _fullpath
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
ms.openlocfilehash: 0910cf4f39e00be84e683cd6f3b9afbeb3f2a749
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345483"
---
# <a name="_fullpath-_wfullpath"></a>_fullpath、_wfullpath

指定された相対パス名の絶対または完全パス名を作成します。

## <a name="syntax"></a>構文

```C
char *_fullpath(
   char *absPath,
   const char *relPath,
   size_t maxLength
);
wchar_t *_wfullpath(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength
);
```

### <a name="parameters"></a>パラメーター

*アブスパス*<br/>
絶対パス名または絶対パス名、または**NULL**を含むバッファーへのポインター。

*レルパス*<br/>
相対パス名。

*maxLength*<br/>
絶対パス名バッファーの最大長 (*absPath*)。 この長さは **_fullpath**の場合はバイト単位ですが **、_wfullpath**の場合はワイド文字 (**wchar_t**) で指定します。

## <a name="return-value"></a>戻り値

これらの関数は、絶対パス名 (*absPath*) を含むバッファへのポインタを返します。 エラーが発生した場合 (たとえば *、relPath*に渡された値に無効なドライブ文字が含まれているか、または見つからない場合、または作成された絶対パス名 (*absPath*) の長さが*maxLength*より大きい場合は、関数は**NULL**を返します。

## <a name="remarks"></a>解説

**_fullpath**関数は*relPath*の相対パス名を絶対パスまたは絶対パスに展開し、その名前を*absPath*に格納します。 *absPath*が**NULL**の場合 **、malloc**はパス名を保持するのに十分な長さのバッファーを割り振るために使用されます。 このバッファーを解放するのは、呼び出し元の役目です。 相対パス名は、現在の場所から別の場所 (現在の作業ディレクトリ "." など) にパスを指定します。 絶対パス名は、ファイル システムのルートから目的の位置に到達するために必要なパス全体を示す相対パス名の拡張です。 **_makepath**とは異なり **、_fullpath**を使用して、相対パス (*relPath*) の絶対パス名を取得できます。/" 彼らの名前で。

たとえば、C ランタイム ルーチンを使用するには、アプリケーションに、ルーチンの宣言を含むヘッダー ファイルを含める必要があります。 各ヘッダー ファイルは、(アプリケーションの作業ディレクトリから) 相対的な方法でファイルの場所を参照するステートメントを含んでいます。

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <stdlib.h>
```

ファイルの絶対パス (実際のファイル システムの場所) は次のようになります。

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath**は、マルチバイト文字の文字列引数を適切に処理し、現在使用中のマルチバイトコードページに従ってマルチバイト文字シーケンスを認識します。 **_wfullpath**はワイド文字の **_fullpath**です。_wfullpath**する文字列**引数はワイド文字列です。 **_wfullpath**と **_fullpath**は、マルチバイト文字の文字列**を**扱わないという点を除いて、同じように動作_wfullpath。

**_DEBUG**と **_CRTDBG_MAP_ALLOC**の両方が定義されている場合 **、_fullpath**と **_wfullpath**の呼び出しは **、_fullpath_dbg**への呼び出しによって置き換えられ、メモリ割り当てのデバッグを可能にする **_wfullpath_dbg。** 詳細については、「[_fullpath_dbg、_wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md)」を参照してください。

この関数は *、maxlen*が 0 以下の場合に、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、この関数は**errno**を**EINVAL**に設定し **、NULL**を返します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

*absPath*バッファーが**NULL**の場合 **、_fullpath**は[malloc](malloc.md)を呼び出してバッファーを割り当て *、maxLength*引数を無視します。 このバッファーを ([free](free.md) を使用して) 適切に解放するのは、呼び出し元の責任です。 *relPath*引数にディスク ドライブを指定すると、このドライブの現在のディレクトリがパスと結合されます。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h>|
|**_wfullpath**|\<stdlib.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_fullpath.c
// This program demonstrates how _fullpath
// creates a full path from a partial path.

#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <direct.h>

void PrintFullPath( char * partialPath )
{
   char full[_MAX_PATH];
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )
      printf( "Full path is: %s\n", full );
   else
      printf( "Invalid path\n" );
}

int main( void )
{
   PrintFullPath( "test" );
   PrintFullPath( "\\test" );
   PrintFullPath( "..\\test" );
}
```

```Output
Full path is: C:\Documents and Settings\user\My Documents\test
Full path is: C:\test
Full path is: C:\Documents and Settings\user\test
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_getcwd、_wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd、_wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath、_wmakepath](makepath-wmakepath.md)<br/>
[_splitpath、_wsplitpath](splitpath-wsplitpath.md)<br/>
