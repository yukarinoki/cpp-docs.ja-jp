---
title: _unlock_file | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d000dce4c0009341c787a211ed8ef41d1728b51b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407773"
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

*ファイル*ファイル ハンドル。

## <a name="remarks"></a>コメント

**_Unlock_file**関数によって指定されたファイルのロックを解除*ファイル*です。 ファイルのロックを解除すると、他のプロセスがそのファイルにアクセスできるようになります。 しない限り、この関数を呼び出すことはできません **_lock_file**でが呼び出された、*ファイル*ポインター。 呼び出す **_unlock_file**ロックされていないファイルのデッドロックにつながる可能性があります。 例については、「[_lock_file](lock-file.md)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
