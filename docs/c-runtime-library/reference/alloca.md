---
title: _alloca |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fdc595d33bdc5ce464df1aed86cf885e5673ddc9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394118"
---
# <a name="alloca"></a>_alloca

スタックにメモリを割り当てます。 安全なバージョンがあるために、この関数は推奨されていません参照してください[_malloca](malloca.md)です。

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

**_Alloca**ルーチンを返します、 **void**を任意の型のオブジェクトの記憶域を適切に配置することが保証される、割り当てられた領域へのポインター。 場合*サイズ*0 の場合は、 **_alloca**長さ 0 のアイテムを割り当て、その項目に有効なポインターを返します。

領域の割り当てができない場合、スタック オーバーフロー例外が生成されます。 スタック オーバーフロー例外は C++ 例外ではなく、構造化例外です。 C++ 例外処理を使用する代わりに、[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md) (SEH) を使用する必要があります。

## <a name="remarks"></a>コメント

**_alloca**割り当てます*サイズ*はプログラム スタックからのバイト数。 割り当てられた領域はときではなく、割り当てがスコープ外に渡すだけ)、呼び出し元の関数が終了したときに自動的に解放されます。 そのため、によって返されるポインター値を渡していない **_alloca**への引数として[空き](free.md)です。

明示的に呼び出すに制限がある **_alloca**例外ハンドラー (EH)。 x86 クラスのプロセッサで動作する EH ルーチンは、自身のメモリ フレーム内で処理されるため、外側の関数のスタック ポインターが示す現在位置を基にしたメモリ領域ではタスクを実行しません。 最も一般的な実装には、Windows NT 構造化例外処理 (SEH) や C++ catch 句の式などがあります。 そのため、明示的に呼び出す **_alloca**呼び出し元の EH ルーチンへ戻る時にプログラムの障害に次のシナリオの結果のいずれかで。

- Windows NT の SEH 例外フィルター式: `__except ( _alloca() )`

- Windows NT SEH の最終的な例外ハンドラー: `__finally { _alloca() }`

- C++ EH catch 句の式

ただし、 **_alloca**が呼び出せますから直接 EH ルーチン内、または呼び出される、アプリケーションによって提供されるコールバックから前に示した EH シナリオのいずれか。

> [!IMPORTANT]
> Windows XP の場合は **_alloca**が呼び出された try ブロックと catch ブロック内で呼び出す必要があります[_resetstkoflw](resetstkoflw.md)の catch ブロックでします。

使用する場合、上記の制限に加えて、[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)オプション、 **_alloca**では使用できません **_ _except**ブロックします。 詳細については、「 [/clr Restrictions](../../build/reference/clr-restrictions.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
