---
title: -LIBPATH (追加ライブラリのパス) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
dev_langs:
- C++
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ccb94ad20735e81fc3d83f757cc0265cdc32169
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="libpath-additional-libpath"></a>/LIBPATH (追加ライブラリのパス)
```  
/LIBPATH:dir  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 `dir`  
 パスを指定、LIB 環境オプションで指定されたパスを検索する前に、リンカーが検索されます。  
  
## <a name="remarks"></a>コメント  
 /LIBPATH オプションを使用して、環境ライブラリ パスをオーバーライドします。 リンカーは、まずこのオプションで指定されたパスで検索し、LIB 環境変数で指定されたパスで検索されます。 ディレクトリを入力する各/LIBPATH オプションを 1 つのみを指定することができます。 1 つ以上のディレクトリを指定する場合は、複数の/LIBPATH オプションを指定する必要があります。 リンカーの順序で指定されたディレクトリが検索されます。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**全般**プロパティ ページ。  
  
4.  変更、**追加のライブラリ ディレクトリ**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)