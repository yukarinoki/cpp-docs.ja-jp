---
title: fclose、_fcloseall
ms.date: 11/04/2016
apiname:
- fclose
- _fcloseall
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
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: 4713ffb7ecdf8da73e5f949bbef7be124dfaf28a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334880"
---
# <a name="fclose-fcloseall"></a>fclose、_fcloseall

ストリームを閉じます (**fclose**) またはすべての開いているストリームを閉じる (**_fcloseall**)。

## <a name="syntax"></a>構文

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>パラメーター

*stream*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fclose**ストリームが正常に閉じられた場合は 0 を返します。 **_fcloseall**閉じられたストリームの合計数を返します。 どちらの関数が返す**EOF**はエラーを示します。

## <a name="remarks"></a>Remarks

**Fclose**関数の閉じ*ストリーム*します。 場合*ストリーム*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**fclose**設定**errno**に**EINVAL**返します**EOF**します。 推奨されます、*ストリーム*常にポインターがこの関数を呼び出す前にチェックされます。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

**_Fcloseall**関数を除くすべての開いているストリームを閉じます**stdin**、 **stdout**、 **stderr** (および、MS-DOS、 **_stdaux**と **_stdprn**)。 また終了し、によって作成された一時ファイルを削除します。 **tmpfile**します。 両方の関数では、終了する前に、ストリームに関連付けられているすべてのバッファーがフラッシュされます。 システムによって割り当てられたバッファーについては、ストリームを閉じる際に解放します。 持つユーザーによって割り当てられたバッファー **setbuf**と**setvbuf**は自動的に解放されません。

**注:** ストリームを閉じるようにこれらの関数を使用している場合、基になるファイル記述子と OS ファイル ハンドル (またはソケット) は閉じられます、およびストリーム。 そのため、ファイルが最初に開かれている場合、ファイルとして処理ファイル記述子やを閉じるには**fclose**、呼び出し **_close**にファイル記述子を閉じます Win32 関数を呼び出さないでください **。CloseHandle**ファイル ハンドルを閉じます。

**fclose**と **_fcloseall**他のスレッドによる干渉から保護するためのコードが含まれます。 ロックしないバージョンの**fclose**を参照してください **_fclose_nolock**します。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fclose**|\<stdio.h>|
|**_fcloseall**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[fopen](fopen-wfopen.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen、_wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[freopen、_wfreopen](freopen-wfreopen.md)<br/>
