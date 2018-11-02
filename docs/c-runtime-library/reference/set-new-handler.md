---
title: _set_new_handler
ms.date: 11/04/2016
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
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
ms.openlocfilehash: bc7718503f59c69868a75cac9383286a548fc307
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640311"
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

前の例外処理によって登録された関数へのポインターを返します **_set_new_handler**、前の関数を後で復元できるようにします。 既定の動作を復元する戻り値を使用できますの前の関数が設定されていない場合この値は**NULL**します。

## <a name="remarks"></a>Remarks

C++ **_set_new_handler**関数を場合は、制御を獲得する例外処理関数を指定します、**新しい**演算子がメモリの割り当てに失敗します。 場合**新しい**失敗した場合、実行時のシステムは自動的に例外処理関数に引数として渡された呼び出し **_set_new_handler**します。 **_PNH**New.h に定義されている型を返す関数へのポインターには、 **int**型の引数を取ります**size_t**します。 使用**size_t**に割り当てられる領域の量を指定します。

既定のハンドラーはありません。

**_set_new_handler**は基本的に、ガベージ コレクション スキームです。 ランタイム システムは、関数がゼロ以外の値を返すたびに割り当てを再試行し、関数がゼロを返すと失敗します。

発生、 **_set_new_handler**プログラムで関数が実行時のシステムと、引数リストで指定された例外処理関数を登録します。

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

最後に渡された関数のアドレスを保存することができます、 **_set_new_handler**関数を後で再開します。

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

C++ の [_set_new_mode](set-new-mode.md) 関数は、[malloc](malloc.md) 用の新しいハンドラー モードを設定します。 新しいハンドラー モードを示すかどうか、失敗した場合、 **malloc**によって設定された新しいハンドラー ルーチンを呼び出すには、 **_set_new_handler**します。 既定では、 **malloc**でメモリの割り当ての失敗によって新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドするように、 **malloc** 、メモリの割り当てに失敗した**malloc**に同じ新しいハンドラー ルーチンを呼び出す方法、**新しい**演算子が同じ理由で失敗しました。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```cpp
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、Newmode.obj にリンクします。

ユーザー定義する場合`operator new`が指定されて、失敗した場合、新しいハンドラー関数が自動的に呼び出されません。

詳細については、「*C++ 言語リファレンス*」の「[new](../../cpp/new-operator-cpp.md)」および「[delete](../../cpp/delete-operator-cpp.md)」を参照してください。

1 つは **_set_new_handler**ハンドラーを動的にリンクされる Dll または; の実行可能ファイルを呼び出す場合でも **_set_new_handler**別、ハンドラーが置き換えられること、または置換する、ハンドラーが別の DLL または実行可能ファイルで設定します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
