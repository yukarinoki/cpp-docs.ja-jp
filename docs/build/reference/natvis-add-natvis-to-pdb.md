---
title: -NATVIS (PDB に Natvis を追加する) |Microsoft Docs
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
ms.openlocfilehash: 2c1a20fef785c0267eb630bf044c8cb9609605e2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45708124"
---
# <a name="natvis-add-natvis-to-pdb"></a>/NATVIS (PDB に Natvis を追加する)

> /NATVIS:*ファイル名*

## <a name="parameters"></a>パラメーター

*ファイル名*<br/>
PDB ファイルに追加する Natvis ファイル。 Natvis ファイルの PDB にデバッガーの視覚化を埋め込みます。

## <a name="remarks"></a>Remarks

/NATVIS オプションには、Natvis ファイルで定義されているデバッガーの視覚化が埋め込まれる*filename* LINK によって生成される PDB ファイルにします。 これにより、デバッガーは .natvis ファイルとは無関係に視覚エフェクトを表示できます。 1 つ以上の Natvis ファイルを生成される PDB ファイルに埋め込むには、複数の/NATVIS オプションを使用できます。

使用して PDB ファイルが作成されていない場合、リンクが/NATVIS を無視する[/debug](../../build/reference/debug-generate-debug-info.md)オプション。 .Natvis ファイルの作成と使用については、次を参照してください。 [Visual Studio デバッガーでネイティブ オブジェクトのカスタム ビューの作成](/visualstudio/debugger/create-custom-views-of-native-objects)です。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. 選択、**コマンドライン**プロパティ ページで、**リンカー**フォルダー。

1. /NATVIS オプションを追加、**追加オプション**テキスト ボックス。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- このオプションでは、同等のプログラムはありません。

## <a name="see-also"></a>関連項目

[Visual Studio デバッガーでネイティブ オブジェクトのカスタム ビューを作成します。](/visualstudio/debugger/create-custom-views-of-native-objects)<br/>
[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)