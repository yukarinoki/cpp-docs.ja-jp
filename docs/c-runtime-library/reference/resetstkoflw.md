---
title: _resetstkoflw
ms.date: 4/2/2020
api_name:
- _resetstkoflw
- _o__resetstkoflw
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- resetstkoflw
- _resetstkoflw
helpviewer_keywords:
- resetstkoflw function
- stack overflow
- stack, recovering
- _resetstkoflw function
ms.assetid: 319529cd-4306-4d22-810b-2063f3ad9e14
ms.openlocfilehash: dfe0de4f48173a0e79bcdcfb24bfdf7a21f47a04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332815"
---
# <a name="_resetstkoflw"></a>_resetstkoflw

スタック オーバーフローから復元します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _resetstkoflw( void );
```

## <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外、失敗した場合は 0。

## <a name="remarks"></a>解説

**_resetstkoflw**関数はスタック・オーバーフロー状態からリカバリーするため、致命的な例外エラーで失敗する代わりにプログラムを継続できます。 **_resetstkoflw**関数が呼び出されない場合、前の例外の後にガード ページはありません。 次にスタック オーバーフローが発生したときに例外は発生しないので、プロセスは警告なしで終了します。

アプリケーションのスレッドにより **EXCEPTION_STACK_OVERFLOW** の例外が発生した場合、そのスレッドによってスタックは破損したままの状態になります。 これは、スタックが破損しない **EXCEPTION_ACCESS_VIOLATION** や **EXCEPTION_INT_DIVIDE_BY_ZERO** などの他の例外とは対照的です。 プログラムが最初に読み込まれたときには、スタックには小さい値が設定されます。 その後、スタックはスレッドのニーズに対応して必要に応じて大きくなります。 これは、現在のスタックの末尾に PAGE_GUARD のアクセス権を使用してページを設定することによって実装されます。 詳細については、「[Creating Guard Pages](/windows/win32/Memory/creating-guard-pages)」 (ガード ページの作成) をご覧ください。

コードによってスタック ポインターがこのページのアドレスをポイントすると、例外が発生し、システムは次の 3 つのことを実行します。

- ガード ページの PAGE_GUARD の保護を削除して、スレッドがメモリにデータを読み書きできるようにします。

- 最後のページの下のページにある新しいガード ページを割り当てます。

- 例外を発生させた命令を再実行します。

この方法では、システムがスレッドに対するスタック サイズを自動的にインクリメントできます。 プロセスの各スレッドには最大スタック サイズがあります。 スタック サイズはコンパイル時に [/STACK (Stack Allocations)](../../build/reference/stack-stack-allocations.md)、またはプロジェクトの .def ファイルの [STACKSIZE](../../build/reference/stacksize.md) ステートメントによって設定されます。

この最大スタック サイズを超えると、システムは次の 3 つのことを実行します。

- 前述のようにガード ページの PAGE_GUARD の保護を削除します。

- 最後のページの下に新しいガード ページの割り当てを試みます。 ただし、これは最大スタック サイズを超過しているため失敗します。

- 例外を発生させて、スレッドが例外ブロックで処理できるようにします。

その時点ではスタックにガード ページがないことに注意してください。 次にプログラムによってスタックのサイズが最後まで拡張されると、この場合はガード ページがある必要があり、プログラムはスタックの末尾を越えて書き込みを行い、アクセス違反が発生します。

スタック オーバーフロー例外の後に回復が行われるたびにガード ページを復元するには **、_resetstkoflw**を呼び出します。 この関数は **、__except**ブロックの本体の内部または **__except**ブロックの外側から呼び出すことができます。 ただし、使用する必要がある場合には、いくつかの制限があります。 **_resetstkoflw**は、次の場合に呼び出す必要があります。

- フィルター式。

- フィルター関数。

- フィルター関数から呼び出される関数。

- **catch** ブロック。

- **__finally**ブロック。

これらの時点では、スタックは完全にはアンワインドされていません。

スタック オーバーフロー例外は C++ 例外ではなく構造化例外として生成されるため **、_resetstkoflw**はスタック オーバーフロー例外をキャッチしないため、通常の**catch**ブロックでは役に立ちません。 ただし、[_set_se_translator](set-se-translator.md) を使用して C++ 例外をスローする構造化例外の変換を実装すると (2 番目の例のように)、スタック オーバーフロー例外によって C ++ 例外が発生します。これは C++ の catch ブロックで処理できます。

構造化例外変換関数によってスローされる例外から到達した C ++ catch ブロックでの **_resetstkoflw** の呼び出しは安全ではありません。 この場合、catch ブロックの前で消滅させられるオブジェクトに対してデストラクターが呼び出された場合でも、catch ブロックの外部に出るまでスタック領域は解放されず、スタック ポインターはリセットされません。 この関数は、スタック領域が解放され、スタック ポインターがリセットされるまで呼び出さないようにする必要があります。 したがって、catch ブロックが終了した後でのみ呼び出すようにします。 catch ブロックではできるだけ小さなスタック領域を使用するようにします。これは、前回のスタック オーバーフローから自身で回復しようとしている catch ブロックでスタック オーバーフローが発生すると回復できなくなり、catch ブロック内でのオーバーフローによって同じ catch ブロックによってハンドルされる例外がトリガーされてプログラムの応答が停止するおそれがあるためです。

**_resetstkoflw** が **__except** ブロック内などの適切な位置で使用されていても、エラーになる場合があります。 スタックのアンワインドを実行した後でも、スタックの最後のページに書き込みをしないで **_resetstkoflw** を実行するためのスタック領域が十分にない場合は、**_resetstkoflw** はスタックの最後のページをガード ページとしてリセットすることに失敗し、エラーを表す 0 を返します。 したがってこの関数を安全に使用するには、スタックを使用しても安全であると想定するのではなく、戻り値をチェックする必要があります。

構造化例外処理では、アプリケーションが **/clr**でコンパイルされるときに **、STATUS_STACK_OVERFLOW**例外をキャッチしません[(/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)を参照)。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_resetstkoflw**|\<malloc.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

**ライブラリ:**[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のすべてのバージョンです。

## <a name="example"></a>例

次の例は **、_resetstkoflw**関数の推奨される使用方法を示しています。

```C
// crt_resetstkoflw.c
// Launch program with and without arguments to observe
// the difference made by calling _resetstkoflw.

#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void recursive(int recurse)
{
   _alloca(2000);
   if (recurse)
      recursive(recurse);
}

// Filter for the stack overflow exception.
// This function traps the stack overflow exception, but passes
// all other exceptions through.
int stack_overflow_exception_filter(int exception_code)
{
   if (exception_code == EXCEPTION_STACK_OVERFLOW)
   {
       // Do not call _resetstkoflw here, because
       // at this point, the stack is not yet unwound.
       // Instead, signal that the handler (the __except block)
       // is to be executed.
       return EXCEPTION_EXECUTE_HANDLER;
   }
   else
       return EXCEPTION_CONTINUE_SEARCH;
}

int main(int ac)
{
   int i = 0;
   int recurse = 1, result = 0;

   for (i = 0 ; i < 10 ; i++)
   {
      printf("loop #%d\n", i + 1);
      __try
      {
         recursive(recurse);

      }

      __except(stack_overflow_exception_filter(GetExceptionCode()))
      {
         // Here, it is safe to reset the stack.

         if (ac >= 2)
         {
            puts("resetting stack overflow");
            result = _resetstkoflw();
         }
      }

      // Terminate if _resetstkoflw failed (returned 0)
      if (!result)
         return 3;
   }

   return 0;
}
```

プログラム引数を指定しない出力例:

```Output
loop #1
```

プログラムはこれ以上のイテレーションを実行せずに応答を停止します。

プログラムの引数があります:

```Output
loop #1
resetting stack overflow
loop #2
resetting stack overflow
loop #3
resetting stack overflow
loop #4
resetting stack overflow
loop #5
resetting stack overflow
loop #6
resetting stack overflow
loop #7
resetting stack overflow
loop #8
resetting stack overflow
loop #9
resetting stack overflow
loop #10
resetting stack overflow
```

### <a name="description"></a>説明

構造化例外が C++ 例外に変換されるプログラムで**の_resetstkoflw**の推奨される使用例を次に示します。

### <a name="code"></a>コード

```cpp
// crt_resetstkoflw2.cpp
// compile with: /EHa
// _set_se_translator requires the use of /EHa
#include <malloc.h>
#include <stdio.h>
#include <windows.h>
#include <eh.h>

class Exception { };

class StackOverflowException : Exception { };

// Because the overflow is deliberate, disable the warning that
// this function will cause a stack overflow.
#pragma warning (disable: 4717)
void CauseStackOverflow (int i)
{
    // Overflow the stack by allocating a large stack-based array
    // in a recursive function.
    int a[10000];
    printf("%d ", i);
    CauseStackOverflow (i + 1);
}

void __cdecl SEHTranslator (unsigned int code, _EXCEPTION_POINTERS*)
{
    // For stack overflow exceptions, throw our own C++
    // exception object.
    // For all other exceptions, throw a generic exception object.
    // Use minimal stack space in this function.
    // Do not call _resetstkoflw in this function.

    if (code == EXCEPTION_STACK_OVERFLOW)
        throw StackOverflowException ( );
    else
        throw Exception( );
}

int main ( )
{
    bool stack_reset = false;
    bool result = false;

    // Set up a function to handle all structured exceptions,
    // including stack overflow exceptions.
    _set_se_translator (SEHTranslator);

    try
    {
        CauseStackOverflow (0);
    }
    catch (StackOverflowException except)
    {
        // Use minimal stack space here.
        // Do not call _resetstkoflw here.
        printf("\nStack overflow!\n");
        stack_reset = true;
    }
    catch (Exception except)
    {
        // Do not call _resetstkoflw here.
        printf("\nUnknown Exception!\n");
    }
    if (stack_reset)
    {
        result = _resetstkoflw();
        // If stack reset failed, terminate the application.
        if (result == 0)
            exit(1);
    }

    void* pv = _alloca(100000);
    printf("Recovered from stack overflow and allocated 100,000 bytes"
           " using _alloca.");

    return 0;
}
```

```Output
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24
Stack overflow!
Recovered from stack overflow and allocated 100,000 bytes using _alloca.
```

## <a name="see-also"></a>関連項目

[_alloca](alloca.md)<br/>
