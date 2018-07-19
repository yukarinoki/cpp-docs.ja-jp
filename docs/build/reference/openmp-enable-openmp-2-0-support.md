---
title: openmp (OpenMP 2.0 サポートを有効にする) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
dev_langs:
- C++
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe64011f48255a18aa8f8ccab7571533540a598a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378731"
---
# <a name="openmp-enable-openmp-20-support"></a>/openmp (OpenMP 2.0 サポートの有効化)
コンパイラで処理する`#pragma` [omp](../../preprocessor/omp.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
/openmp  
```  
  
## <a name="remarks"></a>コメント  
 `#pragma omp` 使用して指定[ディレクティブ](../../parallel/openmp/reference/openmp-directives.md)と[句](../../parallel/openmp/reference/openmp-clauses.md)です。 場合 **/openmp**が指定されていない、コンパイル時に、コンパイラは、OpenMP 句およびディレクティブは無視されます。 [OpenMP 関数](../../parallel/openmp/reference/openmp-functions.md)いなくても、コンパイラによって呼び出しが処理されます **/openmp**が指定されていません。  
  
 コンパイルされたアプリケーション **/openmp**と **/clr** 1 つのアプリケーション ドメインのプロセスでのみ実行できます。 複数のアプリケーション ドメインはサポートされません。 つまり、モジュール コンス トラクター (.cctor) の実行時に検出プロセスのコンパイルでは **/openmp**場合は既定ではないランタイム、アプリケーションが読み込まれるとします。 詳細については、次を参照してください。 [appdomain](../../cpp/appdomain.md)、 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)、および[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)です。  
  
 コンパイルしたアプリケーションを読み込もうとすると場合 **/openmp**と **/clr**を既定以外のアプリケーション ドメインに、<xref:System.TypeInitializationException>デバッガーの外部例外がスローされます、デバッガーで OpenMPWithMultipleAppdomainsException 例外がスローされます。  
  
 これらの例外は、次の状況でも発生します。  
  
-   アプリケーションがコンパイルされた場合 **/clr**が、 **/openmp**、既定以外のアプリケーション ドメインには、プロセスがでコンパイルされたアプリケーションに含まれる場合は、読み込まれて **/openmp**です。  
  
-   渡す場合、 **/clr** regasm.exe などのユーティリティへのアプリケーション ([Regasm.exe (アセンブリ登録ツール)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool))、既定以外のアプリケーション ドメインにターゲット アセンブリは、これによって読み込まれます。  
  
 共通言語ランタイムのコード アクセス セキュリティは、OpenMP の地域で機能しません。 場合は、並列領域の外側 CLR コード アクセス セキュリティ属性を適用すると、有効で、並行領域内ことができなきます。  
  
 Microsoft で作成しないことをお勧め **/openmp**により、部分的にアプリケーションを使用して、呼び出し元を信頼された<xref:System.Security.AllowPartiallyTrustedCallersAttribute>、または任意の CLR コード アクセス セキュリティ属性。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、 **C/C++** ノード。  
  
4.  選択、**言語**プロパティ ページ。  
  
5.  変更、 **OpenMP サポート**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、スレッド プールの起動と起動後、スレッド プールを使用すると場合の影響の一部を示します。 X64、1 つのコアを想定してデュアル プロセッサ、スレッド プールは、スタートアップに 16 ミリ秒を移動します。 その後もがスレッド プールのコストが非常に低いです。  
  
 コンパイルするときに **/openmp**、test2 を 2 番目の呼び出しが不要でコンパイルする場合よりも実行されない **/openmp-** threadpool スタートアップが存在しないため、します。 100万回反復、 **/openmp**バージョンがよりも高速、 **/openmp-** test2 および 25 のイテレーションでは、2 番目の呼び出しのバージョン **/openmp-** と **/openmp**クロック粒度よりも小さいバージョン登録します。  
  
 アプリケーションで 1 つだけのループがあるし、(コンピューター上のオーバーヘッドの概算の調整された) を使う未満で実行される場合は **/openmp**は適していない可能性がありますより長いである場合は、の使用を検討することができます **/openmp**です。  
  
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
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)