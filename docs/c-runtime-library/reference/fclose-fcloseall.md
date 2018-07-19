---
title: fclose、_fcloseall | Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71b98a239cd1a6504611bf436533e7b5fbe1302c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32400240"
---
# <a name="fclose-fcloseall"></a>fclose、_fcloseall

ストリームを閉じます (**fclose**) または開いているすべてのストリームを閉じる (**_fcloseall**)。

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

**fclose**ストリームが正常に閉じられた場合は 0 を返します。 **_fcloseall**閉じられたストリームの合計数を返します。 どちらの関数が返す**EOF**はエラーを示します。

## <a name="remarks"></a>コメント

**Fclose**関数の閉じ*ストリーム*です。 場合*ストリーム*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**fclose**設定**errno**に**EINVAL**し、返します**EOF**です。 推奨、*ストリーム*常にポインターがこの関数を呼び出す前にチェックします。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

**_Fcloseall**関数は除く、開いているすべてのストリームをクローズ**stdin**、 **stdout**、 **stderr** (および、MS-DOS、 **_stdaux**と **_stdprn**)。 また、閉じ、によって作成された一時ファイルを削除**tmpfile**です。 両方の関数では、終了する前に、ストリームに関連付けられているすべてのバッファーがフラッシュされます。 システムによって割り当てられたバッファーについては、ストリームを閉じる際に解放します。 持つユーザーによって割り当てられたバッファー **setbuf**と**setvbuf**は自動的に解放されません。

**注:** これらの関数を使用してストリームを閉じる場合は、ストリームだけでなく基になるファイル記述子と OS ファイル ハンドル (またはソケット) も閉じられます。 したがって、ファイルが最初に開いた場合、ファイルとして処理ファイル記述子やを閉じるには**fclose**、呼び出しではないも **_close**をファイル記述子を閉じる以外の場合は、Win32 関数を呼び出す必要はありません**CloseHandle**ファイル ハンドルを閉じることです。

**fclose**と **_fcloseall**他のスレッドによる干渉から保護するコードを追加します。 ロックしないバージョンの**fclose**を参照してください **_fclose_nolock**です。

## <a name="requirements"></a>要件

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
