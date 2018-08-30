---
title: -MANIFESTDEPENDENCY (マニフェストの依存関係の指定) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
dev_langs:
- C++
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d486047b708e0c3412aa63e0a0b026a2a4204f71
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213900"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (マニフェストの依存関係を指定する)
```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## <a name="remarks"></a>Remarks  
 /MANIFESTDEPENDENCY を使用してでは、属性を指定できます、\<依存関係 > マニフェスト ファイルのセクション。  
  
 参照してください[/MANIFEST (アセンブリ マニフェストを作成して並列)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)についてはマニフェスト ファイルを作成する方法。  
  
 詳細については、\<依存関係 > セクションのマニフェスト ファイルを参照してください。[発行者構成ファイル](/windows/desktop/SbsCs/publisher-configuration-files)します。  
  
 /MANIFESTDEPENDENCY 情報は、2 つの方法のいずれかでリンカーに渡すことができます。  
  
-   コマンドラインで直接 (または応答ファイル内)/MANIFESTDEPENDENCY を使用します。  
  
-   使用して、[コメント](../../preprocessor/comment-c-cpp.md)プラグマ。  
  
 次の例では、プラグマを使用して渡す/MANIFESTDEPENDENCY コメント  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 その結果、マニフェスト ファイルで次のエントリには。  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 同じ/MANIFESTDEPENDENCY コメントは、コマンドラインで渡されることができます。  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 リンカーは/MANIFESTDEPENDENCY コメントの収集、重複するエントリを削除し、マニフェスト ファイルに結果の XML 文字列を追加します。  リンカーは、競合するエントリを検出します。、マニフェスト ファイルは破損し、アプリケーションは起動に失敗場合、(エントリは、エラーの原因を示す、イベント ログに追加される可能性があります)。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **[構成プロパティ]** ノードを展開します。  
  
3.  展開、**リンカー**ノード。  
  
4.  選択、**マニフェスト ファイル**プロパティ ページ。  
  
5.  変更、**追加のマニフェストの依存関係**プロパティ。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)