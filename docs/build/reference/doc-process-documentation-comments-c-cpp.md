---
title: -doc (ドキュメント コメントの処理) (C/C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs:
- C++
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 899ff6b774c365ce9df3019ef5ba6d08d0d7b93d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (ドキュメント コメントの処理) (C/C++)
コンパイラがドキュメント コメントの処理にソース コード ファイル内およびドキュメントのコメントのある各ソース コード ファイルの .xdc ファイルを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
/doc[name]  
```  
  
## <a name="arguments"></a>引数  
 `name`  
 コンパイラで作成される .xdc ファイルの名前。 1 つの .cpp ファイルがコンパイル時に渡されるときにのみ有効です。  
  
## <a name="remarks"></a>コメント  
 .Xdc ファイルは、xdcmake.exe を .xml ファイルに処理されます。 詳細については、次を参照してください。 [XDCMake リファレンス](../../ide/xdcmake-reference.md)です。  
  
 ソース コード ファイルには、ドキュメントのコメントを追加できます。 詳細については、次を参照してください。[ドキュメント コメントとして推奨されるタグ](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md)です。  
  
 IntelliSense を備えた、生成された .xml ファイルを使用するには、.xml ファイルをサポートし、.xml ファイルを格納するアセンブリと同じアセンブリと同じディレクトリ内のファイル名を確認します。 アセンブリが、Visual Studio プロジェクトで参照されている場合、.xml ファイルも存在します。 詳細については、次を参照してください。 [IntelliSense の使用](/visualstudio/ide/using-intellisense)と[XML コード コメント](/visualstudio/ide/supplying-xml-code-comments)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、 **C/C++** ノード。  
  
4.  選択、**出力ファイル**プロパティ ページ。  
  
5.  変更、 **XML ドキュメント ファイルの生成**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)