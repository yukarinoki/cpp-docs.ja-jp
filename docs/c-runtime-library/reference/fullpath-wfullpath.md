---
description: '詳細については、次を参照してください: _fullpath、_wfullpath'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: e9c02d100abc175f24194ce71627502544085f9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334153"
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

*absPath*<br/>
絶対パス名または完全パス名を格納しているバッファーへのポインター、または **NULL**。

*relPath*<br/>
相対パス名。

*maxLength*<br/>
絶対パス名バッファー (*Abspath*) の最大長。 この長さは、 **_fullpath** の場合はバイト単位ですが、 **`wchar_t`** **_wfullpath** の場合はワイド文字 () になります。

## <a name="return-value"></a>戻り値

これらの各関数は、絶対パス名 (*Abspath*) を格納しているバッファーへのポインターを返します。 エラーが発生した場合 (たとえば、 *relPath* に渡された値に有効でないドライブ文字が含まれている場合や、見つからない場合、または作成された絶対パス名 (*abspath*) の長さが *maxLength* を超える場合)、関数は **NULL** を返します。

## <a name="remarks"></a>解説

**_Fullpath** 関数は、 *relPath* の相対パス名を完全修飾パスまたは絶対パスに展開し、この名前を *abspath* に格納します。 *Abspath* が **NULL** の場合、 **malloc** は、パス名を保持するのに十分な長さのバッファーを割り当てるために使用されます。 このバッファーを解放するのは、呼び出し元の役目です。 相対パス名は、現在の場所から別の場所 (現在の作業ディレクトリ "." など) にパスを指定します。 絶対パス名は、ファイル システムのルートから目的の位置に到達するために必要なパス全体を示す相対パス名の拡張です。 **_Makepath** とは異なり、 **_fullpath** を使用して、"./" または "." を含む相対パス (*relPath*) の絶対パス名を取得できます。/"という名前です。

たとえば、C ランタイム ルーチンを使用するには、アプリケーションに、ルーチンの宣言を含むヘッダー ファイルを含める必要があります。 各ヘッダー ファイルは、(アプリケーションの作業ディレクトリから) 相対的な方法でファイルの場所を参照するステートメントを含んでいます。

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <stdlib.h>
```

ファイルの絶対パス (実際のファイル システムの場所) は次のようになります。

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** は、現在使用されているマルチバイトコードページに従ってマルチバイト文字シーケンスを認識し、マルチバイト文字列の引数を適切な方法で自動的に処理します。 **_wfullpath** は **_fullpath** のワイド文字バージョンです。 **_wfullpath** する文字列引数はワイド文字列です。 **_wfullpath** と **_fullpath** は、 **_wfullpath** がマルチバイト文字列を処理しない点を除き、同じように動作します。

**_DEBUG** と **_CRTDBG_MAP_ALLOC** の両方が定義されている場合、 **_fullpath** と **_wfullpath** への呼び出しは、メモリ割り当てのデバッグを可能にするために **_fullpath_dbg** と **_wfullpath_dbg** の呼び出しに置き換えられます。 詳細については、「[_fullpath_dbg、_wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md)」を参照してください。

この関数は、「 [パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、" *maxlen* " が0以下の場合に、無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、この関数は **errno** を **EINVAL** に設定し、 **NULL** を返します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

*Abspath* バッファーが **NULL** の場合、 **_fullpath** は [malloc](malloc.md)を呼び出してバッファーを割り当て、 *maxLength* 引数を無視します。 このバッファーを ([free](free.md) を使用して) 適切に解放するのは、呼び出し元の責任です。 *RelPath* 引数にディスクドライブが指定されている場合、このドライブの現在のディレクトリがパスと結合されます。

## <a name="requirements"></a>要件

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

[ファイルの処理](../../c-runtime-library/file-handling.md)<br/>
[_getcwd、_wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd、_wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath、_wmakepath](makepath-wmakepath.md)<br/>
[_splitpath、_wsplitpath](splitpath-wsplitpath.md)<br/>
