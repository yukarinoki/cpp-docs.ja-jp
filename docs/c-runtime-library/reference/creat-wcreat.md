---
description: '詳細については、次を参照してください: _creat、_wcreat'
title: _creat、_wcreat
ms.date: 4/2/2020
api_name:
- _creat
- _wcreat
- _o__creat
- _o__wcreat
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
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
ms.openlocfilehash: 716f0d11af408ba30cb91744fd770300272dc26b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269043"
---
# <a name="_creat-_wcreat"></a>_creat、_wcreat

新しいファイルを 1 つ作成します。 **_creat** と **_wcreat** は非推奨とされました。代わりに [、_sopen_s、_wsopen_s](sopen-s-wsopen-s.md) を使用してください。

## <a name="syntax"></a>構文

```C
int _creat(
   const char *filename,
   int pmode
);
int _wcreat(
   const wchar_t *filename,
   int pmode
);
```

### <a name="parameters"></a>パラメーター

*filename*<br/>
新しいファイルの名前。

*pmode*<br/>
アクセス許可の設定。

## <a name="return-value"></a>戻り値

これらの関数は正常に実行された場合、作成されたファイルにファイル記述子を返します。 それ以外の場合、次の表に示すように、関数は-1 を返し、 **errno** を設定します。

|**errno** の設定|説明|
|---------------------|-----------------|
|**EACCES**|*filename* には、既存の読み取り専用ファイルを指定するか、ファイルの代わりにディレクトリを指定します。|
|**EMFILE**|ファイル記述子をこれ以上使用できません。|
|**ENOENT**|指定されたファイルが見つかりませんでした。|

*Filename* が **NULL** の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は **errno** を **EINVAL** に設定し、-1 を返します。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Creat** 関数は、新しいファイルを作成するか、既存のファイルを開き、切り捨てます。 **_wcreat** は **_creat** のワイド文字バージョンです。**_wcreat** する *filename* 引数は、ワイド文字列です。 **_wcreat** と **_creat** は同じように動作します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

*Filename* によって指定されたファイルが存在しない場合は、指定されたアクセス許可の設定で新しいファイルが作成され、書き込み用に開かれます。 ファイルが既に存在し、そのアクセス許可設定によって書き込みが許可されている場合、 **_creat** は、ファイルを長さ0に切り詰め、前の内容を破棄して、書き込み用に開きます。 アクセス許可の設定である *pmode* は、新しく作成されたファイルにのみ適用されます。 新しいファイルは、最初に閉じた後に、指定されたアクセス許可設定を受け取ります。 整数式には、マニフェスト定数 **_S_IWRITE** と **_S_IREAD** の一方または両方が含ま *れてい* ます。 両方の定数が指定されている場合は、ビットごとの or 演算子 ( **&#124;** ) と結合されます。 *Pmode* パラメーターは、次のいずれかの値に設定されます。

|値|定義|
|-----------|----------------|
|**_S_IWRITE**|書き込みが許可されます。|
|**_S_IREAD**|読み取りが許可されます。|
|**_S_IREAD** &#124; **_S_IWRITE**|読み取りと書き込みが許可されます。|

書き込みアクセス許可が与えられない場合、ファイルは読み取り専用になります。 ファイルはすべて常に読み取り可能です。書き込みのみのアクセス許可を与えることはできません。 これらのモード **_S_IWRITE** と **_S_IREAD**  |  **_S_IWRITE** は同等です。 **_Creat** を使用して開いたファイルは、 **_SH_DENYNO** で常に互換モード ( [_sopen](sopen-wsopen.md)を参照) で開かれます。

**_creat** は、アクセス許可を設定する前に、現在のファイルアクセス許可マスクを *pmode* に適用します ( [_umask](umask.md)を参照してください)。 **_creat** は、主に以前のライブラリとの互換性のために用意されています。 *Oflag* パラメーターで **_O_CREAT** と **_O_TRUNC** を使用した **_open** の呼び出しは、 **_creat** と同じであり、新しいコードに適しています。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wcreat**|\<io.h> または \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_creat.c
// compile with: /W3
// This program uses _creat to create
// the file (or truncate the existing file)
// named data and open it for writing.

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int fh;

   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996
   // Note: _creat is deprecated; use _sopen_s instead
   if( fh == -1 )
      perror( "Couldn't create data file" );
   else
   {
      printf( "Created data file.\n" );
      _close( fh );
   }
}
```

```Output
Created data file.
```

## <a name="see-also"></a>関連項目

[低レベル i/o](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod、_wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup、_dup2](dup-dup2.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_sopen、_wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>
