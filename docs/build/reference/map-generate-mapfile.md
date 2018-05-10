---
title: マップ (マップ ファイルの生成) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
dev_langs:
- C++
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10f4b23cf8f1c05fb8bd196dc9a6cd54971b1572
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="map-generate-mapfile"></a>/MAP (マップ ファイルの生成)
```  
/MAP[:filename]  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 マップ ファイルのユーザー指定の名前。 既定の名前に置き換えます。  
  
## <a name="remarks"></a>コメント  
 /MAP オプションを使用すると、リンカーは、マップ ファイルを作成します。  
  
 既定では、名前にマップ ファイル、プログラム、および拡張 .map ベース名です。 省略可能な*filename*マップ ファイルの既定の名前をオーバーライドすることができます。  
  
 マップ ファイルは、リンクされているプログラムに関する次の情報を含むテキスト ファイルです。  
  
-   ファイルの基本名は、モジュール名、  
  
-   (ファイル システム) からではなく、プログラム ファイルのヘッダーからのタイムスタンプ  
  
-   各グループの開始アドレスを使用して、プログラム内のグループの一覧 (として*セクション*:*オフセット*)、長さ、グループ名、およびクラス  
  
-   各アドレスに、パブリック シンボルの一覧 (として*セクション*:*オフセット*)、シンボルの名前、フラットなアドレス、およびシンボルが定義されている .obj ファイル  
  
-   エントリ ポイント (として*セクション*:*オフセット*)  
  
 [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)オプションは、マップ ファイルに含まれる追加の情報を指定します。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**デバッグ**プロパティ ページ。  
  
4.  変更、**マップ ファイルの生成**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)