---
title: _alloca
ms.date: 11/04/2016
apiname:
- _alloca
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
- _alloca
- alloca
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
ms.openlocfilehash: 7c083e791301d3224709a5fc6c711ceaa6397d38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668075"
---
# <a name="alloca"></a>_alloca

スタックにメモリを割り当てます。 安全なバージョンがあるため、この関数は非推奨します。参照してください[_malloca](malloca.md)します。

## <a name="syntax"></a>構文

```C
void *_alloca(
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
スタックから割り当てられるバイト数。

## <a name="return-value"></a>戻り値

**_Alloca**ルーチンを返します、 **void**どの型のオブジェクトの記憶域の適切なアラインメントが保証されている、割り当てられた領域へのポインター。 場合*サイズ*は 0 です。 **_alloca**長さ 0 の項目を割り当てると、その項目の有効なポインターを返します。

領域の割り当てができない場合、スタック オーバーフロー例外が生成されます。 スタック オーバーフロー例外は C++ 例外ではなく、構造化例外です。 C++ 例外処理を使用する代わりに、[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) (SEH) を使用する必要があります。

## <a name="remarks"></a>Remarks

**_alloca**割り当てます*サイズ*プログラム スタックからのバイト数。 (ときではなく、割り当てがスコープ外に渡すだけです)、呼び出し元関数の終了時に割り当てられた領域は自動的に解放されます。 そのため、によって返されるポインター値を渡していない **_alloca**への引数として[無料](free.md)します。

明示的に呼び出すには制限 **_alloca**例外ハンドラー (EH)。 x86 クラスのプロセッサで動作する EH ルーチンは、自身のメモリ フレーム内で処理されるため、外側の関数のスタック ポインターが示す現在位置を基にしたメモリ領域ではタスクを実行しません。 最も一般的な実装には、Windows NT 構造化例外処理 (SEH) や C++ catch 句の式などがあります。 そのため、明示的に呼び出す **_alloca**呼び出した EH ルーチンへの復帰時にプログラム エラー シナリオ結果は次のいずれかで。

- Windows NT SEH 例外フィルター式: `__except ( _alloca() )`

- Windows NT SEH 最終例外ハンドラー: `__finally { _alloca() }`

- C++ EH catch 句の式

ただし、 **_alloca**できますから直接呼び出すを EH ルーチン内、または呼び出されるアプリケーションによって提供されるコールバックから以前にリストされた EH シナリオのいずれか。

> [!IMPORTANT]
> Windows XP で場合 **_alloca**が呼び出されます、try/catch ブロック内で呼び出す必要がある[_resetstkoflw](resetstkoflw.md)の catch ブロックでします。

使用する場合、上記の制限だけでなく、[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)オプション、 **_alloca**では使用できません **_ _except**ブロックします。 詳細については、「 [/clr Restrictions](../../build/reference/clr-restrictions.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_alloca**|\<malloc.h>|

## <a name="example"></a>例

```C
// crt_alloca.c
// This program demonstrates the use of
// _alloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size = 1000;
    int     errcode = 0;
    void    *pData = NULL;

    // Note: Do not use try/catch for _alloca,
    // use __try/__except, since _alloca throws
    // Structured Exceptions, not C++ exceptions.

    __try {
        // An unbounded _alloca can easily result in a
        // stack overflow.
        // Checking for a size < 1024 bytes is recommended.
        if (size > 0 && size < 1024)
        {
            pData = _alloca( size );
            printf_s( "Allocated %d bytes of stack at 0x%p",
                      size, pData);
        }
        else
        {
            printf_s("Tried to allocate too many bytes.\n");
        }
    }

    // If an exception occured with the _alloca function
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_alloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf_s("Could not reset the stack!\n");
            _exit(1);
        }
    };
}
```

```Output
Allocated 1000 bytes of stack at 0x0012FB50
```

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
[_malloca](malloca.md)<br/>
