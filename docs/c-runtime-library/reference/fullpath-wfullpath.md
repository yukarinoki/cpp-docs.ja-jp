---
title: _fullpath、_wfullpath | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fullpath
- _wfullpath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wfullpath
- fullpath
- _wfullpath
- _fullpath
dev_langs:
- C++
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b472987b0cac41c57e5fd22b2eedecef522613b4
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451681"
---
# <a name="fullpath-wfullpath"></a>_fullpath、_wfullpath

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

*absPath*<br/>
絶対または完全パス名を格納するバッファーへのポインターまたは**NULL**です。

*relPath*<br/>
相対パス名。

*maxLength*<br/>
絶対パス名のバッファーの最大長 (*absPath*)。 この長さはバイト単位、 **_fullpath**がワイド文字 (**wchar_t**) の **_wfullpath**です。

## <a name="return-value"></a>戻り値

絶対パス名を格納するバッファーへのポインターを返しますこれらの関数 (*absPath*)。 エラーがある場合 (値が渡された場合など、 *relPath*が無効または見つからないドライブ文字が含まれる場合、または作成された絶対パス名の長さ (*absPath*) より大きい*maxLength*)、この関数を返します**NULL**です。

## <a name="remarks"></a>コメント

**_Fullpath**関数は、相対パス名で、展開*relPath*を完全修飾パスまたは絶対パスとストアの名前をこの*absPath*です。 場合*absPath*は**NULL**、 **malloc**パス名を保持するために十分な長さのバッファーを割り当てるために使用します。 このバッファーを解放するのは、呼び出し元の役目です。 相対パス名は、現在の場所から別の場所 (現在の作業ディレクトリ "." など) にパスを指定します。 絶対パス名は、ファイル システムのルートから目的の位置に到達するために必要なパス全体を示す相対パス名の拡張です。 異なり **_makepath**、 **_fullpath**相対パスの絶対パス名を取得するために使用できます (*relPath*) が含まれる"./「または」../"、名前にします。

たとえば、C ランタイム ルーチンを使用するには、アプリケーションに、ルーチンの宣言を含むヘッダー ファイルを含める必要があります。 各ヘッダー ファイルは、(アプリケーションの作業ディレクトリから) 相対的な方法でファイルの場所を参照するステートメントを含んでいます。

```C
#include <stdlib.h>
```

ファイルの絶対パス (実際のファイル システムの場所) は次のようになります。

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath**自動的に現在使用中のマルチバイト コード ページに基づいてマルチバイト文字シーケンスを認識し、必要に応じてマルチバイト文字の文字列引数を処理します。 **_wfullpath**のワイド文字バージョンは、 **_fullpath**; 文字列引数を **_wfullpath**ワイド文字列です。 **_wfullpath**と **_fullpath**という点以外の動作は同じ **_wfullpath**マルチバイト文字の文字列を処理しません。

場合 **_DEBUG**と **_CRTDBG_MAP_ALLOC**は両方とも、定義への呼び出し **_fullpath**と **_wfullpath** への呼び出しによって置き換えられます **_fullpath_dbg**と **_wfullpath_dbg**メモリ割り当てをデバッグできるようにします。 詳細については、「[_fullpath_dbg、_wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md)」を参照してください。

」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)場合は、 *maxlen*が 0 未満です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、返します**NULL**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

場合、 *absPath*バッファーが**NULL**、 **_fullpath**呼び出し[malloc](malloc.md)バッファーを割り当てることを無視し、 *maxLength*引数。 このバッファーを ([free](free.md) を使用して) 適切に解放するのは、呼び出し元の責任です。 場合、 *relPath*引数には、ディスク ドライブが指定します、このドライブの現在のディレクトリがパスに結合します。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h>|
|**_wfullpath**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
