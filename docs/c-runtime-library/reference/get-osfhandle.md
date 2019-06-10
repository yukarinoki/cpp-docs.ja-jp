---
title: _get_osfhandle
ms.date: 05/29/2018
apiname:
- _get_osfhandle
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
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: cc3b50e3d3f65bee83b8df83aa0adb5c8694e35a
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821664"
---
# <a name="getosfhandle"></a>_get_osfhandle

指定されたファイル記述子に関連付けられている、オペレーティング システム ファイル ハンドルを取得します。

## <a name="syntax"></a>構文

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>パラメーター

*fd*<br/>
既存のファイル記述子。

## <a name="return-value"></a>戻り値

場合は、オペレーティング システム ファイル ハンドルを返します*fd*は有効です。 それ以外の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 返すかどうかは、引き続き実行が許可された、 **INVALID_HANDLE_VALUE** (-1)。 また、設定**errno**に**EBADF**、無効なファイル ハンドルを示します。 警告を避けるためには、結果を Win32 ファイル ハンドルとして使用する場合、キャストを**処理**型。

> [!NOTE]
> ときに**stdin**、 **stdout**、および**stderr**ないファイル記述子の値 (たとえば、アプリケーションでは、Windows コンソール ウィンドウがない)、ストリームに関連付けられています。これらのストリームがから返された[_fileno](fileno.md)として、特殊な値-2。 同様に、呼び出しの結果ではなく、ファイル記述子のパラメーターとして 0、1、または 2 を使用する場合 **_fileno**、 **_get_osfhandle**ファイル記述子が関連付けられていない場合にも特別な値-2 を返しますストリームを設定しないと**errno**します。 ただし、これは、有効なファイル ハンドルの値ではありません、それを使用しようとする後続の呼び出しは失敗する可能性があります。

詳細については**EBADF** 、他のエラー コードを参照してくださいと[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。

## <a name="remarks"></a>Remarks

オペレーティング システム (OS) のファイル ハンドルが取得したファイルを閉じる **_get_osfhandle**、呼び出す[_close](close.md)ファイル記述子に*fd*。 呼び出さない**CloseHandle**でこの関数の戻り値。 基になる OS ファイル ハンドルを所有、 *fd*ファイル記述子、および閉じられたときに、 [_close](close.md)で呼び出される*fd*します。 ファイル記述子が所有している場合、`FILE *`呼び出してストリーム[fclose](fclose-fcloseall.md)を`FILE *`ストリームは、両方のファイル記述子と基になる OS ファイル ハンドルを閉じます。 この場合、呼び出さない[_close](close.md)ファイル記述子。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_dup、_dup2](dup-dup2.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
