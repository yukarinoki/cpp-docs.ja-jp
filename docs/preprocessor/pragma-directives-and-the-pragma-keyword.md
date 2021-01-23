---
title: プラグマディレクティブ、__ pragma および _Pragma キーワード
description: pragmaMicrosoft Visual C および C++ (MSVC) で使用できるディレクティブについて説明します。
ms.date: 01/19/2021
f1_keywords:
- '#pragma'
- _Pragma
- __pragma
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- _Pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
no-loc:
- pragma
ms.openlocfilehash: fb6daf4c2912ea2168c38bfe2d1ae2650aaecc20
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713351"
---
# <a name="pragma-directives-and-the-__no-locpragma-and-_pragma-keywords"></a>プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード

プラグマディレクティブは、コンピューター固有またはオペレーティングシステム固有のコンパイラ機能を指定します。 **`__pragma`** Microsoft コンパイラに固有のキーワードを使用すると、マクロ定義内のディレクティブをコード化でき pragma ます。 標準 **`_Pragma`** プリプロセッサ演算子は C99 で導入され、c++ 11 で採用されました。

## <a name="syntax"></a>構文

> **`#pragma`***トークン-文字列*\
> **`__pragma(`***トークン-文字列* **`)`** 2つの先頭にアンダースコア-Microsoft 固有の拡張機能 \
> **`_Pragma(`***文字列-リテラル* **`)`** 規定

## <a name="remarks"></a>解説

C および C++ の各実装は、そのホスト コンピューターまたはオペレーティング システムに固有の機能をいくつかサポートしています。 たとえば、一部のプログラムでは、メモリ内のデータの場所を正確に制御したり、特定の関数がパラメーターを受け取る方法を制御したりする必要があります。 ディレクティブは、 **`#pragma`** コンパイラごとに、C および C++ 言語との全体的な互換性を維持しながら、コンピューターおよびオペレーティングシステム固有の機能を提供する手段を提供します。

プラグマディレクティブは、定義上、コンピューター固有またはオペレーティングシステム固有であり、通常、コンパイラごとに異なります。 は、 pragma 新しいプリプロセッサ機能を提供するために、条件付きディレクティブで使用できます。 または、1つを使用して、コンパイラに実装定義の情報を提供します。

*トークン文字列* は、特定のコンパイラ命令と引数 (存在する場合) を表す一連の文字です。 シャープ記号 ( **`#`** ) は、を含む行の最初の空白以外の文字である必要があり pragma ます。 空白文字は、シャープ記号と "" という単語を区切ることができ pragma ます。 次 **`#pragma`** に、変換プログラムがプリプロセストークンとして解析できるテキストを記述します。 の引数は、 **`#pragma`** マクロの展開の対象となります。

*文字列リテラル* は、への入力です `_Pragma` 。 外部引用符と先頭/末尾の空白は削除されます。 `\"` はに置き換えられ `"` 、 `\\` はに置き換えられ `\` ます。

コンパイラは、認識できないを検出してコンパイルを続行すると、警告を発行し pragma ます。

Microsoft C および C++ コンパイラは、次のディレクティブを認識し pragma ます。

:::row:::
   :::column span="":::
      [`alloc_text`](../preprocessor/alloc-text.md)\
      [`auto_inline`](../preprocessor/auto-inline.md)\
      [`bss_seg`](../preprocessor/bss-seg.md)\
      [`check_stack`](../preprocessor/check-stack.md)\
      [`code_seg`](../preprocessor/code-seg.md)\
      [`comment`](../preprocessor/comment-c-cpp.md)\
      [`component`](../preprocessor/component.md)\
      [`conform`](../preprocessor/conform.md)<sup>1</sup>\
      [`const_seg`](../preprocessor/const-seg.md)\
      [`data_seg`](../preprocessor/data-seg.md)\
      [`deprecated`](../preprocessor/deprecated-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`detect_mismatch`](../preprocessor/detect-mismatch.md)\
      [`endregion`](../preprocessor/region-endregion.md)\
      [`fenv_access`](../preprocessor/fenv-access.md)\
      [`float_control`](../preprocessor/float-control.md)\
      [`fp_contract`](../preprocessor/fp-contract.md)\
      [`function`](../preprocessor/function-c-cpp.md)\
      [`hdrstop`](../preprocessor/hdrstop.md)\
      [`include_alias`](../preprocessor/include-alias.md)\
      [`init_seg`](../preprocessor/init-seg.md)<sup>1</sup>\
      [`inline_depth`](../preprocessor/inline-depth.md)\
      [`inline_recursion`](../preprocessor/inline-recursion.md)
   :::column-end:::
   :::column span="":::
      [`intrinsic`](../preprocessor/intrinsic.md)\
      [`loop`](../preprocessor/loop.md)<sup>1</sup>\
      [`make_public`](../preprocessor/make-public.md)\
      [`managed`](../preprocessor/managed-unmanaged.md)\
      [`message`](../preprocessor/message.md)\
      [`omp`](../preprocessor/omp.md)\
      [`once`](../preprocessor/once.md)\
      [`optimize`](../preprocessor/optimize.md)\
      [`pack`](../preprocessor/pack.md)\
      [`pointers_to_members`](../preprocessor/pointers-to-members.md) <sup>1</sup>
   :::column-end:::
   :::column span="":::
      [`pop_macro`](../preprocessor/pop-macro.md)\
      [`push_macro`](../preprocessor/push-macro.md)\
      [`region`](../preprocessor/region-endregion.md)\
      [`runtime_checks`](../preprocessor/runtime-checks.md)\
      [`section`](../preprocessor/section.md)\
      [`setlocale`](../preprocessor/setlocale.md)\
      [`strict_gs_check`](../preprocessor/strict-gs-check.md)\
      [`unmanaged`](../preprocessor/managed-unmanaged.md)\
      [`vtordisp`](../preprocessor/vtordisp.md)<sup>1</sup>\
      [`warning`](../preprocessor/warning.md)
   :::column-end:::
:::row-end:::

<sup>1</sup> C++ コンパイラでのみサポートされます。

## <a name="pragma-directives-and-compiler-options"></a>プラグマディレクティブとコンパイラオプション

pragmaディレクティブによっては、コンパイラオプションと同じ機能が提供されます。 pragmaソースコードでに到達すると、コンパイラオプションによって指定された動作がオーバーライドされます。 たとえば、を指定した場合、 [`/Zp8`](../build/reference/zp-struct-member-alignment.md) コードの特定のセクションについて、次のようにこのコンパイラ設定をオーバーライドでき [`pack`](../preprocessor/pack.md) ます。

```cmd
cl /Zp8 some_file.cpp
```

```cpp
// some_file.cpp - packing is 8
// ...
#pragma pack(push, 1) - packing is now 1
// ...
#pragma pack(pop) - packing is 8 again
// ...
```

## <a name="the-__no-locpragma-keyword"></a>`__pragma()` キーワード

コンパイラは、ディレクティブと同じ機能を持つ、Microsoft 固有のキーワードもサポートしてい **`__pragma`** **`#pragma`** ます。 違いは、キーワードは **`__pragma`** マクロ定義でインラインで使用できるということです。 **`#pragma`** ディレクティブはマクロ定義では使用できません。コンパイラは、ディレクティブのシャープ記号 (# [) を文字列化演算子 (#)](../preprocessor/stringizing-operator-hash.md)として解釈するためです。

次のコード例は、 **`__pragma`** マクロでキーワードを使用する方法を示しています。 このコードは、「コンパイラ COM サポートサンプル」の ACDUAL サンプルの *mfcdual .h* ヘッダーから抜粋ですされています。

```cpp
#define CATCH_ALL_DUAL \
CATCH(COleException, e) \
{ \
_hr = e->m_sc; \
} \
AND_CATCH_ALL(e) \
{ \
__pragma(warning(push)) \
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \
AFX_MANAGE_STATE(pThis->m_pModuleState); \
__pragma(warning(pop)) \
_hr = DualHandleException(_riidSource, e); \
} \
END_CATCH_ALL \
return _hr; \
```

## <a name="the-_pragma-preprocessing-operator-c99-c11"></a>`_Pragma`プリプロセス演算子 (C99、c++ 11)

`_Pragma` は、 [`__pragma`](#the-__pragma-keyword) 標準の一部であることを除けば、Microsoft 固有のキーワードに似ています。 これは C99 で C に導入されました。 C++ では、C++ 11 で導入されました。

 これにより、ディレクティブをマクロ定義に配置でき pragma ます。 このクラスには、 `_` Microsoft 固有のキーワードが含まれる2つの先頭のアンダースコアではなく、先頭にアンダースコアが1つあり、 `__` 最初の文字が大文字になっています。

文字列リテラルは、ステートメントの後に記述する場合と同じにする必要があり *`#pragma`* ます。 例:

```c
#pragma message("the #pragma way")
_Pragma ("message( \"the _Pragma way\")") 
```

上に示すように、引用符と円記号はエスケープする必要があります。 pragma認識されない文字列は無視されます。

次のコード例は、 **`_Pragma`** 条件式が定数である場合に警告が表示されないようにするために、assert に似たマクロでキーワードを使用する方法を示しています。 

マクロ定義では、複数ステートメントのマクロの表現形式を使用して、 `do` - `while(0)` 1 つのステートメントと同じように使用できます。 詳細については、Stack Overflow での [C の複数行マクロ](https://stackoverflow.com/questions/1067226/c-multi-line-macro-do-while0-vs-scope-block) に関する情報を参照してください。 ステートメントは、 **`_Pragma`** その後に続くコード行にのみ適用されます。

```C
// Compile with /W4

#include <stdio.h>
#include <stdlib.h>

#define MY_ASSERT(BOOL_EXPRESSION) \
    do { \
        _Pragma("warning(suppress: 4127)") /* C4127 conditional expression is constant */  \
        if (!(BOOL_EXPRESSION)) {   \
            printf("MY_ASSERT FAILED: \"" #BOOL_EXPRESSION "\" on %s(%d)", __FILE__, __LINE__); \
            exit(-1); \
        } \
    } while (0)

int main()
{
    MY_ASSERT(0 && "Note that there is no warning: C4127 conditional expression is constant");

    return 0;
}
```

## <a name="see-also"></a>関連項目

[C/C++ のプリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)\
[C pragma ディレクティブ](../c-language/c-pragmas.md)\
[キーワード](../cpp/keywords-cpp.md)
