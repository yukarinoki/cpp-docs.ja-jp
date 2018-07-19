---
title: -Wp64 (64 ビット移植に関する問題の検出) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
dev_langs:
- C++
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 295f2f690cb3c9db17a410cea1f23d04e54b0054
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379173"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (64 ビット移植性の問題の検出)

このコンパイラ オプションは廃止されました。 Visual Studio 2013 より前の Visual Studio のバージョンでは、このオプションは、 [__w64](../../cpp/w64.md) キーワードでもマークされている型の 64 ビット移植性の問題を検出します。  
  
## <a name="syntax"></a>構文  
  
```  
/Wp64  
```  
  
## <a name="remarks"></a>コメント  

既定では、Visual Studio 2013 より前に、の Visual Studio のバージョンでは、 **/Wp64**コンパイラ オプションが 32 ビット x86 をビルドする Visual C コンパイラではオフ、コードの Visual C コンパイラでビルドする 64 ビット、x64 およびコード。  
  
> [!IMPORTANT]
>  
  [/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) コンパイラ オプションと [__w64](../../cpp/w64.md) キーワードは、Visual Studio 2010 および Visual Studio 2012 で非推奨となり、Visual Studio 2013 以降ではサポートされません。 このスイッチを使用するプロジェクトを変換すると、変換中にスイッチは移行されません。 このオプションを Visual Studio 2010 または Visual Studio 2012 で使用するには、プロジェクト プロパティの **[コマンド ライン]** セクションの **[追加オプション]** で、コンパイラ スイッチを入力する必要があります。 コマンド ラインから **/Wp64** コンパイラ オプションを使用すると、コンパイラはコマンド ラインの警告 D9002 を発行します。 このオプションとキーワードを使用して 64 ビット移植に関する問題を検出する代わりに、64 ビット プラットフォームに対応する Visual C++ コンパイラを使用して、 [/W4](../../build/reference/compiler-option-warning-level.md) オプションを指定します。 詳細については、次を参照してください。 [64 ビット、x64 用の Visual c の構成のターゲット](../../build/configuring-programs-for-64-bit-visual-cpp.md)です。  
  
次の型の変数は、64 ビット オペレーティング システムで使用されている場合と同様に、32 ビットのオペレーティング システムでテストされます。  
  
-   int  
  
-   long  
  
-   pointer  
  
 64 ビット、x64 を構築するコンパイラを使用して定期的に、アプリケーションをコンパイルする場合、コードだけを無効にできます **/Wp64** 32 ビットのコンパイル時に、64 ビットのコンパイラがすべての問題を検出するためです。 ターゲット Windows 64 ビットのオペレーティング システムをする方法の詳細については、次を参照してください。 [64 ビット、x64 用の Visual c の構成のターゲット](../../build/configuring-programs-for-64-bit-visual-cpp.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。  
  
     詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **/Wp64** を含めるよう **[詳細オプション]** ボックスを変更します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  

[コンパイラ オプション](../../build/reference/compiler-options.md)   
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
[64 ビット、x64 ターゲット用の Visual C の構成](../../build/configuring-programs-for-64-bit-visual-cpp.md)