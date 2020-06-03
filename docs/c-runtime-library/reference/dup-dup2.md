---
title: _dup、_dup2
ms.date: 4/2/2020
api_name:
- _dup
- _dup2
- _o__dup
- _o__dup2
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _dup2
- _dup
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
ms.openlocfilehash: 6c635930fdbc8da550a2a32ea614e150fbeb08a8
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915210"
---
# <a name="_dup-_dup2"></a>_dup、_dup2

開いているファイル (**_dup**) の2番目のファイル記述子を作成するか、ファイル記述子 (**_dup2**) を再割り当てします。

## <a name="syntax"></a>構文

```C
int _dup( int fd );
int _dup2( int fd1, int fd2 );
```

### <a name="parameters"></a>パラメーター

*fd*、 *fd1*<br/>
開いているファイルを参照するファイル記述子。

*fd2*<br/>
任意のファイル記述子。

## <a name="return-value"></a>戻り値

**_dup**は新しいファイル記述子を返します。 成功を示すには **_dup2** 0 を返します。 エラーが発生した場合、各関数は-1 を返し、ファイル記述子が無効で**ある場合は** **errno**に、ファイル記述子が使用できない場合は**EMFILE**に設定します。 ファイル記述子が無効な場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、関数によって無効なパラメーター ハンドラーも開始されます。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Dup**関数と **_dup2**関数は、2番目のファイル記述子を現在開いているファイルに関連付けます。 これらの関数を使用すると、 **stdout**などの定義済みのファイル記述子を別のファイルに関連付けることができます。 ファイル操作はいずれかのファイル記述子を使用して実行できます。 新しい記述子の作成によって、ファイルに対するアクセス権の種類が影響を受けることはありません。 **_dup**は、指定されたファイルに対して次に使用できるファイル記述子を返します。 **_dup2**は、 *fd2*が*fd1*と同じファイルを参照するように強制します。 呼び出し時に*fd2*が開いているファイルに関連付けられている場合、そのファイルは閉じています。

**_Dup**と **_dup2**はどちらもファイル記述子をパラメーターとして受け取ります。 これらの関数のいずれ`FILE *`かにストリーム () を渡すには、 [_fileno](fileno.md)を使用します。 **Fileno**ルーチンは、指定されたストリームに現在関連付けられているファイル記述子を返します。 次の例は、 **stderr**にとし`FILE *`て定義されている stderr をファイル記述子と関連付ける方法を示しています。

```C
int cstderr = _dup( _fileno( stderr ));
```

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_dup**|\<io.h>|
|**_dup2**|\<io.h>|

コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリではサポートされていません。 コンソール、 **stdin**、 **stdout**、および**stderr**に関連付けられている標準ストリームハンドルは、C ランタイム関数が UWP アプリで使用できるようになる前にリダイレクトする必要があります。 互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_dup.c
// This program uses the variable old to save
// the original stdout. It then opens a new file named
// DataFile and forces stdout to refer to it. Finally, it
// restores stdout to its original state.

#include <io.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int old;
   FILE *DataFile;

   old = _dup( 1 );   // "old" now refers to "stdout"
                      // Note:  file descriptor 1 == "stdout"
   if( old == -1 )
   {
      perror( "_dup( 1 ) failure" );
      exit( 1 );
   }
   _write( old, "This goes to stdout first\n", 26 );
   if( fopen_s( &DataFile, "data", "w" ) != 0 )
   {
      puts( "Can't open file 'data'\n" );
      exit( 1 );
   }

   // stdout now refers to file "data"
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )
   {
      perror( "Can't _dup2 stdout" );
      exit( 1 );
   }
   puts( "This goes to file 'data'\n" );

   // Flush stdout stream buffer so it goes to correct file
   fflush( stdout );
   fclose( DataFile );

   // Restore original stdout
   _dup2( old, 1 );
   puts( "This goes to stdout\n" );
   puts( "The file 'data' contains:" );
   _flushall();
   system( "type data" );
}
```

```Output
This goes to stdout first
This goes to stdout

The file 'data' contains:
This goes to file 'data'
```

## <a name="see-also"></a>関連項目

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
