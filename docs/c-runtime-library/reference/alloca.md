---
title: _alloca
ms.date: 11/04/2016
api_name:
- _alloca
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _alloca
- alloca
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
ms.openlocfilehash: 2212f9e40c78932b63eebfc221ad2f07fa3d3f9d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943694"
---
# <a name="_alloca"></a>_alloca

スタックにメモリを割り当てます。 セキュリティが強化されたバージョンを使用できるため、この関数は非推奨とされます。「 [_malloca](malloca.md)」を参照してください。

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

**_Alloca**ルーチンは、割り当てられた領域への**void**ポインターを返します。これは、どの型のオブジェクトの格納にも適切にアラインメントされていることが保証されています。 *Size*が0の場合、 **_alloca**は長さが0のアイテムを割り当て、そのアイテムへの有効なポインターを返します。

領域の割り当てができない場合、スタック オーバーフロー例外が生成されます。 スタック オーバーフロー例外は C++ 例外ではなく、構造化例外です。 C++ 例外処理を使用する代わりに、[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) (SEH) を使用する必要があります。

## <a name="remarks"></a>Remarks

**_alloca**は、プログラムスタックから*サイズ*バイトを割り当てます。 割り当てられた領域は、呼び出し元の関数が終了したときに自動的に解放されます (割り当てがスコープ外に渡されるだけではありません)。 したがって、 **_alloca**によって返されたポインター値を引数として[解放](free.md)することはできません。

例外ハンドラー (EH) で **_alloca**を明示的に呼び出すには、制限があります。 X86 クラスのプロセッサで実行される EH ルーチンは、独自のメモリフレームで動作します。これらのタスクは、外側の関数のスタックポインターの現在の位置に基づいていないメモリ空間で実行されます。 最も一般的な実装には、Windows NT 構造化例外処理 (SEH) や C++ catch 句の式などがあります。 したがって、次のいずれかのシナリオで **_alloca**を明示的に呼び出すと、呼び出し元の EH ルーチンに戻るときにプログラムエラーが発生します。

- Windows NT SEH 例外フィルター式:`__except ( _alloca() )`

- Windows NT SEH の最後の例外ハンドラー:`__finally { _alloca() }`

- C++ EH catch 句の式

ただし、 **_alloca**は eh ルーチン内から直接呼び出すことも、前述の eh シナリオのいずれかで呼び出されるアプリケーション提供のコールバックから呼び出すこともできます。

> [!IMPORTANT]
> Windows XP では、 **_alloca**が try/catch ブロック内で呼び出された場合は、catch ブロックで[_resetstkoflw](resetstkoflw.md)を呼び出す必要があります。

上記の制限に加え、[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)オプションを使用する場合、_alloca**ブロックで** **_alloca**を使用することはできません。 詳細については、「 [/clr Restrictions](../../build/reference/clr-restrictions.md)」を参照してください。

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
