---
title: /fp (浮動小数点の動作の指定)
ms.date: 11/09/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
ms.openlocfilehash: 402b59c4aee34a413a08235aab2327ca64e7db39
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439679"
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (浮動小数点の動作の指定)

コンパイラが浮動小数点式、最適化、および例外をどのように処理するかを指定します。 **/Fp**オプションでは、生成されたコードで浮動小数点環境を丸めモード、例外マスク、subnormal の動作に変更できるかどうか、および浮動小数点の状態チェックで現在の正確な結果が返されるかどうかを指定します。 これは、ソース操作と式の順序を維持し、NaN の伝達の標準に準拠するコードをコンパイラが生成するかどうかを制御します。または、代わりに操作を並べ替えたり結合したりするためのより効率的なコードを生成するかどうかを制御します標準で許可されていない代数変換。

## <a name="syntax"></a>構文

> **/fp:** [**正確** | **strict** | **fast** | [ **-** ]] を**除く**

### <a name="arguments"></a>引数

#### <a name="precise"></a>詳しい

既定では、コンパイラは `/fp:precise` 動作を使用します。

`/fp:precise` 下では、コンパイラは、ターゲットコンピューターのオブジェクトコードを生成および最適化するときに、浮動小数点コードのソース式の順序と丸めのプロパティを保持します。 コンパイラは、式の評価中に、割り当て時、typecasts 時、浮動小数点引数が関数呼び出しに渡されたとき、および関数呼び出しから浮動小数点値が返されたときに、ソースコードの有効桁数に丸めます。 中間計算は、コンピューターの精度で実行できます。 Typecasts を使用して、中間計算を明示的に丸めることができます。

変換によってビットごとの同一の結果が生成される場合を除き、再関連付けや distribution などの浮動小数点式では、コンパイラは代数変換を実行しません。
特殊な値 (NaN、+ 無限大、-無限大、-0.0) を含む式は、IEEE-754 仕様に従って処理されます。 たとえば、x が NaN の場合、`x != x` は**true**に評価されます。 浮動小数点の*短縮形*(浮動小数点演算を結合するマシン命令) は、`/fp:precise`の下で生成される場合があります。

コンパイラは、[既定の浮動](#the-default-floating-point-environment)小数点環境での実行を意図したコードを生成します。また、浮動小数点環境が実行時にアクセスまたは変更されないことを前提としています。 つまり、このコードでは、浮動小数点例外のマスク解除、浮動小数点ステータスレジスタの読み取りまたは書き込み、または丸めモードの変更を行わないことを前提としています。

浮動小数点コードが浮動小数点ステートメントの演算および式の順序に依存していない場合 (たとえば、`a * b + a * c` が `(b + c) * a` として計算されるか、`a + a`として `2 * a` されるかを気にしない場合は、 [/fp: fast](#fast)オプションを検討してください。これにより、より高速で効率的なコードを生成できます。 コードが演算と式の順序に依存していて、浮動小数点環境にアクセスしたり変更したりする場合 (丸めモードを変更する場合や、浮動小数点例外をトラップする場合など) は、 [/fp: strict](#strict)を使用します。

#### <a name="strict"></a>strict

`/fp:strict` には `/fp:precise`と同様の動作があります。つまり、ターゲットコンピューターのオブジェクトコードを生成および最適化するときに、コンパイラは浮動小数点コードのソースの順序付けと丸めのプロパティを保持し、特別な値を処理するときに標準を監視します。 また、プログラムは実行時に、浮動小数点環境に安全にアクセスしたり、変更したりする可能性があります。

`/fp:strict`では、コンパイラは、プログラムが浮動小数点例外のマスク解除、浮動小数点ステータスレジスタの読み取りまたは書き込み、または丸めモードの変更を安全に行うコードを生成します。 これは、式の評価中に、割り当て時、typecasts 時、浮動小数点引数が関数呼び出しに渡されたとき、および関数呼び出しから浮動小数点値が返されたときに、4つの特定のポイントでソースコードの有効桁数に丸められます。 中間計算は、コンピューターの精度で実行できます。 Typecasts を使用して、中間計算を明示的に丸めることができます。 変換によってビットごとの同一の結果が生成される場合を除き、再関連付けや distribution などの浮動小数点式では、コンパイラは代数変換を実行しません。 特殊な値 (NaN、+ 無限大、-無限大、-0.0) を含む式は、IEEE-754 仕様に従って処理されます。 たとえば、x が NaN の場合、`x != x` は**true**に評価されます。 浮動小数点短縮形は、`/fp:strict`の下では生成されません。

コンパイラは例外をトラップし、プログラムが実行時に浮動小数点環境にアクセスしたり変更したりできるようにするために、追加の命令を挿入する必要があるため、`/fp:precise` よりも計算の負荷が大きく `/fp:strict` ます。 コードがこの機能を使用せず、ソースコードの順序付けと丸め処理を必要とする場合、または特殊な値に依存する場合は、`/fp:precise`を使用します。 それ以外の場合は、`/fp:fast`を使用することを検討してください。これにより、より高速で小さなコードを生成できます

#### <a name="fast"></a>fast

`/fp:fast` オプションを使用すると、コンパイラは、浮動小数点演算を順序変更、結合、または簡略化して、浮動小数点コードを最適化し、速度と領域を確保することができます。 コンパイラは、代入ステートメント、typecasts、または関数呼び出しで丸め処理を省略できます。 このような変換では、著しいの丸め動作が異なる場合でも、操作の順序を変更したり、代数変換を実行したりすることがあります。 この強化された最適化のため、一部の浮動小数点計算の結果は、他の `/fp` オプションで生成されるものとは異なる場合があります。 特殊な値 (NaN、+ 無限大、-無限大、-0.0) は、IEEE-754 標準に従って厳密に伝達または動作しない可能性があります。 浮動小数点短縮形は、`/fp:fast`の下で生成される場合があります。 コンパイラは、`/fp:fast`の下の基になるアーキテクチャによってバインドされています。また、 [/arch](arch-minimum-cpu-architecture.md)オプションを使用して追加の最適化を行うこともできます。

`/fp:fast`では、コンパイラは、既定の浮動小数点環境で実行するためのコードを生成し、実行時に浮動小数点環境にアクセスしたり変更したりしないことを前提としています。 つまり、このコードでは、浮動小数点例外のマスク解除、浮動小数点ステータスレジスタの読み取りまたは書き込み、または丸めモードの変更を行わないことを前提としています。

`/fp:fast` は、厳密なソースコードの順序付けと浮動小数点式の丸めを必要としないプログラムを対象としており、NaN などの特別な値を処理するための標準の規則に依存しません。 浮動小数点コードでソースコードの順序付けと丸めを行う必要がある場合、または特殊な値の標準動作に依存する場合は、 [/fp: 精密](#precise)を使用します。 丸めモードを変更する、浮動小数点例外をマスク解除する、または浮動小数点の状態をチェックするために、コードが浮動小数点環境にアクセスまたは変更する場合は、 [/fp: strict](#strict)を使用します。

#### <a name="except"></a>ば

`/fp:except` オプションを使用すると、マスクされていない浮動小数点例外が発生した位置で確実に発生し、追加の浮動小数点例外が発生しないようにするためのコードが生成されます。 既定では、`/fp:strict` オプションは `/fp:except`を有効にし、`/fp:precise` は有効にしません。 `/fp:except` オプションは `/fp:fast`と互換性がありません。 このオプションは、`/fp:except-`によって明示的に無効にすることができます。

`/fp:except` では、浮動小数点例外自体が有効になるわけではありませんが、プログラムで浮動小数点例外を有効にする必要があることに注意してください。 浮動小数点例外を有効にする方法については、「 [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) 」を参照してください。

## <a name="remarks"></a>コメント

複数の `/fp` オプションは、同じコンパイラのコマンドラインで指定できます。 `/fp:strict`、`/fp:fast`、および `/fp:precise` のオプションは、一度に1つしか有効にできません。 これらのオプションのいずれかがコマンドラインで指定されている場合、後のオプションが優先され、コンパイラによって警告が生成されます。 `/fp:strict` オプションと `/fp:except` オプションは `/clr`と互換性がありません。

[/Za](za-ze-disable-language-extensions.md) (ANSI compatibility) オプションは `/fp`と互換性がありません。

### <a name="using-compiler-directives-to-control-floating-point-behavior"></a>コンパイラディレクティブを使用した浮動小数点動作の制御

コンパイラには、コマンドラインで指定された浮動小数点動作をオーバーライドするために、 [float_control](../../preprocessor/float-control.md)、 [fenv_access](../../preprocessor/fenv-access.md)、および[fp_contract](../../preprocessor/fp-contract.md)の3つのプラグマディレクティブが用意されています。 これらのディレクティブを使用すると、関数内ではなく、関数レベルで浮動小数点動作を制御できます。 これらのディレクティブは、`/fp` オプションに直接対応していないことに注意してください。 次の表は、`/fp` オプションとプラグマディレクティブが相互にどのようにマップされるかを示しています。 詳細については、個々のオプションとプラグマディレクティブのドキュメントを参照してください。

||float_control (正確)|float_control (除く)|fenv_access|fp_contract|
|-|-|-|-|-|
|`/fp:fast`|オフ|オフ|オフ|上の|
|`/fp:precise`|上の|オフ|オフ|上の|
|`/fp:strict`|上の|上の|上の|オフ|

### <a name="the-default-floating-point-environment"></a>既定の浮動小数点環境

プロセスが初期化されると、*既定の浮動小数点環境*が設定されます。 この環境では、すべての浮動小数点例外がマスクされ、丸めモードが [近似値に丸め] (`FE_TONEAREST`) に設定され、subnormal (denormal) 値が保持されます。また、 **float**、 **double**、および**long double 型**の値に対して有効桁 (仮数) の既定の有効桁数を使用し、サポートされている場合は、無限大

### <a name="floating-point-environment-access-and-modification"></a>浮動小数点環境へのアクセスと変更

Microsoft Visual C++ runtime には、浮動小数点環境にアクセスして変更するための関数がいくつか用意されています。 これには、 [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md)、 [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)、 [_statusfp](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)とそのバリエーションが含まれます。 コードが浮動小数点環境にアクセスまたは変更したときに正しいプログラム動作を保証するには、これらの関数が何らかの影響を及ぼすように、`/fp:strict` オプションまたは `fenv_access` プラグマを使用して `fenv_access` を有効にする必要があります。 `fenv_access` が有効になっていない場合、浮動小数点環境のアクセスまたは変更によって予期しないプログラムの動作が発生する可能性があります。コードが浮動小数点環境に対する要求された変更を反映しないことがあります。浮動小数点ステータスレジスタは、予期される結果や現在の結果を報告しない場合があります。予期しない浮動小数点例外が発生したり、予期しない浮動小数点例外が発生したりすることがあります。

コードが浮動小数点環境にアクセスしたり変更したりする場合は、`fenv_access` が有効になっているコードと `fenv_access` が有効になっていないコードを結合するときに注意する必要があります。 `fenv_access` が有効になっていないコードでは、コンパイラは、プラットフォームの既定の浮動小数点環境が有効であること、および浮動小数点の状態がアクセスまたは変更されないことを前提としています。 `fenv_access` が有効になっていない関数に制御が転送される前に、ローカルの浮動小数点環境を既定の状態に保存して復元することをお勧めします。 この例では、`float_control` プラグマを設定および復元する方法を示します。

```cpp
#pragma float_control(strict, on, push)
// Code that uses /fp:strict mode
#pragma float_control(pop)
```

### <a name="floating-point-rounding-modes"></a>浮動小数点丸めモード

`/fp:precise` と `/fp:fast` の両方で、コンパイラは既定の浮動小数点環境での実行を意図したコードを生成し、実行時に環境がアクセスまたは変更されないことを前提としています。 つまり、このコードでは、浮動小数点例外のマスク解除、浮動小数点ステータスレジスタの読み取りまたは書き込み、または丸めモードの変更を行わないことを前提としています。  ただし、一部のプログラムでは、浮動小数点環境を変更する必要があります。 たとえば、次のサンプルでは、浮動小数点丸めモードを変更することによって、浮動小数点の乗算の誤差範囲を計算します。

```cpp
// fp_error_bounds.cpp
#include <iostream>
#include <limits>
using namespace std;

int main(void)
{
    float a = std::<float>::max();
    float b = -1.1;
    float cLower = 0.0;
    float cUpper = 0.0;
    unsigned int control_word = 0;
    int err = 0;

    // compute lower error bound.
    // set rounding mode to -infinity.
    err = _controlfp_s(&control_word, _RC_DOWN, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _RC_DOWN, _MCW_RC) failed with error:" << err << endl;
    }  
    cLower = a * b;

    // compute upper error bound.
    // set rounding mode to +infinity.
    err = _controlfp_s(&control_word, _RC_UP, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _RC_UP, _MCW_RC) failed with error:" << err << endl;
    }
    cUpper = a * b;

    // restore default rounding mode.
    err = _controlfp_s(&control_word, _CW_DEFAULT, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _CW_DEFAULT, _MCW_RC) failed with error:" << err << endl;
    }
    // display error bounds.
    cout << "cLower = " << cLower << endl;
    cout << "cUpper = " << cUpper << endl;
    return 0;
}
```

コンパイラは `/fp:fast` と `/fp:precise` の既定の浮動小数点環境を前提としているため、`_controlfp_s`の呼び出しを無視してもかまいません。 たとえば、x86 アーキテクチャで `/O2` と `/fp:precise` の両方を使用してコンパイルした場合、境界は計算されず、サンプルプログラムによって出力されます。

```Output
cLower = -inf
cUpper = -inf
```

X86 アーキテクチャの `/O2` と `/fp:strict` の両方を使用してコンパイルすると、サンプルプログラムによって次のように出力されます。

```Output
cLower = -inf
cUpper = -3.40282e+38
```

### <a name="floating-point-special-values"></a>浮動小数点特殊値

`/fp:precise` と `/fp:strict`では、特殊な値 (NaN、+ 無限大、-無限大、-0.0) を含む式は、IEEE-754 仕様に従って動作します。 `/fp:fast`では、これらの特殊な値の動作が IEEE-754 と矛盾している可能性があります。

このサンプルでは、`/fp:precise`、`/fp:strict` および `/fp:fast`での特殊な値のさまざまな動作を示します。

```cpp
// fp_special_values.cpp
#include <stdio.h>
#include <cmath>

float gf0 = -0.0;

int main()
{
    float f1 = INFINITY;
    float f2 = NAN;
    float f3 = -INFINITY;
    bool a, b;
    float c, d, e;
    a = (f1 == f1);
    b = (f2 == f2);
    c = (f1 - f1);
    d = (f2 - f2);
    printf("INFINITY == INFINITY : %d\n", a);
    printf("NAN == NAN           : %d\n", b);
    printf("INFINITY - INFINITY  : %f\n", c);
    printf("NAN - NAN            : %f\n", d);

    e = gf0 / abs(f3);
    printf("std::signbit(-0.0/-INFINITY): %d\n", std::signbit(c));
    return 0;
}
```

X86 アーキテクチャで `/O2` `/fp:precise` または `/O2` `/fp:strict` を使用してコンパイルした場合、出力は IEEE-754 仕様と一致します。

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 0
INFINITY - INFINITY  : -nan(ind)
NAN - NAN            : -nan(ind)
std::signbit(-0.0/-INFINITY): 1
```

X86 アーキテクチャで `/O2` `/fp:fast` を使用してコンパイルした場合、出力は IEEE-754 と一致しません。

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 1
INFINITY - INFINITY  : 0.000000
NAN - NAN            : 0.000000
std::signbit(-0.0/-INFINITY): 0
```

### <a name="floating-point-algebraic-transformations"></a>浮動小数点の代数変換

`/fp:precise` と `/fp:strict`では、変換によってビットごとの同一の結果が生成されることが保証されない限り、コンパイラは数学的変換を実行しません。 コンパイラは、`/fp:fast`の下でこのような変換を実行できます。 たとえば、サンプル関数 `algebraic_transformation` 内の `a * b + a * c` 式は `/fp:fast`下の `a * (b + c)` にコンパイルされる場合があります。 このような変換は `/fp:precise` または `/fp:strict`では実行されず、コンパイラによって `a * b + a * c`が生成されます。

```cpp
float algebraic_transformation (float a, float b, float c)
{
    return a * b + a * c;
}
```

### <a name="floating-point-explicit-casting-points"></a>浮動小数点の明示的なキャストポイント

`/fp:precise` と `/fp:strict`では、コンパイラは、式の評価中に、typecasts、浮動小数点引数が関数呼び出しに渡されたとき、および関数呼び出しから浮動小数点値が返されたときに、ソースコードの有効桁数に丸めます。 Typecasts を使用して、中間計算を明示的に丸めることができます。 `/fp:fast`では、コンパイラは、ソースコードの精度を保証するために、これらのポイントで明示的なキャストを生成しません。 このサンプルでは、さまざまな `/fp` オプションの動作を示します。

```cpp
float casting(float a, float b)
{
    return 5.0*((double)(a+b));
}
```

`/O2` `/fp:precise` または `/O2` `/fp:strict`を使用してコンパイルした場合は、x64 アーキテクチャ用に生成されたコードの型キャストと関数の戻り値の両方に明示的な型キャストが挿入されていることがわかります。

```asm
        addss    xmm0, xmm1
        cvtss2sd xmm0, xmm0
        mulsd    xmm0, QWORD PTR __real@4014000000000000
        cvtsd2ss xmm0, xmm0
        ret      0
```

`/fp:fast` `/O2` では、すべての型キャストが最適化されるため、生成されたコードは簡略化されます。

```asm
        addss    xmm0, xmm1
        mulss    xmm0, DWORD PTR __real@40a00000
        ret      0
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関する記事を参照してください。

1. **[構成プロパティ]**  > [ **CC++ /**  > **コード生成**] プロパティページを選択します。

1. **浮動小数点モデル**のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>) をご覧ください。

## <a name="see-also"></a>参照

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
 