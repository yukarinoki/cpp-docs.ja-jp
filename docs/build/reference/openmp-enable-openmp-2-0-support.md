---
description: 詳細について:/openmp (OpenMP サポートを有効にする)
title: /openmp (OpenMP サポートの有効化)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: 818cd6167bf56b9948a3d9f455b0153b4302e8df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221983"
---
# <a name="openmp-enable-openmp-support"></a>/openmp (OpenMP サポートの有効化)

OpenMP をサポートするディレクティブをコンパイラで処理し [`#pragma omp`](../../preprocessor/omp.md) ます。

## <a name="syntax"></a>構文

::: moniker range=">= msvc-160"

> **/openmp** \[**:**__試験段階__]

::: moniker-end

::: moniker range="<= msvc-150"

> **/openmp**

::: moniker-end

## <a name="remarks"></a>解説

`#pragma omp` は、 [ディレクティブ](../../parallel/openmp/reference/openmp-directives.md) および [句](../../parallel/openmp/reference/openmp-clauses.md)を指定するために使用されます。 コンパイルで **/openmp** が指定されていない場合、コンパイラは openmp 句およびディレクティブを無視します。 [OpenMP 関数](../../parallel/openmp/reference/openmp-functions.md) 呼び出しは、 **/openmp** が指定されていない場合でも、コンパイラによって処理されます。

::: moniker range=">= msvc-160"

現在、C++ コンパイラは OpenMP 2.0 標準をサポートしています。 ただし、Visual Studio 2019 では SIMD 機能も提供されています。 SIMD を使用するには、 **/openmp: 実験的** オプションを使用してコンパイルします。 このオプションを選択すると、通常の OpenMP 機能と、 **/openmp** スイッチを使用するときに使用できない追加の openmp SIMD 機能の両方が有効になります。

::: moniker-end

**/Openmp** と **/clr** の両方を使用してコンパイルされたアプリケーションは、1つのアプリケーションドメインプロセスでのみ実行できます。 複数のアプリケーションドメインはサポートされていません。 つまり、モジュールコンストラクター () が実行されると、 `.cctor` **/openmp** を使用してプロセスがコンパイルされているかどうか、およびアプリが既定以外のランタイムに読み込まれているかどうかが検出されます。 詳細については、「 [appdomain](../../cpp/appdomain.md)」、「 [/Clr (共通言語ランタイムのコンパイル)](clr-common-language-runtime-compilation.md)」、および「 [混合アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)」を参照してください。

**/Openmp** と **/clr** の両方を使用してコンパイルされたアプリを既定以外のアプリケーションドメインに読み込もうとすると、 <xref:System.TypeInitializationException> デバッガーの外部で例外がスローされ、 `OpenMPWithMultipleAppdomainsException` デバッガーで例外がスローされます。

これらの例外は、次のような場合にも発生する可能性があります。

- アプリケーションが **/clr** を使用してコンパイルされ、 **/openmp** がない場合は、が既定以外のアプリケーションドメインに読み込まれます。この場合、プロセスには、 **/openmp** を使用してコンパイルされたアプリが含まれます。

- **/Clr** アプリを [regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)などのユーティリティに渡すと、そのターゲットアセンブリが既定以外のアプリケーションドメインに読み込まれます。

共通言語ランタイムのコードアクセスセキュリティは、OpenMP リージョンでは機能しません。 CLR コードアクセスセキュリティ属性を並列領域の外部に適用すると、並列領域では無効になります。

Microsoft では、部分的に信頼された呼び出し元を許可する **/openmp** アプリを作成することはお勧めしません。 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>または CLR コードアクセスセキュリティ属性は使用しないでください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**  >  ] [**C/c + +**  >  **言語**] プロパティページを展開します。

1. **OpenMP サポート** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>

## <a name="example"></a>例

次のサンプルでは、スレッドプールのスタートアップとスレッドプールの使用の開始後の影響の一部を示します。 X64、シングルコア、デュアルプロセッサの場合、スレッドプールの起動には約16ミリ秒かかります。 その後、スレッドプールの追加コストはほとんどありません。

**/Openmp** を使用してコンパイルする場合、 **/openmp-** を使用してコンパイルする場合よりも、test2 の2回目の呼び出しは実行されません。これは、スレッドプールの起動がないためです。 100万回のイテレーションでは、 **/openmp** のバージョンは、test2 への2回目の呼び出しの **/openmp-** バージョンよりも高速です。 25回のイテレーションでは、 **/openmp-** と **/openmp** の両方のバージョンが、クロックの粒度よりも小さく登録されます。

アプリケーション内にループが1つしかなく、15ミリ秒未満で実行されている場合 (コンピューターのおおよそのオーバーヘッドに合わせて調整されている場合)、 **/openmp** は適切ではない可能性があります。 より高い場合は、 **/openmp** の使用を検討してください。

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
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md) \
[MSVC での OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)
