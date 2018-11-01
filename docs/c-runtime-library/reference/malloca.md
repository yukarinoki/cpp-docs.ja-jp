---
title: _malloca
ms.date: 11/04/2016
apiname:
- _malloca
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
- malloca
- _malloca
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
ms.openlocfilehash: 8c8ce8bdf8ab40cae45ecec9c4b182bdf3d6bc82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563983"
---
# <a name="malloca"></a>_malloca

スタックにメモリを割り当てます。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_alloca](alloca.md) です。

## <a name="syntax"></a>構文

```C
void *_malloca(
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
スタックから割り当てられるバイト数。

## <a name="return-value"></a>戻り値

**_Malloca**ルーチンを返します、 **void**どの型のオブジェクトの記憶域の適切なアラインメントが保証されている、割り当てられた領域へのポインター。 場合*サイズ*は 0 です。 **_malloca**長さ 0 の項目を割り当てると、その項目の有効なポインターを返します。

領域の割り当てができない場合、スタック オーバーフロー例外が生成されます。 スタック オーバーフロー例外は C++ 例外ではなく、構造化例外です。 C++ 例外処理を使用する代わりに、[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) (SEH) を使用する必要があります。

## <a name="remarks"></a>Remarks

**_malloca**割り当てます*サイズ*プログラム スタックまたはヒープの場合は、要求で指定されたバイト数で特定のサイズを超えていますからバイト **_ALLOCA_S_THRESHOLD**します。 間の差 **_malloca**と **_alloca**される **_alloca**サイズに関係なく、スタックで常に割り当てます。 異なり **_alloca**、する必要がありますまたはへの呼び出しを許可しません**無料**、メモリを解放する **_malloca**の使用を要求[_freea](freea.md)メモリを解放します。 デバッグ モードで **_malloca**常に、ヒープからメモリを割り当てます。

明示的に呼び出すには制限 **_malloca**例外ハンドラー (EH)。 x86 クラスのプロセッサで動作する EH ルーチンは、自身のメモリ フレーム内で処理されるため、外側の関数のスタック ポインターが示す現在位置を基にしたメモリ領域ではタスクを実行しません。 最も一般的な実装には、Windows NT 構造化例外処理 (SEH) や C++ catch 句の式などがあります。 そのため、明示的に呼び出す **_malloca**呼び出した EH ルーチンへの復帰時にプログラム エラー シナリオ結果は次のいずれかで。

- Windows NT SEH 例外フィルター式: **_ _except** (`_malloca ()` )

- Windows NT SEH 最終例外ハンドラー: **_ _finally** {`_malloca ()` }

- C++ EH catch 句の式

ただし、 **_malloca**できますから直接呼び出すを EH ルーチン内、または呼び出されるアプリケーションによって提供されるコールバックから以前にリストされた EH シナリオのいずれか。

> [!IMPORTANT]
> Windows XP で場合 **_malloca**が呼び出されます、try/catch ブロック内で呼び出す必要がある[_resetstkoflw](resetstkoflw.md)の catch ブロックでします。

使用する場合、上記の制限だけでなく、 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)オプション、 **_malloca**では使用できません **_ _except**ブロックします。 詳細については、「 [/clr Restrictions](../../build/reference/clr-restrictions.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_malloca**|\<malloc.h>|

## <a name="example"></a>例

```C
// crt_malloca_simple.c
#include <stdio.h>
#include <malloc.h>

void Fn()
{
   char * buf = (char *)_malloca( 100 );
   // do something with buf
   _freea( buf );
}

int main()
{
   Fn();
}
```

## <a name="example"></a>例

```C
// crt_malloca_exception.c
// This program demonstrates the use of
// _malloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size;
    int     numberRead = 0;
    int     errcode = 0;
    void    *p = NULL;
    void    *pMarker = NULL;

    while (numberRead == 0)
    {
        printf_s("Enter the number of bytes to allocate "
                 "using _malloca: ");
        numberRead = scanf_s("%d", &size);
    }

    // Do not use try/catch for _malloca,
    // use __try/__except, since _malloca throws
    // Structured Exceptions, not C++ exceptions.

    __try
    {
        if (size > 0)
        {
            p =  _malloca( size );
        }
        else
        {
            printf_s("Size must be a positive number.");
        }
        _freea( p );
    }

    // Catch any exceptions that may occur.
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_malloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf("Could not reset the stack!");
            _exit(1);
        }
    };
}
```

### <a name="input"></a>入力

```Input
1000
```

### <a name="sample-output"></a>出力例

```Output
Enter the number of bytes to allocate using _malloca: 1000
```

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
