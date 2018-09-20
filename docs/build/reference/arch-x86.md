---
title: -arch (x86) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 819d95883cecb4d219fd11c4ab83e18afa2dbbd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444932"
---
# <a name="arch-x86"></a>/arch (x86)

x86 でコード生成のアーキテクチャを指定します。 参照してください[/arch (x64)](../../build/reference/arch-x64.md)と[/arch (ARM)](../../build/reference/arch-arm.md)します。

## <a name="syntax"></a>構文

```
/arch:[IA32|SSE|SSE2|AVX|AVX2]
```

## <a name="arguments"></a>引数

**/arch:IA32**<br/>
拡張命令なしを指定し、浮動小数点計算に x87 を指定します。

**/arch:SSE**<br/>
SSE 命令の使用を有効にします。

**/arch:sse2 以上**<br/>
SSE2 命令の使用を有効にします。 これは、既定の命令に x86 プラットフォームがない場合は **/arch**オプションを指定します。

**/arch:AVX**<br/>
Advanced Vector Extensions 命令の使用を有効にします。

**/arch:AVX2**<br/>
Advanced Vector Extensions 2 命令の使用を有効にします。

## <a name="remarks"></a>Remarks

SSE 命令および SSE2 命令は、さまざまな Intel プロセッサおよび AMD プロセッサに組み込まれています。 AVX 命令は、Intel Sandy Bridge プロセッサおよび AMD Bulldozer プロセッサに組み込まれています。 AVX2 命令は、Intel Haswell および Broadwell プロセッサと AMD Excavator ベースのプロセッサでサポートされています。

`_M_IX86_FP`、`__AVX__`と`__AVX2__`マクロかを示しますがあれば、 **/arch**コンパイラ オプションを使用します。 詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。 **/Arch:AVX2**オプションと`__AVX2__`マクロは、Visual Studio 2013 Update 2、バージョン 12.0.34567.1 で導入されました。

オプティマイザーは、SSE 命令と SSE2 命令を使用するタイミングと方法と **/arch**を指定します。 SSE 命令と SSE2 命令は、x87 浮動小数点レジスタ スタックよりも SSE/SSE2 命令およびレジスタを使用した方が高速であると判断された場合に、一部のスカラー浮動小数点演算に使用されます。 したがって、実際のコードでは、浮動小数点演算に x87 と SSE/SSE2 の両方を組み合わせて使用してもかまいません。 また、 **/arch:sse2 以上**、SSE2 命令を一部の 64 ビット整数演算に使用できます。

コンパイラでは、SSE 命令と SSE2 命令の使用に加え、SSE および SSE2 をサポートするプロセッサ リビジョンに組み込まれているその他の命令も使用します。 例としては、Intel プロセッサの Pentium Pro リビジョンで初めて導入された CMOV 命令が挙げられます。

指定する必要がありますが、x86 コンパイラ生成では、既定で SSE2 命令を使用するがコード、 **/arch:IA32** x86 の SSE 命令と SSE2 命令の生成を無効にするプロセッサ。

**/arch**だけでネイティブ関数の生成のコードに影響します。 使用すると[/clr](../../build/reference/clr-common-language-runtime-compilation.md)をコンパイルする **/arch**マネージ関数のコード生成に影響を与えません。

**/arch**と[/QIfist](../../build/reference/qifist-suppress-ftol.md)同じコンパイル単位では使用できません。 特に、ユーザーが `_controlfp` を使用して FP 制御ワードを変更しない場合、ランタイム スタートアップ コードでは x87 FPU 制御ワードの精度制御フィールドが 53 ビットに設定されます。 そのため、式内のすべての浮動小数点演算と倍精度浮動小数点演算は、53 ビットの有効桁と 15 ビットの指数部を使用します。 ただし、すべての SSE 単精度浮動小数点演算では、24 ビットの有効桁と 8 ビットの指数部が使用され、SSE2 倍精度浮動小数点演算では、53 ビットの有効桁と 11 ビットの指数部が使用されます。 詳細については、「[_control87、_controlfp、\__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)」を参照してください。 これらの差異は、ユーザーの代入が各部分式の後に行われる場合ではなく、単一の式ツリー内で発生する可能性があります。 次に例を示します。

```cpp
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.
```

比較します。

```cpp
t = f1 * f2;   // Do f1 * f2, round to the type of t.
r = t + d;     // This should produce the same overall result
               // whether x87 stack is used or SSE/SSE2 is used.
```

### <a name="to-set-this-compiler-option-for-avx-avx2-ia32-sse-or-sse2-in-visual-studio"></a>AVX、AVX2、IA32、SSE、または SSE2 のこのコンパイラ オプションを Visual Studio で設定するには

1. 開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ**、 **C/C++** フォルダー。

1. 選択、**コード生成**プロパティ ページ。

1. 変更、**拡張命令セットを有効にする**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>

## <a name="see-also"></a>関連項目

[/arch (最小限の CPU アーキテクチャ)](../../build/reference/arch-minimum-cpu-architecture.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)