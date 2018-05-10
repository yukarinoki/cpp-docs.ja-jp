---
title: _malloca | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c6f6b731bce5667ca992e7181518bf0a9eb2b87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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

**_Malloca**ルーチンを返します、 **void**を任意の型のオブジェクトの記憶域を適切に配置することが保証される、割り当てられた領域へのポインター。 場合*サイズ*0 の場合は、 **_malloca**長さ 0 のアイテムを割り当て、その項目に有効なポインターを返します。

領域の割り当てができない場合、スタック オーバーフロー例外が生成されます。 スタック オーバーフロー例外は C++ 例外ではなく、構造化例外です。 C++ 例外処理を使用する代わりに、[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) (SEH) を使用する必要があります。

## <a name="remarks"></a>コメント

**_malloca**割り当てます*サイズ*はプログラム スタックまたは要求が特定のサイズによって指定されたバイトを超える場合、ヒープからのバイト **_ALLOCA_S_THRESHOLD**です。 違い **_malloca**と **_alloca**される **_alloca**サイズに関係なく、スタックに常に割り当てます。 異なり **_alloca**、する必要がありますまたはへの呼び出しを許可しません**空き**割り当てられているため、メモリを解放する **_malloca**の使用を要求[_freea](freea.md)メモリを解放します。 デバッグ モードで **_malloca**常に、ヒープからメモリを割り当てます。

明示的に呼び出すに制限がある **_malloca**例外ハンドラー (EH)。 x86 クラスのプロセッサで動作する EH ルーチンは、自身のメモリ フレーム内で処理されるため、外側の関数のスタック ポインターが示す現在位置を基にしたメモリ領域ではタスクを実行しません。 最も一般的な実装には、Windows NT 構造化例外処理 (SEH) や C++ catch 句の式などがあります。 そのため、明示的に呼び出す **_malloca**呼び出し元の EH ルーチンへ戻る時にプログラムの障害に次のシナリオの結果のいずれかで。

- Windows NT の SEH 例外フィルター式: **_ _except** (`_malloca ()` )

- Windows NT SEH 最終的な例外ハンドラー: **_ _finally** {`_malloca ()` }

- C++ EH catch 句の式

ただし、 **_malloca**が呼び出せますから直接 EH ルーチン内、または呼び出される、アプリケーションによって提供されるコールバックから前に示した EH シナリオのいずれか。

> [!IMPORTANT]
> Windows XP の場合は **_malloca**が呼び出された try ブロックと catch ブロック内で呼び出す必要があります[_resetstkoflw](resetstkoflw.md)の catch ブロックでします。

使用する場合、上記の制限に加えて、 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)オプション、 **_malloca**では使用できません **_ _except**ブロックします。 詳細については、「 [/clr Restrictions](../../build/reference/clr-restrictions.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
