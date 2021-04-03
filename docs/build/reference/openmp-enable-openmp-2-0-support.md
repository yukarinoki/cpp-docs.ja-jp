---
description: 詳細について:/openmp (OpenMP サポートを有効にする)
title: /openmp (OpenMP サポートの有効化)
ms.date: 04/01/2021
f1_keywords:
- /openmp
- /openmp:experimental
- /openmp:llvm
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- /openmp:experimental compiler option [C++]
- /openmp:llvm compiler option [C++]
- -openmp compiler option [C++]
ms.openlocfilehash: d8363b253136c7e962ef62ecb29f0e2f13cc453e
ms.sourcegitcommit: be9a1af0b9d3f1d6c2987d8744392170b8dccab0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "106232323"
---
# <a name="openmp-enable-openmp-support"></a>`/openmp` (OpenMP サポートを有効にする)

OpenMP をサポートするディレクティブをコンパイラで処理し [`#pragma omp`](../../preprocessor/omp.md) ます。

## <a name="syntax"></a>構文

::: moniker range=">= msvc-160"

> **`/openmp`**\
> **`/openmp:experimental`**\
> **`/openmp:llvm`**

::: moniker-end

::: moniker range="<= msvc-150"

> **`/openmp`**

::: moniker-end

## <a name="remarks"></a>解説

`#pragma omp` は、 [ディレクティブ](../../parallel/openmp/reference/openmp-directives.md) および [句](../../parallel/openmp/reference/openmp-clauses.md)を指定するために使用されます。 **`/openmp`** コンパイルでが指定されていない場合、コンパイラは OpenMP 句およびディレクティブを無視します。 [OpenMP 関数](../../parallel/openmp/reference/openmp-functions.md) 呼び出しは、が指定されていない場合でも、コンパイラによって処理され **`/openmp`** ます。

::: moniker range=">= msvc-160"

現在、C++ コンパイラは OpenMP 2.0 標準をサポートしています。 ただし、Visual Studio 2019 では SIMD 機能も提供されています。 SIMD を使用するには、オプションを使用してコンパイルし **`/openmp:experimental`** ます。 このオプションを選択すると、通常の OpenMP 機能と、スイッチを使用するときに使用できない OpenMP SIMD 機能の両方が有効になり **`/openmp`** ます。

Visual Studio 2019 バージョン16.9 以降では、 **`/openmp:llvm`** の代わりに実験的オプションを使用し **`/openmp`** て、Llvm OpenMP ランタイムを対象にすることができます。 必須の libomp Dll が再頒布可能ではないため、現在、サポートは実稼働コードでは利用できません。 オプションは、と同じ OpenMP 2.0 ディレクティブをサポートして **`/openmp`** います。 また、オプションでサポートされているすべての SIMD ディレクティブをサポートしてい **`/openmp:experimental`** ます。 また、OpenMP 3.0 標準に準拠した for ループの符号なし整数インデックスもサポートしています。 詳細については、「 [Visual Studio での C++ の強化](https://devblogs.microsoft.com/cppblog/improved-openmp-support-for-cpp-in-visual-studio/)された OpenMP サポート」を参照してください。

現時点では、この **`/openmp:llvm`** オプションは x64 アーキテクチャでのみ機能します。 オプションは、またはと互換性がありません **`/clr`** **`/ZW`** 。

::: moniker-end

との両方を使用してコンパイル **`/openmp`** **`/clr`** されたアプリケーションは、1つのアプリケーションドメインプロセスでのみ実行できます。 複数のアプリケーションドメインはサポートされていません。 つまり、モジュールコンストラクター () が実行されると、 `.cctor` プロセスがを使用してコンパイルされているかどうか、 **`/openmp`** およびアプリが既定以外のランタイムに読み込まれているかどうかが検出されます。 詳細については、「」、「」 [`appdomain`](../../cpp/appdomain.md) [ `/clr` (共通言語ランタイムのコンパイル)](clr-common-language-runtime-compilation.md)、および「[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)」を参照してください。

と * の両方を使用してコンパイルされたアプリを **`/openmp`** *`/clr*`* 既定以外のアプリケーションドメインに読み込もうとする <xref:System.TypeInitializationException> と、デバッガーの外部で例外がスローされ、 `OpenMPWithMultipleAppdomainsException` デバッガーで例外がスローされます。

これらの例外は、次のような場合にも発生する可能性があります。

- アプリケーションがを使用してコンパイルされ、ではない場合は、を使用してコンパイルされた **`/clr`** アプリが **`/openmp`** プロセスに含まれる、既定以外のアプリケーションドメインに読み込まれ **`/openmp`** ます。

- アプリをregasm.exeなどのユーティリティに渡すと、 **`/clr`** その [](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)ターゲットアセンブリが既定以外のアプリケーションドメインに読み込まれます。

共通言語ランタイムのコードアクセスセキュリティは、OpenMP リージョンでは機能しません。 CLR コードアクセスセキュリティ属性を並列領域の外部に適用すると、並列領域では無効になります。

Microsoft では、 **`/openmp`** 部分的に信頼された呼び出し元を許可するアプリを作成することはお勧めしません。 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>または CLR コードアクセスセキュリティ属性は使用しないでください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**  >  ] [**C/c + +**  >  **言語**] プロパティページを展開します。

1. **OpenMP サポート** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>

## <a name="example"></a>例

次のサンプルでは、スレッドプールのスタートアップとスレッドプールの使用の開始後の影響の一部を示します。 X64、シングルコア、デュアルプロセッサの場合、スレッドプールの起動には約16ミリ秒かかります。 その後、スレッドプールの追加コストはほとんどありません。

を使用してコンパイルすると、 **`/openmp`** **`/openmp-`** スレッドプールのスタートアップがないため、を使用してコンパイルした場合よりも、test2 への2回目の呼び出しは長時間実行されません。 100万回のイテレーションで **`/openmp`** は、バージョンは **`/openmp-`** test2 への2回目の呼び出しのバージョンよりも高速です。 25回のイテレーションでは、との両方のバージョンは、 **`/openmp-`** **`/openmp`** クロック粒度よりも小さくなります。

アプリケーション内にループが1つしかなく、15ミリ秒未満で実行されている場合 (コンピューターのおおよそのオーバーヘッドに合わせて調整されている場合)、は **`/openmp`** 適切でない可能性があります。 より高い場合は、を使用することを検討してください **`/openmp`** 。

```cpp
// cpp_compiler_options_openmp.cpp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>

volatile DWORD dwStart;
volatile int global = 0;

double test2(int num_steps) {
   int i;
   global++;
   double x, pi, sum = 0.0, step;

   step = 1.0 / (double) num_steps;

   #pragma omp parallel for reduction(+:sum) private(x)
   for (i = 1; i <= num_steps; i++) {
      x = (i - 0.5) * step;
      sum = sum + 4.0 / (1.0 + x*x);
   }

   pi = step * sum;
   return pi;
}

int main(int argc, char* argv[]) {
   double   d;
   int n = 1000000;

   if (argc > 1)
      n = atoi(argv[1]);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);
}
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md) \
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md) \
[MSVC での OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)
