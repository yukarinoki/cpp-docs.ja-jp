---
title: -Oi (組み込み関数の生成) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
dev_langs:
- C++
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f28051f5d7aaaa4606fffa4d4c94fb2086031419
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375842"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (組み込み関数の生成)
置換関数は、アプリケーションに役立つ固有またはそれ以外の場合に特別な形式と一部の関数の呼び出しの実行速度が向上します。  
  
## <a name="syntax"></a>構文  
  
```  
/Oi[-]  
```  
  
## <a name="remarks"></a>コメント  
 組み込み関数を使用するプログラムは、高速ため、関数呼び出しのオーバーヘッドはありませんが、コードを追加する作成ので大きい可能性があります。  
  
 参照してください[組み込み](../../preprocessor/intrinsic.md)詳細については関数が組み込み形式があります。  
  
 **/Oi**に一部の関数呼び出しを置き換える組み込み; コンパイラに要求のみコンパイラ可能性があります、関数を呼び出す (および関数呼び出しを組み込みで置き換える) のパフォーマンスが向上が得られる場合です。  
  
 **x86 固有**  
  
 浮動小数点の組み込み関数がなく入力値に特別なセキュリティ チェックを実行し、ので、入力の制限の範囲で作業、別の例外処理と同じ名前のライブラリ ルーチンより境界条件。 本物の組み込み形式を使用して、IEEE 例外処理の損失とのことを意味`_matherr`と`errno`機能です。 後者の ANSI 規格適合性が失われることを意味します。 ただし、組み込み形式は浮動小数点を多用するプログラムをかなり高速化できますされ、多くのプログラムの準拠の問題の実践的な価値はほとんどありません。  
  
 使用することができます、 [Za](../../build/reference/za-ze-disable-language-extensions.md)コンパイラ オプションの場合は true。 組み込み浮動小数点オプションの生成をオーバーライドします。 浮動小数点関数はライブラリ ルーチンとして生成されます。これらのライブラリ ルーチンでは、引数はプログラム スタックにプッシュされずに、数値演算コプロセッサに直接渡されます。  
  
 **END x86 固有**  
  
 使用することも[組み込み](../../preprocessor/intrinsic.md)の組み込み関数を作成するか、[関数 (C++)](../../preprocessor/function-c-cpp.md)関数呼び出しを明示的に強制します。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**最適化**プロパティ ページ。  
  
4.  変更、**組み込み関数を有効にする**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [コンパイラの組み込み](../../intrinsics/compiler-intrinsics.md)