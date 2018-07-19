---
title: _set_new_handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_new_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_new_handler
- set_new_handler
dev_langs:
- C++
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30cd0c2a991ec046b0b1f55100c58641833cb992
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409811"
---
# <a name="setnewhandler"></a>_set_new_handler

**new** 演算子がメモリの割り当てに失敗した場合は、独自のエラー処理機構に制御を移します。

## <a name="syntax"></a>構文

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>パラメーター

*pNewHandler*<br/>
アプリケーションによって提供されたメモリ処理関数へのポインター。 引数が 0 の場合、新しいハンドラーは削除されます。

## <a name="return-value"></a>戻り値

前の例外を処理して登録されている関数へのポインターを返します **_set_new_handler**、前の関数を後で復元できるようにします。 Previous 関数が設定されていない場合、戻り値を使用して、既定の動作を復元することができます。この値は、 **NULL**です。

## <a name="remarks"></a>コメント

C++ **_set_new_handler**関数を場合は、制御を獲得する例外処理関数を指定します、**新しい**演算子がメモリの割り当てに失敗します。 場合**新しい**失敗した場合、実行時のシステムに自動的に関数を呼び出す例外処理への引数として渡された **_set_new_handler**です。 **_PNH**New.h で定義されている型を返す関数へのポインターには、 **int**型の引数を受け取ると**size_t**です。 使用して**size_t**に割り当てられる領域の量を指定します。

既定のハンドラーはありません。

**_set_new_handler**ガベージ コレクション スキームでは基本的には、します。 ランタイム システムは、関数がゼロ以外の値を返すたびに割り当てを再試行し、関数がゼロを返すと失敗します。

発生した、 **_set_new_handler**プログラム内の関数は、ランタイム システムで、引数リストで指定された例外処理関数を登録します。

```cpp
// set_new_handler1.cpp
#include <new.h>

int handle_program_memory_depletion( size_t )
{
   // Your code
}

int main( void )
{
   _set_new_handler( handle_program_memory_depletion );
   int *pi = new int[BIG_NUMBER];
}
```

最後に渡された関数のアドレスを保存することができます、 **_set_new_handler**機能し、後で復元します。

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

C++ の [_set_new_mode](set-new-mode.md) 関数は、[malloc](malloc.md) 用の新しいハンドラー モードを設定します。 新しいハンドラー モードを示すかどうか、失敗した場合、 **malloc**によって設定された新しいハンドラー ルーチンを呼び出すには、 **_set_new_handler**です。 既定では、 **malloc**メモリの割り当てに失敗した場合に新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドすることができるようにときに、 **malloc** 、メモリの割り当てに失敗する**malloc**に同じ新しいハンドラー ルーチンを呼び出す方法、**新しい**演算子が同じ理由で失敗します。 既定の動作を上書きするには、次の関数を呼び出します。

```cpp
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、Newmode.obj にリンクします。

ユーザー定義する場合`operator new`は提供された場合、エラー発生時に新しいハンドラー関数が自動的に呼び出されません。

詳細については、「*C++ 言語リファレンス*」の「[new](../../cpp/new-operator-cpp.md)」および「[delete](../../cpp/delete-operator-cpp.md)」を参照してください。

1 つ **_set_new_handler**のハンドラーを動的にリンクされる Dll または実行可能ファイルですを呼び出す場合でも **_set_new_handler** 、ハンドラーを置き換える可能性があります、または交換する、。ハンドラーが別の DLL または実行可能ファイルで設定します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_set_new_handler**|\<new.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

この例では、割り当てが失敗した場合に、MyNewHandler に制御が移ります。 MyNewHandler に渡される引数は、要求されたバイト数です。 MyNewHandler から返される値は、割り当てを再試行する必要があるかどうかを示すフラグです。ゼロ以外の値は割り当てを再試行すべきことを示し、ゼロの値は割り当てが失敗したことを示します。

```cpp
// crt_set_new_handler.cpp
// compile with: /c
#include <stdio.h>
#include <new.h>
#define BIG_NUMBER 0x1fffffff

int coalesced = 0;

int CoalesceHeap()
{
   coalesced = 1;  // Flag RecurseAlloc to stop
   // do some work to free memory
   return 0;
}
// Define a function to be called if new fails to allocate memory.
int MyNewHandler( size_t size )
{
   printf("Allocation failed. Coalescing heap.\n");

   // Call a function to recover some heap space.
   return CoalesceHeap();
}

int RecurseAlloc() {
   int *pi = new int[BIG_NUMBER];
   if (!coalesced)
      RecurseAlloc();
   return 0;
}

int main()
{
   // Set the failure handler for new to be MyNewHandler.
   _set_new_handler( MyNewHandler );
   RecurseAlloc();
}
```

```Output
Allocation failed. Coalescing heap.

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
