---
title: intrinsic プラグマ
description: MSVC 組み込みプラグマは、組み込み関数として使用する、サポートされている組み込み関数を指定するために使用されます。
ms.date: 07/08/2020
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
ms.openlocfilehash: 31f4ebc2fdd4c5c984160d441b4e0a723c686a46
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180956"
---
# <a name="intrinsic-pragma"></a>`intrinsic` プラグマ

プラグマの引数リストで指定された関数の呼び出しが組み込みであることを指定します。

## <a name="syntax"></a>構文

> **`#pragma intrinsic(`** *`function1`* [**`,`** _`function2`_ ... ] **`)`**

## <a name="remarks"></a>解説

**`intrinsic`** プラグマは、関数が既知の動作を持つことをコンパイラに通知します。 コンパイラは、関数を呼び出し、より優れたパフォーマンスを得られる場合は、関数呼び出しをインライン命令に置き換えないことがあります。

組み込み形式のライブラリ関数を以下に示します。 **`intrinsic`** プラグマが検出されると、指定した組み込み関数を含む最初の関数定義で有効になります。 効果は、ソースファイルの末尾、または同じ組み込み関数を指定するプラグマの外観まで継続され `function` ます。 **`intrinsic`** プラグマは、関数定義の外部でグローバルレベルでのみ使用できます。

次の関数には固有のフォームがあり、組み込みフォームはを指定するときに使用され [`/Oi`](../build/reference/oi-generate-intrinsic-functions.md) ます。

|  |  |  |  |
|--|--|--|--|
| [`_disable`](../intrinsics/disable.md) | [`_outp`](../c-runtime-library/outp-outpw-outpd.md) | [`fabs`](../c-runtime-library/reference/fabs-fabsf-fabsl.md) | [`strcmp`](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md) |
| [`_enable`](../intrinsics/enable.md) | [`_outpw`](../c-runtime-library/outp-outpw-outpd.md) | [`labs`](../c-runtime-library/reference/abs-labs-llabs-abs64.md) | [`strcpy`](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md) |
| [`_inp`](../c-runtime-library/inp-inpw-inpd.md) | [`_rotl`](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md) | [`memcmp`](../c-runtime-library/reference/memcmp-wmemcmp.md) | [`strlen`](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md) |
| [`_inpw`](../c-runtime-library/inp-inpw-inpd.md) | [`_rotr`](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md) | [`memcpy`](../c-runtime-library/reference/memcpy-wmemcpy.md) |  |
| [`_lrotl`](../c-runtime-library/reference/lrotl-lrotr.md) | [`_strset`](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md) | [`memset`](../c-runtime-library/reference/memset-wmemset.md) |  |
| [`_lrotr`](../c-runtime-library/reference/lrotl-lrotr.md) | [`abs`](../c-runtime-library/reference/abs-labs-llabs-abs64.md) | [`strcat`](../c-runtime-library/reference/strcat-wcscat-mbscat.md) |  |

組み込み関数を使用するプログラムは、関数呼び出しのオーバーヘッドがないため、高速です。 ただし、追加のコードが生成されるため、サイズが大きくなる可能性があります。

### <a name="x86-specific-example"></a>x86 固有の例

との組み込みは、 `_disable` `_enable` 割り込みを無効または有効にするカーネルモード命令を生成します。カーネルモードドライバーで役立つ可能性があります。

コマンドラインからを使用して次のコードをコンパイルし、次のコードが `cl -c -FAs sample.c` *`sample.asm`* X86 命令 CLI および STI になることを確認します。

```cpp
// pragma_directive_intrinsic.cpp
// processor: x86
#include <dos.h>   // definitions for _disable, _enable
#pragma intrinsic(_disable)
#pragma intrinsic(_enable)
void f1(void) {
   _disable();
   // do some work here that should not be interrupted
   _enable();
}
int main() {
}
```

### <a name="intrinsic-floating-point-functions"></a>組み込み浮動小数点関数

これらの浮動小数点関数には、真の組み込み形式はありません。 代わりに、引数をスタックにプッシュするのではなく、浮動小数点チップに直接渡すバージョンがあります。

|  |  |  |  |
|--|--|--|--|
| [`acos`](../c-runtime-library/reference/acos-acosf-acosl.md) | [`cosh`](../c-runtime-library/reference/cosh-coshf-coshl.md) | [`pow`](../c-runtime-library/reference/pow-powf-powl.md) | [`tanh`](../c-runtime-library/reference/tanh-tanhf-tanhl.md) |
| [`asin`](../c-runtime-library/reference/asin-asinf-asinl.md) | [`fmod`](../c-runtime-library/reference/fmod-fmodf.md) | [`sinh`](../c-runtime-library/reference/sinh-sinhf-sinhl.md) |  |

これらの浮動小数点関数は [`/Oi`](../build/reference/oi-generate-intrinsic-functions.md) 、および [`/fp:fast`](../build/reference/fp-specify-floating-point-behavior.md) (または、、、およびを含む任意のオプション) を指定するときに、真の組み込み形式を持ち **`/Oi`** [`/Ox`](../build/reference/ox-full-optimization.md) [`/O1`](../build/reference/o1-o2-minimize-size-maximize-speed.md) [`/O2`](../build/reference/o1-o2-minimize-size-maximize-speed.md) ます。

|  |  |  |  |
|--|--|--|--|
| [`atan`](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [`exp`](../c-runtime-library/reference/exp-expf.md) | [`log10`](../c-runtime-library/reference/log-logf-log10-log10f.md) | [`sqrt`](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md) |
| [`atan2`](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md) | [`log`](../c-runtime-library/reference/log-logf-log10-log10f.md) | [`sin`](../c-runtime-library/reference/sin-sinf-sinl.md) | [`tan`](../c-runtime-library/reference/tan-tanf-tanl.md) |
| [`cos`](../c-runtime-library/reference/cos-cosf-cosl.md) |  |  |  |

またはを使用して、 [`/fp:strict`](../build/reference/fp-specify-floating-point-behavior.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 真の組み込み浮動小数点オプションの生成をオーバーライドできます。 浮動小数点関数はライブラリ ルーチンとして生成されます。これらのライブラリ ルーチンでは、引数はプログラム スタックにプッシュされずに、数値演算コプロセッサに直接渡されます。

[`#pragma function`](../preprocessor/function-c-cpp.md)ソーステキストのブロックの組み込みを有効または無効にする方法の詳細と例については、「」を参照してください。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
