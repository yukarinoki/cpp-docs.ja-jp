---
title: /openmp (OpenMP サポートを有効にする)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: d3454650bfaaacd756e5cfc73df056441a39f5ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336190"
---
# <a name="openmp-enable-openmp-support"></a>/openmp (OpenMP サポートを有効にする)

コンパイラが OpenMP[`#pragma omp`](../../preprocessor/omp.md)をサポートするディレクティブを処理します。

## <a name="syntax"></a>構文

::: moniker range=">= vs-2019"

> **/openmp**\[**:**__実験__中 ]

::: moniker-end

::: moniker range="<= vs-2017"

> **/オープンパンプ**

::: moniker-end

## <a name="remarks"></a>解説

`#pragma omp`は[、ディレクティブ](../../parallel/openmp/reference/openmp-directives.md)と句を指定するために使用[されます](../../parallel/openmp/reference/openmp-clauses.md)。 コンパイルで **/openmp**が指定されていない場合、コンパイラは OpenMP 句とディレクティブを無視します。 **/openmp**が指定されていない場合でも[、OpenMP 関数](../../parallel/openmp/reference/openmp-functions.md)呼び出しはコンパイラによって処理されます。

::: moniker range=">= vs-2019"

C++ コンパイラは現在、OpenMP 2.0 標準をサポートしています。 ただし、Visual Studio 2019 では SIMD 機能も提供されるようになりました。 SIMD を使用するには **、/openmp:実験**オプションを使用してコンパイルします。 このオプションを使用すると、通常の OpenMP 機能と **、/openmp**スイッチを使用する場合は使用できない追加の OpenMP SIMD 機能の両方が有効になります。

::: moniker-end

**/openmp**と **/clr**の両方を使用してコンパイルされたアプリケーションは、単一のアプリケーション ドメイン プロセスでのみ実行できます。 複数のアプリケーション ドメインはサポートされていません。 つまり、モジュール コンストラクター (`.cctor`) を実行すると、プロセスが **/openmp**を使用してコンパイルされたかどうか、およびアプリケーションが既定以外のランタイムに読み込まれているかどうかを検出します。 詳細については、「 [appdomain](../../cpp/appdomain.md)、 [/clr (共通言語ランタイムコンパイル](clr-common-language-runtime-compilation.md)) 」、および[「混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)」を参照してください。

**/openmp**と **/clr**の両方を使用してコンパイルされたアプリを既定以外のアプリケーション ドメインに読<xref:System.TypeInitializationException>み込もうとすると、デバッガーの外部`OpenMPWithMultipleAppdomainsException`で例外がスローされ、デバッガーで例外がスローされます。

これらの例外は、次の状況でも発生する可能性があります。

- アプリケーションが **/clr**ではなく **/openmp**を使用してコンパイルされ、既定以外のアプリケーション ドメインに読み込まれる場合は、プロセスに **/openmp**を使用してコンパイルされたアプリが含まれます。

- **/clr**アプリをユーティリティ[(regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)など) に渡すと、ターゲット アセンブリが既定以外のアプリケーション ドメインに読み込まれます。

共通言語ランタイムのコード アクセス セキュリティは OpenMP リージョンでは機能しません。 並列領域の外部に CLR コード アクセス セキュリティ属性を適用する場合、並列領域では有効になりません。

部分的に信頼された発信者を許可する **/openmp**アプリを作成することを推奨していません。 または、CLR<xref:System.Security.AllowPartiallyTrustedCallersAttribute>コード アクセス セキュリティ属性を使用しないでください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ** > **C/C++** > 言語] プロパティ ページ**を**展開します。

1. **OpenMP サポート**プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>」を参照してください。

## <a name="example"></a>例

次の例は、スレッド プールの起動と、スレッド プールの開始後の使用の影響の一部を示しています。 x64、シングルコア、デュアルプロセッサを想定して、スレッドプールの起動には約16ミリ秒かかります。 その後、スレッド プールの余分なコストはほとんどありません。

**/openmp**を使用してコンパイルする場合、スレッド プールの起動がないため **、/openmp-** を使用してコンパイルした場合より、test2 への 2 回目の呼び出しが実行されることはありません。 100 万回の反復で **、/openmp**バージョンは test2 への 2 回目の呼び出しの **/openmp-** バージョンよりも高速です。 25 回の反復では **、/openmp-** と **/openmp**の両方のバージョンがクロックの粒度よりも低く登録されます。

アプリケーションにループが 1 つしかなく、15 ミリ秒未満で実行されている場合 (コンピュータのおおよそのオーバーヘッドに合わせて調整 **)、/openmp**は適切でない可能性があります。 より高い場合は **、/openmp**を使用することを検討してください。

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

[MSVC コンパイラ オプション](compiler-options.md) \
[MSVC コンパイラ のコマンド ライン構文](compiler-command-line-syntax.md) \
[MSVC での OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)
