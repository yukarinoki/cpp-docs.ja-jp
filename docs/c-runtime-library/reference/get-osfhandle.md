---
title: _get_osfhandle
ms.date: 4/2/2020
api_name:
- _get_osfhandle
- _o__get_osfhandle
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
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: a12c0c93ae15350a4b91a8aa905acb941f8b6a10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345030"
---
# <a name="_get_osfhandle"></a>_get_osfhandle

指定されたファイル記述子に関連付けられている、オペレーティング システム ファイル ハンドルを取得します。

## <a name="syntax"></a>構文

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>パラメーター

*Fd*<br/>
既存のファイル記述子。

## <a name="return-value"></a>戻り値

*fd*が有効な場合は、オペレーティング システムのファイル ハンドルを返します。 それ以外の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、INVALID_HANDLE_VALUE **INVALID_HANDLE_VALUE** (-1) を返します。 また **、errno**は**EBADF**に設定され、無効なファイル ハンドルを示します。 Win32 ファイル ハンドルとして結果が使用される場合に警告を回避するには、**ハンドル**型にキャストします。

> [!NOTE]
> **stdin** **、stdout**、および**stderr**がストリームに関連付けられていない場合 (たとえば、コンソール ウィンドウのない Windows アプリケーションの場合)、これらのストリームのファイル記述子値は[、_fileno](fileno.md)から特殊値 -2 として返されます。 同様に **、_fileno**の呼び出しの結果の代わりに 0、1、または 2 をファイル記述子パラメーターとして使用する場合 **、_get_osfhandle**は、ファイル記述子がストリームに関連付けられていない場合に特殊値 -2 を返し **、errno**を設定しません。 ただし、これは有効なファイル ハンドル値ではなく、その後の呼び出しで使用が失敗する可能性があります。

**EBADF**およびその他のエラー コードの詳細については[、_doserrno、エラー、_sys_errlist、および_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)を参照してください。

## <a name="remarks"></a>解説

**_get_osfhandle**でオペレーティング システム (OS) ファイル ハンドルを取得したファイルを閉じるには、 ファイル記述子*fd*の[_close](close.md)を呼び出します。 この関数の戻り値に対して**CloseHandle**を呼び出すことはありません。 基になる OS ファイル ハンドルは*fd*ファイル記述子によって所有され[、fd](close.md) *fd*で _closeが呼び出されると閉じられます。 ファイル記述子が`FILE *`ストリームによって所有されている場合、その`FILE *`ストリームで[fclose](fclose-fcloseall.md)を呼び出すと、ファイル記述子と基礎となる OS ファイルハンドルの両方が閉じられます。 この場合は、ファイル記述子に[対して_close](close.md)を呼び出さないでください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_dup、_dup2](dup-dup2.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
