---
title: プラグマ ディレクティブと __Pragma キーワード
ms.date: 11/04/2016
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
ms.openlocfilehash: b6c2ff579c6fafa78cbfd0a2879a71fca2bfaa01
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027442"
---
# <a name="pragma-directives-and-the-pragma-keyword"></a>プラグマ ディレクティブと __Pragma キーワード

プラグマ ディレクティブは、コンピューター固有またはオペレーティング システム固有のコンパイラ機能を指定します。 **_ _Pragma**マクロ定義内のプラグマ ディレクティブをコードには、Microsoft コンパイラに固有で、キーワードを使用します。

## <a name="syntax"></a>構文

```
#pragma token-string
__pragma(token-string)
```

## <a name="remarks"></a>Remarks

C および C++ の各実装は、そのホスト コンピューターまたはオペレーティング システムに固有の機能をいくつかサポートしています。 たとえば、一部のプログラムは、データが格納されているメモリ領域、または特定の関数がパラメーターを受け取る方法を正確に制御する必要があります。 **#Pragma**ディレクティブは、各コンパイラが C および C++ 言語の全体的な互換性を維持しながらマシンとオペレーティング システムに固有の機能を提供するための手段を提供します。

プラグマは、コンピューター固有つまりオペレーティング システム固有であり、通常はコンパイラごとに異なります。 プラグマは、新しいプリプロセッサ機能を提供するために、または実装定義の情報をコンパイラに提供するために、条件付きステートメントで使用できます。

`token-string` は、特定のコンパイラ命令と引数 (ある場合) を渡す一連の文字です。 シャープ記号 (**#**) 最初の空白以外の文字にする必要があります、プラグマを格納している行には空白文字がシャープ記号と単語「pragma」に分離できます。 次の **#pragma**、翻訳者は、プリプロセス トークンとして解析できる任意のテキストを記述します。 引数に **#pragma**マクロの展開される可能性があります。

コンパイラで認識されないプラグマが検出されると、警告が表示され、コンパイルは続行されます。

Microsoft C および C++ コンパイラは、次のプラグマを認識します。

||||
|-|-|-|
|[alloc_text](../preprocessor/alloc-text.md)|[auto_inline](../preprocessor/auto-inline.md)|[bss_seg](../preprocessor/bss-seg.md)|
|[check_stack](../preprocessor/check-stack.md)|[code_seg](../preprocessor/code-seg.md)|[comment](../preprocessor/comment-c-cpp.md)|
|[component](../preprocessor/component.md)|[conform](../preprocessor/conform.md) <sup>1</sup>|[const_seg](../preprocessor/const-seg.md)|
|[data_seg](../preprocessor/data-seg.md)|[deprecated](../preprocessor/deprecated-c-cpp.md)|[detect_mismatch](../preprocessor/detect-mismatch.md)|
|[fenv_access](../preprocessor/fenv-access.md)|[float_control](../preprocessor/float-control.md)|[fp_contract](../preprocessor/fp-contract.md)|
|[function](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include_alias](../preprocessor/include-alias.md)|
|[init_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline_depth](../preprocessor/inline-depth.md)|[inline_recursion](../preprocessor/inline-recursion.md)|
|[intrinsic](../preprocessor/intrinsic.md)|[loop](../preprocessor/loop.md) <sup>1</sup>|[make_public](../preprocessor/make-public.md)|
|[managed](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)||
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers_to_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|
|[pop_macro](../preprocessor/pop-macro.md)|[push_macro](../preprocessor/push-macro.md)|[region、endregion](../preprocessor/region-endregion.md)|
|[runtime_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|
|[strict_gs_check](../preprocessor/strict-gs-check.md)|[unmanaged](../preprocessor/managed-unmanaged.md)|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|
|[warning](../preprocessor/warning.md)|||

<sup>1</sup> C++ コンパイラでのみサポートされています。

## <a name="pragmas-and-compiler-options"></a>プラグマとコンパイラのオプション

一部のプラグマの機能はコンパイラ オプションのものと同じです。 ソース コード内のプラグマは、コンパイラ オプションで指定された動作をオーバーライドします。 たとえば、指定した[、/zp8 です](../build/reference/zp-struct-member-alignment.md)を使用してコードの特定のセクションのコンパイラ設定をオーバーライドできます[パック](../preprocessor/pack.md):

```
cl /Zp8 ...

<file> - packing is 8
// ...
#pragma pack(push, 1) - packing is now 1
// ...
#pragma pack(pop) - packing is 8
</file>
```

## <a name="the-pragma-keyword"></a>__pragma() キーワード

**Microsoft 固有の仕様**

コンパイラもサポートしています、 **_ _pragma**キーワードは、同じ機能として、 **#pragma**ディレクティブ、インライン マクロ定義で使用できますが、します。 **#Pragma**ディレクティブ、コンパイラ ディレクティブのシャープ記号 ('#') の解釈されるので、マクロ定義では使用できません、[文字列化演算子 (#)](../preprocessor/stringizing-operator-hash.md)します。

コード例を次に示しますが、どのように **_ _pragma**マクロでキーワードを使用できます。 このコードは、「コンパイラ COM サポートのサンプル」の ACDUAL サンプルの mfcdual.h ヘッダーからの抜粋です。

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

**End Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
[C プラグマ](../c-language/c-pragmas.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
