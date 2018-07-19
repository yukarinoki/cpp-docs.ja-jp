---
title: -OUT (出力ファイル名) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
dev_langs:
- C++
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fd9ec1b1631104355e076071370f627a36b4037
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376106"
---
# <a name="out-output-file-name"></a>/OUT (出力ファイル名)
```  
/OUT:filename  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 出力ファイルのユーザー指定の名前。 既定の名前に置き換えます。  
  
## <a name="remarks"></a>コメント  
 /OUT オプションでは、既定の名前と、リンカーによって作成されるプログラムの場所を上書きします。  
  
 既定では、リンカーは、指定された最初の .obj ファイル (.exe または .dll)、適切な拡張のベース名を使用して、ファイル名を形成します。  
  
 マップまたはインポート ライブラリの既定の基本名は、このオプションです。 詳細については、「[マップ ファイルの生成](../../build/reference/map-generate-mapfile.md)(/map) と[/IMPLIB](../../build/reference/implib-name-import-library.md)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**全般**プロパティ ページ。  
  
4.  変更、**出力ファイル**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)