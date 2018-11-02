---
title: va_arg、va_copy、va_end、va_start
ms.date: 11/04/2016
apiname:
- va_arg
- va_end
- va_copy
- va_start
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
- va_arg
- va_start
- va_list
- va_alist
- va_dcl
- va_copy
- va_end
helpviewer_keywords:
- variable argument lists, accessing
- va_start macro
- va_arg macro
- va_end macro
- arguments [C++], argument lists
- va_list macro
- va_dcl macro
- va_alist macro
- va_copy macro
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
ms.openlocfilehash: cc0a903f6bc4895f7d2ea6e80990dea94f28c6c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506354"
---
# <a name="vaarg-vacopy-vaend-vastart"></a>va_arg、va_copy、va_end、va_start

可変個引数リストにアクセスする。

## <a name="syntax"></a>構文

```C
type va_arg(
   va_list arg_ptr,
   type
);
void va_copy(
   va_list dest,
   va_list src
); // (ISO C99 and later)
void va_end(
   va_list arg_ptr
);
void va_start(
   va_list arg_ptr,
   prev_param
); // (ANSI C89 and later)
void va_start(
   arg_ptr
);  // (deprecated Pre-ANSI C89 standardization version)
```

### <a name="parameters"></a>パラメーター

*type*<br/>
取得される引数の型。

*arg_ptr*<br/>
引数リストへのポインター。

*dest*<br/>
初期化される引数のリストへのポインター *src*

*src*<br/>
コピーする引数の初期化リストへのポインター *dest*します。

*prev_param*<br/>
最初の省略可能な引数に先行するパラメーター。

## <a name="return-value"></a>戻り値

**va_arg**は現在の引数を返します。 **va_copy**、 **va_start**と**va_end**値は返されません。

## <a name="remarks"></a>Remarks

**Va_arg**、 **va_copy**、 **va_end**、および**va_start**マクロは、移植可能な関数の引数にアクセスするときに、関数は、可変個の引数を受け取ります。 このマクロには 2 種類のバージョンがあります。STDARG.H で定義されているマクロは、ISO C99 標準に準拠します。VARARGS.H で定義されているマクロは非推奨とされましたが、ANSI C89 標準以前に作成されたコードの下位互換性のために残されています。

これらのマクロは、関数が固定の個数の必須の引数の後に、省略可能な引数を可変個数受け取るものと想定します。 必須の引数は、関数の通常のパラメーターのように宣言され、パラメーター名でアクセスできます。 省略可能な引数は、STDARG.H (または、ANSI C89 標準以前に書かれたコードの場合は VARARGS.H) のマクロを使用してアクセスします。これらのマクロは、ポインターを引数リストの最初の省略可能な引数へセットし、リストから引数を取得し引数の処理が終了するとポインターをリセットします。

STDARG.H で定義されている C 標準マクロは次のように使用されます。

- **va_start**設定*arg_ptr*関数に渡される引数の一覧で 1 番目の省略可能な引数。 引数*arg_ptr*必要があります、 **va_list**型。 引数*prev_param*引数リストの最初の省略可能な引数の直前にある必須のパラメーターの名前を指定します。 場合*prev_param*マクロの動作は未定義レジスタのストレージ クラスで宣言されます。 **va_start**前に使用する必要があります**va_arg**を初めて使用します。

- **va_arg**の値を取得*型*で指定された場所から*arg_ptr*、およびインクリメント*arg_ptr*で一覧には、次の引数をポイントするにはサイズを使用して*型*に次の引数の開始位置を特定します。 **va_arg**できる時間の任意の数をリストから引数を取得する関数で使用します。

- **va_copy**現在の状態で引数のリストのコピーを作成します。 *Src*パラメーターで既に初期化する必要があります**va_start**; で更新された**va_arg**を呼び出すが使用する必要がありますリセットされていない**va_end**. 次の引数によって取得される**va_arg**から*dest*から取得される次の引数と同じ*src*します。

- すべての引数が取得された後**va_end**へのポインターをリセット**NULL**します。 **va_end**使用して初期化される各引数リストで呼び出す必要がある**va_start**または**va_copy**関数が戻る前にします。

> [!NOTE]
> VARARGS.H のマクロは非推奨とされており、C89 ANSI 規格以前に作成されたコードとの下位互換性のためだけに残されています。 それ以外の場合は、STDARGS.H のマクロを使用します。

これらのマクロを使用するプログラムを [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) でコンパイルすると、ネイティブ言語ランタイムと共通言語ランタイム (CLR) の型システムの違いにために予期しない結果が発生することがあります。 次のプログラムを検討します。

```C
#include <stdio.h>
#include <stdarg.h>

void testit (int i, ...)
{
    va_list argptr;
    va_start(argptr, i);

    if (i == 0)
    {
        int n = va_arg(argptr, int);
        printf("%d\n", n);
    }
    else
    {
        char *s = va_arg(argptr, char*);
        printf("%s\n", s);
    }

    va_end(argptr);
}

int main()
{
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int
    testit(1, NULL);       // 2nd problem: NULL is not a char*
}
```

注意**testit**いずれかを指定する 2 番目のパラメーターが必要ですが、 **int**または**char**<strong>\*</strong>。 渡された引数は 0 xffffffff (、**符号なし** **int**ではなく、 **int**) と**NULL** (実際には**int**ではなく、 **char**<strong>\*</strong>)。 ネイティブ コードの場合にプログラムをコンパイルすると、次の出力が生成されます。

```Output
-1

(null)
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<stdio.h> および \<stdarg.h>

**非推奨のヘッダー:**\<varargs.h&amp;gt;

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_va.c
// Compile with: cl /W3 /Tc crt_va.c
// The program below illustrates passing a variable
// number of arguments using the following macros:
//      va_start            va_arg              va_copy
//      va_end              va_list

#include <stdio.h>
#include <stdarg.h>
#include <math.h>

double deviation(int first, ...);

int main( void )
{
    /* Call with 3 integers (-1 is used as terminator). */
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));

    /* Call with 4 integers. */
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));

    /* Call with just -1 terminator. */
    printf("Deviation is: %f\n", deviation(-1));
}

/* Returns the standard deviation of a variable list of integers. */
double deviation(int first, ...)
{
    int count = 0, i = first;
    double mean = 0.0, sum = 0.0;
    va_list marker;
    va_list copy;

    va_start(marker, first);     /* Initialize variable arguments. */
    va_copy(copy, marker);       /* Copy list for the second pass */
    while (i != -1)
    {
        sum += i;
        count++;
        i = va_arg(marker, int);
    }
    va_end(marker);              /* Reset variable argument list. */
    mean = sum ? (sum / count) : 0.0;

    i = first;                  /* reset to calculate deviation */
    sum = 0.0;
    while (i != -1)
    {
        sum += (i - mean)*(i - mean);
        i = va_arg(copy, int);
    }
    va_end(copy);               /* Reset copy of argument list. */
    return count ? sqrt(sum / count) : 0.0;
}
```

```Output
Deviation is: 0.816497
Deviation is: 2.236068
Deviation is: 0.000000
```

## <a name="see-also"></a>関連項目

[引数へのアクセス](../../c-runtime-library/argument-access.md)<br/>
[vfprintf、_vfprintf_l、vfwprintf、_vfwprintf_l](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)<br/>
