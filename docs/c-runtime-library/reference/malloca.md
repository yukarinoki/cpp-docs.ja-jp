---
title: _malloca
ms.date: 11/04/2016
api_name:
- _malloca
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
- malloca
- _malloca
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
ms.openlocfilehash: 64bed4dac2bbaeb60c7b04a600af38f455caf08d
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008266"
---
# <a name="_malloca"></a>_malloca

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

**_Malloca**ルーチンは、 **`void`** 割り当てられた領域へのポインターを返します。これは、オブジェクトのすべての型を格納するために適切にアラインメントされていることが保証されています。 *Size*が0の場合、 **_malloca**によって長さ0の項目が割り当てられ、その項目への有効なポインターが返されます。

*Size*が **_ALLOCA_S_THRESHOLD**より大きい場合、 **_malloca**はヒープに割り当てを試み、スペースを割り当てることができない場合は null ポインターを返します。 *Size*が **_ALLOCA_S_THRESHOLD**以下の場合、 **_malloca**はスタックに割り当てを試行し、領域を割り当てることができない場合はスタックオーバーフロー例外が生成されます。 スタックオーバーフロー例外は C++ 例外ではありません。構造化された例外です。 C++ 例外処理を使用する代わりに、 [構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) (SEH) を使用してこの例外をキャッチする必要があります。

## <a name="remarks"></a>解説

要求が **_ALLOCA_S_THRESHOLD**によって指定されたバイト数を超えた場合、 **_malloca**はプログラムスタックまたはヒープから*サイズ*バイトを割り当てます。 **_Malloca**と **_alloca**の違いは、サイズにかかわらず、 **_alloca**は常にスタックに割り当てられるという点です。 メモリを解放して割り当てられるように**解放**するための呼び出しが不要であるか許可されていない **_alloca**とは異なり、 **_malloca**では、メモリを解放するために[_freea](freea.md)を使用する必要があります。 デバッグモードでは、 **_malloca** は常にヒープからメモリを割り当てます。

例外ハンドラー (EH) で **_malloca** を明示的に呼び出すには制限があります。 x86 クラスのプロセッサで動作する EH ルーチンは、自身のメモリ フレーム内で処理されるため、外側の関数のスタック ポインターが示す現在位置を基にしたメモリ領域ではタスクを実行しません。 最も一般的な実装には、Windows NT 構造化例外処理 (SEH) や C++ catch 句の式などがあります。 したがって、次のいずれかのシナリオで明示的に **_malloca** を呼び出すと、呼び出し元の EH ルーチンに戻るときにプログラムエラーが発生します。

- Windows NT SEH 例外フィルター式: **`__except`** ( `_malloca ()` )

- Windows NT SEH の最後の例外ハンドラー: **`__finally`** { `_malloca ()` }

- C++ EH catch 句の式

ただし、 **_malloca** は、eh ルーチン内から直接呼び出すことも、前述の eh シナリオのいずれかで呼び出されるアプリケーション提供のコールバックから呼び出すこともできます。

> [!IMPORTANT]
> Windows XP で **_malloca** が try/catch ブロック内で呼び出された場合は、catch ブロックで [_resetstkoflw](resetstkoflw.md) を呼び出す必要があります。

上記の制限に加え、 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用する場合、 **_malloca** をブロック内で使用することはできません **`__except`** 。 詳細については、「 [/clr Restrictions](../../build/reference/clr-restrictions.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_malloca**|\<malloc.h>|

## <a name="example-malloca"></a>例: malloca

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

## <a name="example-malloca-exception"></a>例: malloca exception

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

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
