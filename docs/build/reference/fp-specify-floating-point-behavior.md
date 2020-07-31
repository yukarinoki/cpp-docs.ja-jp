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
ms.openlocfilehash: f85f9b397ef3ab5bd070be1f4c81845405b14020
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234381"
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (浮動小数点の動作の指定)

コンパイラが浮動小数点式、最適化、および例外をどのように処理するかを指定します。 **/Fp**オプションでは、生成されたコードで浮動小数点環境を丸めモード、例外マスク、subnormal の動作に変更できるかどうか、および浮動小数点の状態チェックで現在の正確な結果が返されるかどうかを指定します。 このメソッドは、ソース操作と式の順序を維持し、NaN の伝達の標準に準拠するコードをコンパイラで生成するかどうかを制御します。または、代わりに、操作を並べ替えたり結合したり、標準で許可されていない代数変換を簡略化したりすることができる、より効率的なコードを生成します。

## <a name="syntax"></a>構文

> **/fp:** [**precise** | **strict** | **fast** | **except**[-]]

### <a name="arguments"></a>引数

#### <a name="precise"></a>precise

既定では、コンパイラは `/fp:precise` 動作を使用します。

`/fp:precise`コンパイラは、ターゲットコンピューターのオブジェクトコードを生成して最適化するときに、浮動小数点コードのソース式の順序付けおよび丸めプロパティを保持します。 コンパイラは、式の評価中に、割り当て時、typecasts 時、浮動小数点引数が関数呼び出しに渡されたとき、および関数呼び出しから浮動小数点値が返されたときに、ソースコードの有効桁数に丸めます。 中間計算は、コンピューターの精度で実行できます。 Typecasts を使用して、中間計算を明示的に丸めることができます。

変換によってビットごとの同一の結果が生成される場合を除き、再関連付けや distribution などの浮動小数点式では、コンパイラは代数変換を実行しません。
特殊な値 (NaN、+ 無限大、-無限大、-0.0) を含む式は、IEEE-754 仕様に従って処理されます。 たとえば、 `x != x` x が NaN の場合、はに評価され **`true`** ます。 浮動小数点の*短縮形*(浮動小数点演算を組み合わせたコンピューター命令) は、の下で生成される場合があり `/fp:precise` ます。

コンパイラは、[既定の浮動](#the-default-floating-point-environment)小数点環境での実行を意図したコードを生成します。また、浮動小数点環境が実行時にアクセスまたは変更されないことを前提としています。 つまり、このコードでは、浮動小数点例外のマスク解除、浮動小数点ステータスレジスタの読み取りまたは書き込み、または丸めモードの変更を行わないことを前提としています。

浮動小数点コードが浮動小数点ステートメントの演算および式の順序に依存しない場合 (たとえば、がとして計算されるかどうかを気にしない場合) は、 `a * b + a * c` `(b + c) * a` `2 * a` `a + a` [/fp: fast](#fast)オプションを検討してください。これにより、より高速で効率的なコードを生成できます。 コードが演算と式の順序に依存していて、浮動小数点環境にアクセスしたり変更したりする場合 (丸めモードを変更する場合や、浮動小数点例外をトラップする場合など) は、 [/fp: strict](#strict)を使用します。

#### <a name="strict"></a>strict

`/fp:strict`はと同様の動作を持ちます `/fp:precise` 。つまり、コンパイラは、ターゲットコンピューターのオブジェクトコードを生成して最適化するときに、浮動小数点コードのソースの順序付けと丸めのプロパティを保持し、特別な値を処理するときに標準を監視します。 また、プログラムは実行時に、浮動小数点環境に安全にアクセスしたり、変更したりする可能性があります。

では、コンパイラによって `/fp:strict` 、プログラムが浮動小数点例外のマスク解除、浮動小数点のステータスレジスタの読み取りまたは書き込み、または丸めモードの変更を安全に行うコードが生成されます。 これは、式の評価中に、割り当て時、typecasts 時、浮動小数点引数が関数呼び出しに渡されたとき、および関数呼び出しから浮動小数点値が返されたときに、4つの特定のポイントでソースコードの有効桁数に丸められます。 中間計算は、コンピューターの精度で実行できます。 Typecasts を使用して、中間計算を明示的に丸めることができます。 変換によってビットごとの同一の結果が生成される場合を除き、再関連付けや distribution などの浮動小数点式では、コンパイラは代数変換を実行しません。 特殊な値 (NaN、+ 無限大、-無限大、-0.0) を含む式は、IEEE-754 仕様に従って処理されます。 たとえば、 `x != x` x が NaN の場合、はに評価され **`true`** ます。 浮動小数点短縮形は、では生成されません `/fp:strict` 。

`/fp:strict`では、例外を `/fp:precise` トラップし、プログラムが実行時に浮動小数点環境にアクセスしたり変更したりできるようにするために、コンパイラが追加の命令を挿入する必要があるため、計算にかかる時間がかかります。 コードがこの機能を使用せず、ソースコードの順序付けと丸め処理を必要とする場合、または特殊な値に依存する場合は、を使用 `/fp:precise` します。 それ以外の場合、を使用することを検討してください `/fp:fast` 。

#### <a name="fast"></a>fast

オプションを使用すると、 `/fp:fast` コンパイラは、浮動小数点演算の順序変更、結合、または簡略化を行い、浮動小数点コードを最適化して速度と領域を確保することができます。 コンパイラは、代入ステートメント、typecasts、または関数呼び出しで丸め処理を省略できます。 このような変換では、著しいの丸め動作が異なる場合でも、操作の順序を変更したり、代数変換を実行したりすることがあります。 この強化された最適化のため、一部の浮動小数点計算の結果は、他のオプションで生成されるものとは異なる場合があり `/fp` ます。 特殊な値 (NaN、+ 無限大、-無限大、-0.0) は、IEEE-754 標準に従って厳密に伝達または動作しない可能性があります。 浮動小数点短縮形は、の下で生成される場合があり `/fp:fast` ます。 コンパイラは、の下の基になるアーキテクチャによってバインドされてい `/fp:fast` ます。また、 [/arch](arch-minimum-cpu-architecture.md)オプションを使用して追加の最適化を行うこともできます。

では `/fp:fast` 、コンパイラは、既定の浮動小数点環境での実行を意図したコードを生成し、実行時に浮動小数点環境にアクセスしたり変更したりしないことを前提としています。 つまり、このコードでは、浮動小数点例外のマスク解除、浮動小数点ステータスレジスタの読み取りまたは書き込み、または丸めモードの変更を行わないことを前提としています。

`/fp:fast`は、厳密なソースコードの順序付けと浮動小数点式の丸めを必要としないプログラムを対象としており、NaN などの特別な値を処理するための標準の規則に依存しません。 浮動小数点コードでソースコードの順序付けと丸めを行う必要がある場合、または特殊な値の標準動作に依存する場合は、 [/fp: 精密](#precise)を使用します。 丸めモードを変更する、浮動小数点例外をマスク解除する、または浮動小数点の状態をチェックするために、コードが浮動小数点環境にアクセスまたは変更する場合は、 [/fp: strict](#strict)を使用します。

#### <a name="except"></a>except

オプションは、マスクされてい `/fp:except` ない浮動小数点例外が発生した位置で確実に発生し、追加の浮動小数点例外が発生しないようにするためのコードを生成します。 既定では、オプションによってが有効になり、で `/fp:strict` は有効になり `/fp:except` `/fp:precise` ません。 `/fp:except`オプションはと互換性がありません `/fp:fast` 。 このオプションは、によって明示的に無効にすることができ `/fp:except-` ます。

で `/fp:except` は、浮動小数点例外がそれ自体によって有効になるわけではありませんが、プログラムで浮動小数点例外を有効にする必要があることに注意してください。 浮動小数点例外を有効にする方法については、「 [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) 」を参照してください。

## <a name="remarks"></a>解説

`/fp`同じコンパイラのコマンドラインで複数のオプションを指定できます。 、、およびの各オプションのうち、一度に有効にできるのは1つだけ `/fp:strict` `/fp:fast` `/fp:precise` です。 これらのオプションのいずれかがコマンドラインで指定されている場合、後のオプションが優先され、コンパイラによって警告が生成されます。 `/fp:strict`および `/fp:except` オプションはと互換性がありません `/clr` 。

[/Za](za-ze-disable-language-extensions.md) (ANSI compatibility) オプションはと互換性がありません `/fp` 。

### <a name="using-compiler-directives-to-control-floating-point-behavior"></a>コンパイラディレクティブを使用した浮動小数点動作の制御

コンパイラには、コマンドラインで指定された浮動小数点動作をオーバーライドするために、 [float_control](../../preprocessor/float-control.md)、 [fenv_access](../../preprocessor/fenv-access.md)、および[fp_contract](../../preprocessor/fp-contract.md)の3つのプラグマディレクティブが用意されています。 これらのディレクティブを使用すると、関数内ではなく、関数レベルで浮動小数点動作を制御できます。 これらのディレクティブは、オプションに直接対応していないことに注意してください `/fp` 。 次の表は、 `/fp` options ディレクティブと pragma ディレクティブが相互にどのようにマップされるかを示しています。 詳細については、個々のオプションとプラグマディレクティブのドキュメントを参照してください。

||float_control (正確)|float_control (除く)|fenv_access|fp_contract|
|-|-|-|-|-|
|`/fp:fast`|オフ|オフ|オフ|on|
|`/fp:precise`|on|オフ|オフ|on|
|`/fp:strict`|on|on|on|オフ|

### <a name="the-default-floating-point-environment"></a>既定の浮動小数点環境

プロセスが初期化されると、*既定の浮動小数点環境*が設定されます。 この環境では、すべての浮動小数点例外がマスクされ、丸めモードが [最も近い] () に設定され、 `FE_TONEAREST` subnormal (denormal) 値が **`float`** 保持 **`double`** されます。では、、、およびの各値に対して有効桁 (仮数) の既定の有効桁数が使用 **`long double`** されます

### <a name="floating-point-environment-access-and-modification"></a>浮動小数点環境へのアクセスと変更

Microsoft Visual C++ ランタイムには、浮動小数点環境にアクセスして変更するための関数がいくつか用意されています。 これには、 [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md)、 [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)、 [_statusfp](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)とそのバリエーションが含まれます。 コードが浮動小数点環境にアクセスしたり変更したりしたときに正しくプログラムが動作するようにするには、を有効にする `fenv_access` 必要があり `/fp:strict` `fenv_access` ます。これらの関数を有効にするには、オプションまたはプラグマを使用する必要があります。 `fenv_access`が有効になっていない場合、浮動小数点環境のアクセスまたは変更によって予期しないプログラムの動作が発生する可能性があります。浮動小数点環境に対する要求された変更をコードが受け入れないことがあります。浮動小数点の状態のレジスタが予期される結果または現在の結果を報告しない可能性があり

コードが浮動小数点環境にアクセスしたり変更したりする場合は、が有効になっていないコードを使用してコードを結合するときに注意する必要があり `fenv_access` `fenv_access` ます。 `fenv_access`が有効になっていないコードでは、コンパイラは、プラットフォームの既定の浮動小数点環境が有効であること、および浮動小数点の状態がアクセスまたは変更されないことを前提としています。 ローカルの浮動小数点環境は、有効になっていない関数に制御が転送される前に、既定の状態に保存して復元することをお勧めし `fenv_access` ます。 この例では、 `float_control` プラグマを設定および復元する方法を示します。

```cpp
#pragma float_control(strict, on, push)
// Code that uses /fp:strict mode
#pragma float_control(pop)
```

### <a name="floating-point-rounding-modes"></a>浮動小数点丸めモード

との両方で、 `/fp:precise` `/fp:fast` コンパイラは、既定の浮動小数点環境での実行を意図したコードを生成し、実行時に環境がアクセスまたは変更されないことを前提としています。 つまり、このコードでは、浮動小数点例外のマスク解除、浮動小数点ステータスレジスタの読み取りまたは書き込み、または丸めモードの変更を行わないことを前提としています。  ただし、一部のプログラムでは、浮動小数点環境を変更する必要があります。 たとえば、次のサンプルでは、浮動小数点丸めモードを変更することによって、浮動小数点の乗算の誤差範囲を計算します。

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

コンパイラでは、の既定の浮動小数点環境が想定されているため、の `/fp:fast` `/fp:precise` 呼び出しは自由に無視 `_controlfp_s` できます。 たとえば、x86 アーキテクチャでとの両方を使用してコンパイルした場合、 `/O2` `/fp:precise` 境界は計算されず、サンプルプログラムは次のように出力します。

```Output
cLower = -inf
cUpper = -inf
```

X86 アーキテクチャでとの両方を使用してコンパイルされた場合 `/O2` `/fp:strict` 、サンプルプログラムは次の出力を出力します。

```Output
cLower = -inf
cUpper = -3.40282e+38
```

### <a name="floating-point-special-values"></a>浮動小数点特殊値

およびの下では `/fp:precise` `/fp:strict` 、特殊な値 (NaN、+ 無限大、-無限大、-0.0) を含む式は、IEEE-754 仕様に従って動作します。 では `/fp:fast` 、これらの特殊な値の動作が IEEE-754 と矛盾している可能性があります。

このサンプルでは、、、およびでの特殊な値のさまざまな動作を示し `/fp:precise` `/fp:strict` `/fp:fast` ます。

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

X86 アーキテクチャでまたはを使用してコンパイルすると、 `/O2` `/fp:precise` `/O2` `/fp:strict` 出力は IEEE-754 仕様と一致します。

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 0
INFINITY - INFINITY  : -nan(ind)
NAN - NAN            : -nan(ind)
std::signbit(-0.0/-INFINITY): 1
```

X86 アーキテクチャ用にを使用してコンパイルした場合 `/O2` `/fp:fast` 、出力は IEEE-754 と一致しません。

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 1
INFINITY - INFINITY  : 0.000000
NAN - NAN            : 0.000000
std::signbit(-0.0/-INFINITY): 0
```

### <a name="floating-point-algebraic-transformations"></a>浮動小数点の代数変換

およびの下では、変換によって `/fp:precise` `/fp:strict` ビットごとの同一の結果が生成されることが保証されない限り、コンパイラは数学的変換を実行しません。 コンパイラは、このような変換をで実行でき `/fp:fast` ます。 たとえば、sample 関数の式は、の `a * b + a * c` `algebraic_transformation` 下にコンパイルされる場合があり `a * (b + c)` `/fp:fast` ます。 このような変換 `/fp:precise` はまたはでは実行され `/fp:strict` ず、コンパイラによってが生成さ `a * b + a * c` れます。

```cpp
float algebraic_transformation (float a, float b, float c)
{
    return a * b + a * c;
}
```

### <a name="floating-point-explicit-casting-points"></a>浮動小数点の明示的なキャストポイント

およびでは `/fp:precise` `/fp:strict` 、コンパイラは、式の評価中に、typecasts、浮動小数点引数が関数呼び出しに渡されたとき、および関数呼び出しから浮動小数点値が返されたときに、ソースコードの精度を4つの特定のポイントで丸めます。 Typecasts を使用して、中間計算を明示的に丸めることができます。 では `/fp:fast` 、コンパイラは、ソースコードの精度を保証するために、これらのポイントで明示的なキャストを生成しません。 このサンプルでは、さまざまなオプションでの動作を示し `/fp` ます。

```cpp
float casting(float a, float b)
{
    return 5.0*((double)(a+b));
}
```

またはを使用してコンパイルすると `/O2` `/fp:precise` `/O2` `/fp:strict` 、x64 アーキテクチャ用に生成されたコードの型キャストと関数の戻り位置の両方に明示的な型キャストが挿入されることがわかります。

```asm
        addss    xmm0, xmm1
        cvtss2sd xmm0, xmm0
        mulsd    xmm0, QWORD PTR __real@4014000000000000
        cvtsd2ss xmm0, xmm0
        ret      0
```

`/O2` `/fp:fast` すべての型キャストが最適化されているため、生成されたコードは単純化されます。

```asm
        addss    xmm0, xmm1
        mulss    xmm0, DWORD PTR __real@40a00000
        ret      0
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コード生成**] プロパティページを選択します。

1. **浮動小数点モデル**のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)<br/>
