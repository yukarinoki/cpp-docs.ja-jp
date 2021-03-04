---
description: 詳細については、「ベクター化 and 並行化 messages」を参照してください。
title: ベクター化と並列化のメッセージ
ms.date: 02/16/2021
f1_keywords:
- C5011
- C5002
- C5021
- C5001
- C5012
ms.openlocfilehash: 9cfafe9af4859a2bb4dbd7897a14003d85052f63
ms.sourcegitcommit: 5efc34c2b98d4d0d3e41aec38b213f062c19d078
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "101844547"
---
# <a name="vectorizer-and-parallelizer-messages"></a>ベクター化と並列化のメッセージ

Microsoft C++ コンパイラオプションを使用して [`/Qpar-report`](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md) 、 [`/Qvec-report`](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md) [自動並列化と自動ベクター化](../../parallel/auto-parallelization-and-auto-vectorization.md) を設定し、そのアクティビティに関する理由コードと情報メッセージを出力することができます。 この記事では、理由コードとメッセージについて説明します。

## <a name="informational-messages"></a><a name="BKMK_InformationalMessages"></a> 情報メッセージ

指定したレポート レベルに応じて、次のいずれかの情報メッセージがループごとに表示されます。

理由コードの詳細については、この記事の次のパートを参照してください。

| 情報メッセージ | 説明 |
|--|--|
| 5001 | ループがベクター化されました。 |
| 5002 | 理由が '*description*' であるため、ループはベクター化ません。 |
| 5011 | ループが並列化されました。 |
| 5012 | ループが並列化されていません。理由: '*description*'。 |
| 5021 | ループをプラグマに関連付けることができません。 |

次のセクションでは、並行化とベクター化の考えられる理由コードを示します。

## <a name="5xx-reason-codes"></a><a name="BKMK_ReasonCode50x"></a> 5xx 理由コード

5 *xx* の理由コードは、並行化とベクター化の両方に適用されます。

| 理由コード | 説明 |
|--|--|
| 500 | 複数のケースを対象とする汎用メッセージ。たとえば、ループに複数の終了が含まれている場合や、ループヘッダーが誘導変数をインクリメントして終了しない場合などです。 |
| 501 | 誘導変数はローカルではありません。または上限がループに依存していません。 |
| 502 | 誘導変数が単純な +1 以外の何らかの方法でステップ インされています。 |
| 503 | ループ内に例外処理または switch ステートメントがあります。 |
| 504 | ループ本体が C++ オブジェクトの破棄を必要とする例外をスローする場合があります。 |
| 505 | 外側のループには、前置インクリメントされた誘導変数があります。 分析を終了しています。 |

```cpp
void code_500(int *A)
{
    // Code 500 is emitted if the loop has non-vectorizable flow.
    // This can include "if", "break", "continue", the conditional
    // operator "?", or function calls.
    // It also encompasses correct definition and use of the induction
    // variable "i", in that the increment "++i" or "i++" must be the last
    // statement in the loop.

    int i = 0;
    while (i<1000)
    {
        if (i == 4)
        {
            break;
        }

        ++i;

        A[i] = A[i] + 1;
    }
    // To resolve code 500, use a 'for' loop with single increment of
    // induction variable.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

int bound();
void code_501_example1(int *A)
{
    // Code 501 is emitted if the compiler cannot discern the
    // induction variable of this loop. In this case, when it checks
    // the upper bound of 'i', the compiler cannot prove that the
    // function call "bound()" returns the same value each time.
    // Also, the compiler cannot prove that the call to "bound()"
    // does not modify the values of array A.

    for (int i=0; i<bound(); ++i)
    {
        A[i] = A[i] + 1;
    }

    // To resolve code 501, ensure that the induction variable is
    // a local variable, and ensure that the upper bound is a
    // provably loop invariant value.

    for (int i=0, imax = bound(); i<imax; ++i)
    {
        A[i] = A[i] + 1;
    }
}

int i;
void code_501_example2(int *A)
{
    // Code 501 is emitted if the compiler cannot discern the
    // induction variable of this loop. In this case, 'i' is
    // a global.

    for (i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }

    // To resolve code 501, ensure that the induction variable is
    // a local variable, and ensure that the upper bound is a
    // provably loop invariant value.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

void code_502(int *A)
{
    // Code 502 is emitted if the compiler cannot discern
    // the induction variable of the loop. In this case,
    // there are three increments to "i", one of which
    // is conditional.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
        ++i;

        if (i < 100)
        {
            ++i;
        }
    }

    // To resolve code 502, ensure that there is just one
    // increment of the induction variable, placed in the usual
    // spot in the "for" loop.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

void code_503(int *A, int x)
{
    // Code 503 is emitted if there are inadmissible
    // operations in the loop - for example, exception handling and
    // switch statements.

    for (int i = 0; i<1000; ++i)
    {
        switch (x)
        {
        case 1: A[i] = A[i] + 1;
        case 2: A[i] = A[i] + 2;
        case 3: A[i] = A[i] + 3;
            break;
        }
    }

    // To resolve code 503, try to remove as many switch statements
    // and exception handling constructs as possible.
}

// compile with /EHsc

int code_504_helper();
class C504
{
public:
    C504();
    ~C504();
};

void code_504(int *A)
{
    // Code 504 is emitted if a C++ object was created and
    // that object requires EH unwind tracking information under
    // /EHs or /EHsc.

    for(int i = 0; i < 1000; ++i)
    {
        C504 c;
        A[i] = code_504_helper();
    }

}

void code_505(int *A)
{
    // Code 505 is emitted on outer loops with pre-incremented
    // induction variables. The vectorizer/parallelizer analysis
    // package doesn't support these loops, and they are
    // intentionally not converted to post-increment loops to
    // prevent a performance degradation.

    // To parallelize an outer loop that causes code 505, change
    // it to a post-incremented loop.

    for (int i=100; i--; )
        for (int j=0; j<100; j++) { // this loop is still vectorized
            A[j] = A[j] + 1;
        }                    
}
```

## <a name="10xx-reason-codes"></a><a name="BKMK_ReasonCode100x"></a> 10xx 理由コード

10 *xx* の理由コードが並行化に適用されます。

| 理由コード | 説明 |
|--|--|
| 1000 | コンパイル時にループ本体でデータ依存関係が検出されました。 |
| 1001 | コンパイル時にループ本体でスカラー変数への格納が検出され、そのスカラーがループを超えて使用されています。 |
| 1002 | コンパイル時、内側のループが並列化済みのループが並列化されようとしました。 |
| 1003 | ループ本体にメモリに対して読み取りまたは書き込みを行う組み込みの呼び出しがあります。 |
| 1004 | ループ本体にはスカラーが減少しています。 ループがベクター化されている場合は、スカラー リダクションが発生する可能性があります。 |
| 1005 | `no_parallel`プラグマが指定されました。 |
| 1006 | この関数には、OpenMP が含まれています。 この関数の OpenMP を削除して解決します。 |
| 1007 | ループ誘導変数またはループ境界は、32ビット番号 (または) に符号が付きません `int` `long` 。 これを解決するには、誘導変数の型を変更します。 |
| 1008 | コンパイラは、このループが自動並列化を正当化するのに十分な処理を実行していないことを検出しました。 |
| 1009 | コンパイラは、"" ループを並列化しようとしました `do` - `while` 。 自動並行化は "" ループのみを対象とし `for` ます。 |
| 1010 | コンパイラは、ループが条件に対して "不等号" () を使用していることを検出しました `!=` 。 |

```cpp
int A[1000];
void func();
void code_1000()
{
    // Code 1000 is emitted if the compiler detects a
    // data dependence in the loop body.

    // You can resolve this by using the ivdep pragma.
    // CAUTION -- the compiler will trust your
    // assertion that there are no data dependencies
    // in the loop body. If there are, you are generating
    // code that may have race conditions.

#pragma loop(hint_parallel(0))
    //#pragma loop(ivdep) // ivdep will force this through.
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i-1] + 1;  // data dependence here
        func();             // data dependence here
    }
}

int code_1001()
{
    // Code 1001 is emitted if the compiler detects
    // a store to a scalar variable in the loop
    // body, and that scalar has a use beyond the loop.

    // Resolve this by rewriting your code so
    // that the scalar is not needed.

    int s = 0;
#pragma loop(hint_parallel(0))
    for (int i=0; i<1000; ++i)
    {
        s = A[i];
    }
    return s;
}

void code_1002()
{
    // Code 1002 is emitted when the compiler tries to
    // parallelize a loop that has an inner loop that
    // has already been parallelized.

#pragma loop(hint_parallel(0))
    for (int i=0; i<1000; ++i) // emit code 1002 for this loop
    {
#pragma loop(hint_parallel(0))
        for (int j=0; j<1000; ++j) // this loop gets parallelized
        {
            A[j] = A[j] + 1;
        }
    }
}

extern "C" void __stosb(unsigned char*, unsigned char, size_t);
void code_1003(unsigned char *dst)
{
    // Code 1003 is emitted when the loop body contains an intrinsic
    // call that may read or write to memory.

    // This can be resolved by using the ivdep pragma.
    // CAUTION -- the compiler will trust your
    // assertion that there are no data dependencies
    // in the loop body. If there are, you are generating
    // code that may have race conditions.

#pragma loop(hint_parallel(0))
    //#pragma loop(ivdep) // ivdep will force this through.
    for (int i=0; i<1000; ++i)
    {
        __stosb(dst, 'c', 10);
        A[i] = A[i] + 1;
    }
}

int code_1004()
{
    // Code 1004 is emitted when there is a scalar reduction
    // in the loop body, which can occur if the loop has been
    // vectorized.

    // You can resolve this by rewriting your code so that it
    // does not have a scalar reduction.

    int s = 0;
#pragma loop(hint_parallel(0))
    for (int i=0; i<1000; ++i)
    {
        s += A[i];
    }
    return s;
}

void code_1005()
{
    // Code 1005 is emitted when the
    // no_parallel pragma is specified.

#pragma loop(no_parallel)
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

#include <omp.h>

// Compile with /openmp
void code_1006()
{
    // Code 1006 is emitted when this function contains
    // openmp. Resolve this by removing any openmp in this
    // function.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }

#pragma omp parallel num_threads(4)
    {
        int i = omp_get_thread_num();
        A[i] = A[i] + 1;
    }
}

void code_1007()
{
    // Code 1007 is emitted when the loop induction variable
    // or the loop bounds are not signed 32-bit numbers (int
    // or long). Resolve this by changing the type of the
    // induction variable.

#pragma loop(hint_parallel(0))
    for (unsigned int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

void code_1008()
{
    // Code 1008 is emitted when the compiler detects that
    // this loop does not perform enough work to warrant
    // auto-parallelization.

    // You can resolve this by specifying the hint_parallel
    // pragma. CAUTION -- if the loop does not perform
    // enough work, parallelizing might cause a potentially
    // large performance penalty.

    // #pragma loop(hint_parallel(0)) //  hint_parallel will force this through
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

void code_1009()
{
    // Code 1009 is emitted when the compiler tries to parallelize a
    // "do-while" loop. The auto-parallelizer only targets "for" loops.

    int i = 0;
#pragma loop(hint_parallel(0))
    do
    {
        A[i] = A[i] + 1;
    }
    while (++i < 1000);
}

void code_1010()
{
    // Code 1010 is emitted when the compiler tries to parallelize a
    // loop with a condition code of "!=".

    // You can resolve this by replacing it with an ordering comparator
    // like "<".
#pragma loop(hint_parallel(0))
    for (int i = 0; i != 1000; ++i)
    {
        A[i]++;
    }
}
```

## <a name="11xx-reason-codes"></a><a name="BKMK_ReasonCode110x"></a> 11xx 理由コード

11 *xx* の理由コードは、ベクター化に適用されます。

| 理由コード | 説明 |
|--|--|
| 1100 | Loop には、"" や "" などの制御フローが含まれてい `if` `?:` ます。 |
| 1101 | ループには、ベクター化できない (暗黙的な) データ型変換が含まれています。 |
| 1102 | ループ内に算術以外またはベクター化以外の演算があります。 |
| 1103 | ループ本体にサイズがループ内で可変する場合があるシフト操作があります。 |
| 1104 | ループ本体にスカラー変数があります。 |
| 1105 | ループには、認識できないリダクション操作が含まれています。 |
| 1106 | 外側のループがベクター化されていません。 |

```cpp
void code_1100(int *A, int x)
{
    // Code 1100 is emitted when the compiler detects control flow
    // in the loop - for example, "if", the ternary operator "?", and
    // the like. Resolve this by flattening or removing control
    // flow in the loop body.

    // Not all control flow causes 1100; some is indeed
    // vectorized.

    for (int i=0; i<1000; ++i)
    {
        // straight line code is more amenable to vectorization
        if (x)
        {
            A[i] = A[i] + 1;
        }
    }
}

extern "C" int __readcr0();
void code_1102(int *A)
{
    // Code 1102 is emitted when the compiler is unable to vectorize
    // an operation in the loop body. For example, intrinsics and other
    // non-arithmetic, non-logical, and non-memory operations are not
    // vectorizable.

    // Resolve this by removing as many non-vectorizable operations
    // as possible from the loop body.

    for (int i=0; i<1000; ++i)
    {
        A[i] = __readcr0();
    }
}

void code_1103(int *A, int *B)
{
    // Code 1103 is emitted when the compiler is unable to vectorize
    // a "shift" operation. In this example, there are two shifts
    // that cannot be vectorized.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] >> B[i]; // not vectorizable

        int x = B[i];
        A[i] = A[i] >> x; // not vectorizable
    }

    // To resolve this, ensure that your shift amounts are loop
    // invariant. If the shift amounts cannot be loop invariant,
    // it may not be possible to vectorize this loop.

    int x = B[0];
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] >> x; // vectorizable
    }
}

int code_1104(int *A, int *B)
{
    // When it vectorizes a loop, the compiler must 'expand' scalar
    // variables to a vector size such that they can fit in
    // vector registers. Code 1104 is emitted when the compiler
    // cannot 'expand' such scalars.

    // In this example, we try to 'expand' x to be used in the
    // vectorized loop. However, there is a use of 'x'
    // beyond the loop body, which prohibits this expansion.

    // To resolve this, try to limit scalars to be used only in
    // the loop body and not beyond, and try to keep their types
    // consistent with the loop types.

    int x;
    for (int i=0; i<1000; ++i)
    {
        x = B[i];
        A[i] = A[i] + x;
    }

    return x;
}

int code_1105(int *A)
{
    // The compiler performs an optimization that's known as "reduction"
    // when it operates on each element of an array and computes
    // a resulting scalar value - for example, in this piece of code, which
    // computes the sum of each element in the array:

    int s = 0;
    for (int i=0; i<1000; ++i)
    {
        s += A[i]; // vectorizable
    }

    // The reduction pattern must resemble the loop in the example. The
    // compiler emits code 1105 if it cannot deduce the reduction
    // pattern, as shown in this example:

    for (int i=0; i<1000; ++i)
    {
        s += A[i] + s;  // code 1105
    }

    // Similarly, reductions of "float" or "double" types require
    // that the /fp:fast switch is thrown. Strictly speaking,
    // the reduction optimization that the compiler performs uses
    // "floating point reassociation". Reassociation is only
    // allowed when /fp:fast is thrown.

    return s;
}

void code_1106(int *A)
{
    // Code 1106 is emitted when the compiler tries to vectorize
    // an outer loop.

    for (int i=0; i<1000; ++i) // this loop is not vectorized
    {
        for (int j=0; j<1000; ++j) // this loop is vectorized
        {
            A[j] = A[j] + 1;
        }
    }
}
```

## <a name="12xx-reason-codes"></a><a name="BKMK_ReasonCode120x"></a> 12 xx 理由コード

12 *xx* 理由コードは、ベクター化に適用されます。

| 理由コード | 説明 |
|--|--|
| 1200 | ループは、ベクター化を妨げるループを実行するデータの依存関係を含んでいます。 ループの反復回数が異なれば、ループの vectorizing が間違った回答を生成するようになり、自動ベクター化はそのようなデータの依存関係がないということを証明できません。 |
| 1201 | ループ中に配列ベースの変更がありました。 |
| 1202 | 構造体のフィールドが32または64ビット幅ではありません。 |
| 1203 | ループ本体に配列への連続しないアクセスがあります。 |
| 1204 | コンパイラの内部データ構造の制限に達しました。データに依存するエッジが多すぎます。 |

```cpp
void fn();
void code_1200(int *A)
{
    // Code 1200 is emitted when data dependence is prohibiting
    // vectorization. This can only be resolved by rewriting the
    // loop, and considering the marking of loop function calls as
    // __forceinline.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i-1] + 1; // vectorization-prohibiting
        fn();               // vectorization-prohibiting
    }
}

void code_1201(int *A)
{
    // Code 1201 is emitted when an array base changes
    // in the loop body. Resolve this by rewriting your
    // code so that varying the array base is not necessary.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
        A++;
    }
}

struct S_1202
{
    short a;
    short b;
} s[1000];

short sA[1000], sB[1000], sC[1000];

void code_1202(S_1202 *s)
{
    // Code 1202 is emitted when non-vectorizable struct accesses
    // are present in the loop body. Only struct accesses
    // that are 32 or 64 bits are vectorized.

    for (int i=0; i<1000; ++i)
    {
        s[i].a = s[i].b + 1; // this 16 bit struct access is not vectorizable
        sA[i] += sB[i] * sC[i]; // this ensures we don't emit reason code '1300'
    }
}

void code_1203(int *A)
{
    // Code 1203 is emitted when non-vectorizable memory references
    // are present in the loop body. Vectorization of some non-contiguous
    // memory access is supported - for example, the gather/scatter pattern.

    for (int i=0; i<1000; ++i)
    {
        A[i] += A[0] + 1;       // constant memory access not vectorized
        A[i] += A[i*2+2] + 2;  // non-contiguous memory access not vectorized
    }
}

void code_1204(int *A)
{
    // Code 1204 is emitted when internal compiler data structures
    // hit a limit on the number of data dependence edges recorded.
    // Resolve this by moving the innermost loop to another function.

    for (int i=0; i<1000; i++)
        for (int j=0; j<1000; j++)
            for (int k=0; k<1000; k++)
                for (int l=0; l<1000; l++)
                {
                    for (int m=0; m<1000; m++)
                        A[m] = A[m+i] + A[m+j] + A[m+k] + A[m+l];
                }
}
```

## <a name="13xx-reason-codes"></a><a name="BKMK_ReasonCode130x"></a> 13xx 理由コード

13 *xx* の理由コードは、ベクター化に適用されます。

| 理由コード | 説明 |
|--|--|
| 1300 | ループ本体には計算がほとんど含まれていません。 |
| 1301 | ループストライドが + 1 ではありません。 |
| 1302 | Loop は " `do` - `while` " です。 |
| 1303 | 値を出力するにはベクター化のループの繰り返し回数が少なすぎます。 |
| 1304 | ループ内にサイズが異なる代入があります。 |
| 1305 | 型情報が不足しています。 |

```cpp
void code_1300(int *A, int *B)
{
    // Code 1300 is emitted when the compiler detects that there is
    // no computation in the loop body.

    for (int i=0; i<1000; ++i)
    {
        A[i] = B[i]; // Do not vectorize, instead emit memcpy
    }
}

void code_1301(int *A)
{
    // Code 1301 is emitted when the stride of a loop is not positive 1.
    // Only loops that have a stride of positive 1 are vectorized;
    // rewriting your loop may be required.

    for (int i=0; i<1000; i += 2)
    {
        A[i] = A[i] + 1;
    }
}

void code_1302(int *A)
{
    // Code 1302 is emitted for "do-while" loops. Only "while"
    // and "for" loops are vectorized.

    int i = 0;
    do
    {
        A[i] = A[i] + 1;
    } while (++i < 1000);
}

int code_1303(int *A, int *B)
{
    // Code 1303 is emitted when the compiler detects that
    // the number of iterations of the loop is too small to
    // make vectorization profitable.

    // If the loop computation fits perfectly in
    // vector registers - for example, the upper bound is 4, or 8 in
    // this case - then the loop _may_ be vectorized.

    // This loop is not vectorized because there are 5 iterations

    for (int i=0; i<5; ++i)
    {
        A[i] = A[i] + 1;
    }

    // This loop is vectorized

    for (int i=0; i<4; ++i)
    {
        A[i] = A[i] + 1;
    }

    // This loop is not vectorized because runtime pointer checks
    // are required to check that A and B don't overlap. It is not
    // worth it to vectorize this loop.

    for (int i=0; i<4; ++i)
    {
        A[i] = B[i] + 1;
    }

    // This loop is not vectorized because of the scalar reduction.

    int s = 0;
    for (int i=0; i<4; ++i)
    {
        s += A[i];
    }
    return s;
}

void code_1304(int *A, short *B)
{
    // Code 1304 is emitted when the compiler detects
    // different sized statements in the loop body.
    // In this case, there is an 32-bit statement and a
    // 16-bit statement.

    // In cases like this consider splitting the loop into loops to
    // maximize vector register utilization.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
        B[i] = B[i] + 1;
    }
}

typedef struct S_1305
{
    int a;
    int b;
} S_1305;

void code_1305( S_1305 *s, S_1305 x)
{
    // Code 1305 is emitted when the compiler can't discern
    // proper vectorizable type information for this loop.
    // This includes non-scalar loop types such as struct
    // assignments, as in this example.

    // Resolve this by ensuring that your loops have statements
    // that operate on integers or floating point types.

    for (int i=0; i<1000; ++i)
    {
        s[i] = x;
    }
}
```

## <a name="14xx-reason-codes"></a><a name="BKMK_ReasonCode140x"></a> 14xx 理由コード

14 *xx* 理由コードは、ベクター化と互換性のないオプションが指定されている場合に発生します。

| 理由コード | 説明 |
|--|--|
| 1400 | `#pragma loop(no_vector)` が指定されています。 |
| 1401 | `/kernel`x86 または ARM を対象とするとき、 スイッチが指定されています。 |
| 1402 | `/arch:SSE2` x86 を対象とする場合、またはそれ以上のスイッチが指定されていません。 |
| 1403 | `/arch:ATOM` switch が指定されており、ループに double に対する操作が含まれています。 |
| 1404 | `/O1` または `/Os` スイッチが指定されています。 |
| 1405 | ベクター化が動的初期化子と静的初期化子との間の最適化用に無効になっています。 |

```cpp
void code_1400(int *A)
{
    // Code 1400 is emitted when the no_vector pragma
    // is specified.

#pragma loop(no_vector)
    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

// Compile with /kernel
void code_1401(int *A)
{
    // Code 1401 is emitted when /kernel is specified.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

// Compile with /arch:IA32
void code_1402(int *A)
{
    // Code 1401 is emitted when /arch:IA32 is specified.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

// Compile with /favor:ATOM
void code_1403(double *A)
{
    // Code 1401 is emitted when /favor:ATOM is specified, and
    // the loop contains operations on "double" arrays.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}

// Compile with /O1 or /Os
void code_1404(int *A)
{
    // Code 1401 is emitted when compiling for size.

    for (int i=0; i<1000; ++i)
    {
        A[i] = A[i] + 1;
    }
}
```

## <a name="15xx-reason-codes"></a><a name="BKMK_ReasonCode150x"></a> 15xx 理由コード

15 *xx* 理由コードはエイリアスに適用されます。 メモリ内の同じ位置に 2 つの異なる名前でアクセスできるときにエイリアスが使用されます。

| 理由コード | 説明 |
|--|--|
| 1500 | 多次元配列でエイリアスが使用されている可能性があります。 |
| 1501 | 構造体の配列でエイリアスが使用されている可能性があります。 |
| 1502 | 使用可能なエイリアスと配列インデックスは n + K 以外です。 |
| 1503 | 使用可能なエイリアスと配列インデックスに複数のオフセットがあります。 |
| 1504 | エイリアスが使用されている可能性があります。要求される実行時チェックが多すぎます。 |
| 1505 | エイリアスが使用されている可能性がありますが、実行時チェックが複雑すぎます。 |

```cpp
void code_1500(int A[100][100], int B[100][100])
{
    // Code 1500 is emitted when runtime pointer
    // disambiguation checks are required, and
    // there are multidimensional array references.

    for (int i=0; i<100; ++i)
    {
        for (int j=0; j<100; ++j)
        {
            A[i][j] = B[i][j] + 1;
        }
    }
}

typedef struct S_1501
{
    int a;
    int b;
} S_1501;

int iA[1000], iB[1000], iC[1000];

void code_1501(S_1501 *s1, S_1501 *s2)
{
    // Code 1501 is emitted when runtime pointer
    // disambiguation checks are required, and
    // there are array-of-struct accesses in the
    // loop body.

    for (int i=0; i<100; ++i)
    {
        s1[i].a = s2[i].b + 1;
        iA[i] += iB[i] * iC[i]; // this is to ensure we don't emit reason code '1300'
    }
}

void code_1502(int *A, int *B)
{
    // Code 1502 is emitted when runtime pointer
    // disambiguation checks are required, and
    // an array reference has an offset that varies
    // in the loop.

    int x = 0;
    for (int i=0; i<100; ++i)
    {
        A[i] = B[i + x] + 1;
        ++x;                   // 'x' varies in the loop
    }
}

void code_1503(int *A, int *B, int x, int y)
{
    // Code 1503 is emitted when runtime pointer
    // disambiguation checks are required, and
    // an array reference has multiple offsets.

    for (int i=0; i<100; ++i)
    {
        A[i] = B[i+x] + B[i+y] + 1;   // multiple offsets when addressing 'B': {x, y}
        A[i] = B[i+x] + B[i] + 1;     // multiple offsets when addressing 'B': {x, 0}
        A[i] = B[i+x] + B[i+x] + 1;   // this is vectorized
    }
}

void code_1504(int *A1, int *A2, int *A3, int *A4,
               int *A5, int *A6, int *A7, int *A8,
               int *A9, int *A10, int *A11, int *A12,
               int *A13, int *A14, int *A15, int *A16)
{
    // Code 1504 is emitted when too many runtime
    // pointer disambiguation checks are required.

    for (int i=0; i<100; ++i)
    {
        ++A1[i];
        ++A2[i];
        ++A3[i];
        ++A4[i];
        ++A5[i];
        ++A6[i];
        ++A7[i];
        ++A8[i];
        ++A9[i];
        ++A10[i];
        ++A11[i];
        ++A12[i];
        ++A13[i];
        ++A14[i];
        ++A15[i];
        ++A16[i];
    }
}

void code_1505(int *A, int *B)
{
    // Code 1505 is emitted when runtime pointer
    // disambiguation checks are required, but are
    // too complex for the compiler to discern.

    for (int i=0; i<100; ++i)
    {
        for (int j=0; j<100; ++j)
        {
            for (int k=0; k<100; ++k)
            {
                A[i+j-k] = B[i-j+k] * 2;
            }
        }
    }
}
```

## <a name="see-also"></a>関連項目

[C/c + + コンパイラおよびビルドツールのエラーと警告](../compiler-errors-1/c-cpp-build-errors.md)\
[自動並列化と自動ベクター化](../../parallel/auto-parallelization-and-auto-vectorization.md)\
[Visual Studio 2012 での自動ベクター化–概要](/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)\
[`#pragma loop()`](../../preprocessor/loop.md)\
[`/Q` オプション (低レベルの操作)](../../build/reference/q-options-low-level-operations.md)\
[`/Qpar-report` (自動並行化レポートレベル)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)\
[`/Qvec-report` (自動ベクター化レポートレベル)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)
