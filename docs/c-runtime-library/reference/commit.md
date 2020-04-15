---
title: _commit
ms.date: 4/2/2020
api_name:
- _commit
- _o__commit
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
- _commit
- commit
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
ms.openlocfilehash: f8e13e7fc197c66395556d518ecbd1cd20ac1f77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348625"
---
# <a name="_commit"></a>_commit

ファイルを直接ディスクにフラッシュします。

## <a name="syntax"></a>構文

```C
int _commit(
   int fd
);
```

### <a name="parameters"></a>パラメーター

*Fd*<br/>
開いているファイルを参照するファイル記述子。

## <a name="return-value"></a>戻り値

**_commitファイル**がディスクに正常にフラッシュされた場合は 0 を返します。 戻り値 -1 はエラーを示します。

## <a name="remarks"></a>解説

**_commit**機能により、オペレーティング・システムは *、fd*に関連付けられたファイルをディスクに書き込みます。 この関数を呼び出すと、オペレーティング システムのタイミングではなく、即時に指定したファイルがフラッシュされます。

*fd*が無効なファイル記述子である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は -1 を返し **、errno**は**EBADF**に設定されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**_commit**|\<io.h>|\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_write](write.md)<br/>
