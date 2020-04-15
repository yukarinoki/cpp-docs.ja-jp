---
title: _unlock_file
ms.date: 4/2/2020
api_name:
- _unlock_file
- _o__unlock_file
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _unlock_file
- unlock_file
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
ms.openlocfilehash: 46d07a8b3645ae0d68276d96271be0a246716f0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361219"
---
# <a name="_unlock_file"></a>_unlock_file

他のプロセスがアクセスできるようにファイルのロックを解除します。

## <a name="syntax"></a>構文

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>パラメーター

*ファイル*<br/>
ファイル ハンドルです。

## <a name="remarks"></a>解説

**_unlock_file**関数は file*で指定*されたファイルのロックを解除します。 ファイルのロックを解除すると、他のプロセスがそのファイルにアクセスできるようになります。 この関数は、*ファイル*ポインタで **_lock_file**が以前に呼び出されていない限り、呼び出す必要があります。 ロックされていないファイルに**対して_unlock_file**を呼び出すと、デッドロックが発生する可能性があります。 例については、「[_lock_file](lock-file.md)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
