---
title: _unlock_file
ms.date: 11/04/2016
apiname:
- _unlock_file
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _unlock_file
- unlock_file
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
ms.openlocfilehash: e3d11cbd59ef5846b33908ae6b6c40d7ea6125e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552530"
---
# <a name="unlockfile"></a>_unlock_file

他のプロセスがアクセスできるようにファイルのロックを解除します。

## <a name="syntax"></a>構文

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>パラメーター

*file*<br/>
ファイル ハンドルです。

## <a name="remarks"></a>Remarks

**_Unlock_file**関数で指定されたファイルのロックを解除*ファイル*します。 ファイルのロックを解除すると、他のプロセスがそのファイルにアクセスできるようになります。 しない限り、この関数を呼び出さないで **_lock_file**が呼び出されていた、*ファイル*ポインター。 呼び出す **_unlock_file**でロックされていないファイルもデッドロックにつながる可能性があります。 例については、「[_lock_file](lock-file.md)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
