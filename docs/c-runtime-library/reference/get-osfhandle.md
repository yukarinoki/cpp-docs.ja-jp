---
title: _get_osfhandle | Microsoft Docs
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15bddcf3d94935f56fa2e23b6ebd0398ed379c54
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569850"
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

場合は、オペレーティング システム ファイル ハンドルを返します*fd*は無効です。 それ以外の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行は継続許可されたかどうか、この関数を返します**INVALID_HANDLE_VALUE** (-1) を設定および**errno**に**EBADF**、無効なファイル ハンドルを示すです。 コンパイラの警告を避けるためには、Win32 ファイル ハンドルを期待するルーチンで、結果を使用する場合、キャストに、**処理**型です。

## <a name="remarks"></a>コメント

オペレーティング システム (OS) のファイル ハンドルが取得されたファイルを閉じる **_get_osfhandle**、呼び出す[_close](close.md)ファイル記述子に*fd*です。 呼び出す必要はありません**CloseHandle**この関数の戻り値にします。 基になる OS ファイル ハンドルが所有、 *fd*ファイル記述子、および閉じるときに[_close](close.md)で呼び出される*fd*です。 ファイル記述子がによって所有されている場合、**ファイル\*** ストリーム、呼び出すことで、 [fclose](fclose-fcloseall.md)を**ファイル\*** ストリームは、両方のファイル記述子を閉じると基になる OS ファイル ハンドル。 この場合、呼び出さない[_close](close.md)ファイル記述子。

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
