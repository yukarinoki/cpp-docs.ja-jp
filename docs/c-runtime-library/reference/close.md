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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: c642820bf1bc2e2afbd14e17832fb3fdb6f865b8
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919850"
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

*スクリプター*<br/>
開いているファイルを参照するファイル記述子。

## <a name="return-value"></a>戻り値

ファイルが正常に閉じられた場合、 **_close**は0を返します。 戻り値-1 はエラーを示します。

## <a name="remarks"></a>解説

**_Close**関数は、 *fd*に関連付けられているファイルを閉じます。

ファイル記述子と基になる OS ファイル ハンドルは閉じられます。 したがって、ファイルが最初に Win32 関数**CreateFile**を使用して開かれ、 **_open_osfhandle**を使用してファイル記述子に変換された場合、 **CloseHandle**を呼び出す必要はありません。

この関数は、パラメーターを検証します。 *Fd*が無効なファイル記述子である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は-1 を返し、 **errno**は**EBADF**に設定されます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

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
