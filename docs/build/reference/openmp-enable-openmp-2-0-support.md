---
title: /openmp (OpenMP 2.0 サポートの有効化)
ms.date: 11/04/2016
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: f1edcc6d29a5b84106b3a5fd91d2446c34e0f7b9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807469"
---
# <a name="openmp-enable-openmp-20-support"></a>/openmp (OpenMP 2.0 サポートの有効化)

コンパイラで処理する`#pragma` [omp](../../preprocessor/omp.md)します。

## <a name="syntax"></a>構文

```
/openmp
```

## <a name="remarks"></a>Remarks

`#pragma omp` 指定するために使用[ディレクティブ](../../parallel/openmp/reference/openmp-directives.md)と[句](../../parallel/openmp/reference/openmp-clauses.md)します。 場合 **/openmp**が指定されていない、コンパイル時に、コンパイラは、OpenMP 句とディレクティブは無視されます。 [OpenMP 関数](../../parallel/openmp/reference/openmp-functions.md)呼び出しがあっても、コンパイラによって処理される **/openmp**が指定されていません。

コンパイルされたアプリケーション **/openmp**と **/clr** 1 つのアプリケーション ドメインのプロセスでのみ実行できます。 複数のアプリケーション ドメインはサポートされません。 つまり、モジュールのコンス トラクター (.cctor) が実行されるを検出し、プロセスをコンパイルした **/openmp**場合、既定以外のランタイム、アプリケーションが読み込まれるとします。 詳細については、次を参照してください。 [appdomain](../../cpp/appdomain.md)、 [/clr (共通言語ランタイムのコンパイル)](clr-common-language-runtime-compilation.md)、および[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)します。

コンパイルしたアプリケーションを読み込もうとした場合 **/openmp**と **/clr**を既定以外のアプリケーション ドメインに、<xref:System.TypeInitializationException>デバッガーの外部例外がスローされます、デバッガーで OpenMPWithMultipleAppdomainsException 例外がスローされます。

これらの例外は、次の状況でも発生します。

- アプリケーションをコンパイルした場合 **/clr**ではなく **/openmp**、既定以外のアプリケーション ドメインには、プロセスにコンパイルされたアプリケーションが含まれていますが、読み込まれた **/openmp**します。

- 渡す場合、 **/clr** regasm.exe などのユーティリティへのアプリケーション ([Regasm.exe (アセンブリ登録ツール)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool))、そのターゲット アセンブリを既定以外のアプリケーション ドメインに読み込まれます。

共通言語ランタイムのコード アクセス セキュリティは、OpenMP のリージョンで動作しません。 並列領域の外側 CLR コード アクセス セキュリティ属性を適用する場合、並行領域内有効にはありません。

Microsoft で作成はないことをお勧め **/openmp**部分的には、アプリケーションを使用して、呼び出し元を信頼された<xref:System.Security.AllowPartiallyTrustedCallersAttribute>、または任意の CLR コード アクセス セキュリティ属性。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. **[構成プロパティ]** ノードを展開します。

1. 展開、 **C/C++** ノード。

1. 選択、**言語**プロパティ ページ。

1. 変更、 **OpenMP サポート**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>

## <a name="example"></a>例

次の例と起動後に、threadpool を使用すると、スレッド プールの起動の影響の一部を示します。 仮定すると、x64、1 つのコア デュアル プロセッサ、threadpool は、スタートアップに 16 ミリ秒を移動します。 その後もごくわずかなコストは、threadpool の。

コンパイルするとき **/openmp**、test2、2 番目の呼び出しが不要でコンパイルする場合よりも実行されない **/openmp-** threadpool のスタートアップが存在しないため、します。 100万回反復、 **/openmp**バージョンがよりも高速、 **/openmp-** test2、および 25 のイテレーションでは、2 番目の呼び出しのバージョン **/openmp-** と **/openmp**クロック粒度よりも小さいバージョン登録します。

(コンピューターにオーバーヘッドの概算の調整) 使う未満で実行されるアプリケーションに 1 つだけのループがある場合 **/openmp**が適切ではありませんより長い場合は、の使用を検討することがあります **/openmp**します。

```
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

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)
