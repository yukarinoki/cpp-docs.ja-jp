---
title: _heapadd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _heapadd
apilocation:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- heapadd
- _heapadd
dev_langs:
- C++
helpviewer_keywords:
- _heapadd function
- memory, adding to heaps
- heaps, adding memory
- heapadd function
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce067dc000a681dfd1bfa9d3376131f86f5a73e1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086851"
---
# <a name="heapadd"></a>_heapadd

ヒープにメモリを追加します。

> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降、CRT で使用できません。

## <a name="syntax"></a>構文

```
int _heapadd(
   void *memblock,
   size_t size
);
```

#### <a name="parameters"></a>パラメーター

*memblock*<br/>
ヒープ メモリへのポインター。

*size*<br/>
追加するメモリのサイズ (バイト単位)。

## <a name="return-value"></a>戻り値

成功すると、`_heapadd` は 0 を返します。それ以外の場合、この関数は -1 を返し、`errno` を `ENOSYS` に設定します。

このリターン コードとその他のリターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

Visual C++ のバージョン 4.0 以降では、新しいデバッグ機能をサポートするために、基になるヒープ構造が C ランタイム ライブラリに移動しました。 その結果、 `_heapadd` は、Win32 API に基づいているすべてのプラットフォームでサポートされなくなりました。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|`_heapadd`|\<malloc.h>|\<errno.h>|

互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../c-runtime-library/compatibility.md) 」を参照してください。

## <a name="see-also"></a>参照

[メモリ割り当て](../c-runtime-library/memory-allocation.md)<br/>
[free](../c-runtime-library/reference/free.md)<br/>
[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapmin](../c-runtime-library/reference/heapmin.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[malloc](../c-runtime-library/reference/malloc.md)<br/>
[realloc](../c-runtime-library/reference/realloc.md)