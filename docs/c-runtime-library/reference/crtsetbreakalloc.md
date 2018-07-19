---
title: _CrtSetBreakAlloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetBreakAlloc
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
apitype: DLLExport
f1_keywords:
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
dev_langs:
- C++
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32e8fedcd70d0e901c63cd5e794773451f436326
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395436"
---
# <a name="crtsetbreakalloc"></a>_CrtSetBreakAlloc

指定されたオブジェクト割り当て順序番号にブレークポイントを設定します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
long _CrtSetBreakAlloc(
   long lBreakAlloc
);
```

### <a name="parameters"></a>パラメーター

*lBreakAlloc*<br/>
ブレークポイントを設定する割り当て順序番号。

## <a name="return-value"></a>戻り値

ブレークポイントが設定されていた、以前のオブジェクト割り当て順序番号を返します。

## <a name="remarks"></a>コメント

**_CrtSetBreakAlloc**アプリケーションでメモリ リークの検出を実行するには、特定の時点のメモリ割り当ての互換性に影響し、要求の起点までさかのぼってトレースします。 関数は、メモリ ブロックがヒープ上に割り当てられたときに決められた、シーケンシャルなオブジェクト割り当て順序番号を使用します。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていないへの呼び出し **_CrtSetBreakAlloc**プリプロセス時に削除されます。

オブジェクト割り当て順序番号は、Crtdbg.h で定義されている **_CrtMemBlockHeader** 構造体の *lRequest* フィールドに格納されます。 デバッグ ダンプ関数のいずれかでメモリ ブロックに関する情報が報告されると、この番号はかっこで囲みますなど{36}です。

方法の詳細についての **_CrtSetBreakAlloc**他のメモリ管理関数と共に使用できるを参照してください[ヒープ割り当て要求の追跡](/visualstudio/debugger/crt-debug-heap-details)です。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_CrtSetBreakAlloc**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

```C
// crt_setbrkal.c
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug

/*
* In this program, a call is made to the _CrtSetBreakAlloc routine
* to verify that the debugger halts program execution when it reaches
* a specified allocation number.
*/

#include <malloc.h>
#include <crtdbg.h>

int main( )
{
        long allocReqNum;
        char *my_pointer;

        /*
         * Allocate "my_pointer" for the first
         * time and ensure that it gets allocated correctly
         */
        my_pointer = malloc(10);
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);

        /*
         * Set a breakpoint on the allocation request
         * number for "my_pointer"
         */
        _CrtSetBreakAlloc(allocReqNum+2);

        /*
         * Alternate freeing and reallocating "my_pointer"
         * to verify that the debugger halts program execution
         * when it reaches the allocation request
         */
        free(my_pointer);
        my_pointer = malloc(10);
        free(my_pointer);
        my_pointer = malloc(10);
        free(my_pointer);
}
```

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
