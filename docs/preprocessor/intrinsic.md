---
title: 組み込み |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
dev_langs:
- C++
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e908a07253e924fa3cfc0a11cdef57a9253eee00
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="intrinsic"></a>intrinsic

プラグマの引数リストで指定された関数の呼び出しが組み込みであることを指定します。

## <a name="syntax"></a>構文

```cpp
#pragma intrinsic( function1 [, function2, ...] )
```

## <a name="remarks"></a>コメント

**組み込み**プラグマは、関数の動作が既知ことをコンパイラに指示します。  コンパイラは、関数を呼び出し、より優れたパフォーマンスを得られる場合は、関数呼び出しをインライン命令に置き換えないことがあります。

組み込み形式のライブラリ関数を以下に示します。 1 回、**組み込み**プラグマが、指定した組み込み関数を含む最初の関数定義で有効になります。 ソース ファイルの末尾にまたはの外観に効果が引き続き、**関数**プラグマ同じ組み込み関数を指定します。 **組み込み**プラグマは関数定義の外側でのみ使用できます: グローバル レベルでします。

次の関数も組み込み形式を指定する場合に組み込みの形式が使用される[/Oi](../build/reference/oi-generate-intrinsic-functions.md):

|||||
|-|-|-|-|
|[_disable](../intrinsics/disable.md)|[_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|
|[_enable](../intrinsics/enable.md)|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||

組み込み関数を使うと、関数呼び出しのオーバーヘッドがなくなるためプログラムの実行速度は向上しますが、コードが追加されるためプログラムのサイズが大きくなる可能性があります。

**x86 固有**

**_Disable**と**有効にする**組み込み割り込みを有効/無効化にカーネル モード命令を生成およびカーネル モード ドライバーで役立つことがあります。

### <a name="example"></a>例

コマンド ラインで「cl -c -FAs sample.c」と入力して次のコードをコンパイルし、sample.asm を見て組み込み関数が x86 命令の CLI と STI になることを確認します。

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

**End x86 固有の仕様**

次に示す浮動小数点関数には本物の組み込み形式はありません。 代わりに、引数をプログラム スタックにプッシュするのではなく、浮動小数点演算コプロセッサに直接渡すバージョンがあります。

|||||
|-|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)||

 指定すると、以下に示す浮動小数点関数は本物の組み込み形式をある[/Oi](../build/reference/oi-generate-intrinsic-functions.md)、 [/Og](../build/reference/og-global-optimizations.md)、および[/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) (または/Og を含む任意のオプション: [/Ox](../build/reference/ox-full-optimization.md)、 [/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md)、および/O2)。

|||||
|-|-|-|-|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)||||

使用することができます[/fp: 厳密な](../build/reference/fp-specify-floating-point-behavior.md)または[/Za](../build/reference/za-ze-disable-language-extensions.md)組み込み浮動小数点オプションが true の生成をオーバーライドします。 浮動小数点関数はライブラリ ルーチンとして生成されます。これらのライブラリ ルーチンでは、引数はプログラム スタックにプッシュされずに、数値演算コプロセッサに直接渡されます。

参照してください[#pragma function](../preprocessor/function-c-cpp.md)情報およびソース テキストのブロック用の組み込み関数の有効/無効にする方法の例です。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
