---
title: -NATVIS (Natvis を pdb ファイルに追加) |Microsoft ドキュメント
ms.date: 08/10/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /natvis
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs:
- C++
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3bce34095aec1558d2466447770a8ac4c46528f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="natvis-add-natvis-to-pdb"></a>/NATVIS (Natvis を pdb ファイルに追加する)
  
> /NATVIS:*ファイル名*  
  
## <a name="parameters"></a>パラメーター  
  
*ファイル名*  
PDB ファイルに追加する Natvis ファイル。 Natvis ファイルで、PDB にデバッガーの視覚化を埋め込みます。  
  
## <a name="remarks"></a>コメント  
  
/NATVIS オプションには、Natvis ファイルで定義されているデバッガーの視覚化が埋め込まれる*filename* LINK によって生成される PDB ファイルにします。 これにより、デバッガーは .natvis ファイルとは無関係に、視覚エフェクトを表示できます。 1 つ以上 Natvis ファイルを生成した PDB ファイルに埋め込むには、複数の/NATVIS オプションを使用できます。  
  
使用して PDB ファイルを作成していない場合、リンクが/NATVIS を無視する[/debug](../../build/reference/debug-generate-debug-info.md)オプション。 .Natvis ファイルの作成と使用については、次を参照してください。 [、Visual Studio デバッガーでのネイティブ オブジェクトのカスタム ビューを作成](/visualstudio/debugger/create-custom-views-of-native-objects)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**コマンドライン**プロパティ ページで、**リンカー**フォルダーです。  
  
3.  追加する/NATVIS オプション、**追加のオプション**テキスト ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   このオプションには、同等のプログラムはありません。  
  
## <a name="see-also"></a>関連項目  
  
[Visual Studio デバッガーでのネイティブ オブジェクトのカスタム ビューを作成します。](/visualstudio/debugger/create-custom-views-of-native-objects)  
[リンカー オプションの設定](../../build/reference/setting-linker-options.md)  
[リンカー オプション](../../build/reference/linker-options.md)