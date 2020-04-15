---
title: _close
ms.date: 4/2/2020
api_name:
- _close
- _o__close
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
- _close
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
ms.openlocfilehash: 4d8b702a10624ae80629b4ce4644c428322500cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348641"
---
# <a name="_close"></a>_close

ファイルを閉じます。

## <a name="syntax"></a>構文

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>パラメーター

*Fd*<br/>
開いているファイルを参照するファイル記述子。

## <a name="return-value"></a>戻り値

**_close**ファイルが正常に閉じられた場合は 0 を返します。 戻り値 -1 はエラーを示します。

## <a name="remarks"></a>解説

**_close**関数は *、fd*に関連付けられたファイルを閉じます。

ファイル記述子と基になる OS ファイル ハンドルは閉じられます。 したがって、ファイルが最初に Win32 関数**CreateFile**を使用して開かれ **、_open_osfhandle**を使用してファイル記述子に変換された場合は **、CloseHandle**を呼び出す必要はありません。

この関数は、パラメーターを検証します。 *fd*が不正なファイル記述子である場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は -1 を返し **、errno**は**EBADF**に設定されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_close**|\<io.h>|\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

[_open](open-wopen.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_dup、_dup2](dup-dup2.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_unlink、_wunlink](unlink-wunlink.md)<br/>
