---
title: fclose、_fcloseall
ms.date: 4/2/2020
api_name:
- fclose
- _fcloseall
- _o__fcloseall
- _o_fclose
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: b2ee14c5fc8bb47cc2652443c0263bd14147c90d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347491"
---
# <a name="fclose-_fcloseall"></a>fclose、_fcloseall

ストリームを閉じる (**fclose**) か、開いているすべてのストリーム (**_fcloseall**) を閉じます。

## <a name="syntax"></a>構文

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fclose**は、ストリームが正常に閉じられた場合は 0 を返します。 **_fcloseall**は、終了したストリームの合計数を返します。 どちらの関数も**EOF**を返してエラーを示します。

## <a name="remarks"></a>解説

**fclose**関数は*ストリーム*を閉じます。 *stream*が**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合は **、fclose**は**errno**を**EINVAL**に設定し **、EOF**を返します。 この関数を呼び出す前に、*ストリーム*ポインターを常にチェックすることをお勧めします。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

**_fcloseall**関数は **、stdin** **、stdout** **、stderr** (および MS-DOS、_stdaux、_stdprn)**_stdprn**を除くすべてのオープンストリームを閉じます。 **_stdaux** また **、tmpfile**で作成された一時ファイルを閉じて削除します。 両方の関数では、終了する前に、ストリームに関連付けられているすべてのバッファーがフラッシュされます。 システムによって割り当てられたバッファーについては、ストリームを閉じる際に解放します。 ユーザーが**setbuf**および**setvbuf**を使用して割り当てたバッファは、自動的には解放されません。

**注:** これらの関数を使用してストリームを閉じる場合は、ストリームだけでなく基になるファイル記述子と OS ファイル ハンドル (またはソケット) も閉じられます。 したがって、ファイルが最初にファイルハンドルまたはファイル記述子としてオープンされ、 **fclose**で閉じられている場合は、 **_close**を呼び出してファイル記述子を閉じないでください。Win32 関数を呼び出さない**CloseHandle**ファイル ハンドルを閉じます。

**fclose**と **_fcloseall**他のスレッドからの干渉から保護するコードが含まれています。 **fclose**のロックなしのバージョンについては **、「_fclose_nolock」** を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
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
