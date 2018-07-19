---
title: /FUNCTIONPADMIN (ホットパッチ可能なイメージの作成) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /functionpadmin
dev_langs:
- C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0a5ecfcc336e198de0adcc2393f740072d70cae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376755"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (ホットパッチ可能なイメージの作成)

ホットパッチ用のイメージを準備します。

## <a name="syntax"></a>構文

> **/FUNCTIONPADMIN**[**:**_space_]  

### <a name="arguments"></a>引数

*space*<br/>
(バイト単位) の各関数の先頭に追加するパディングの量。 X86 で既定値は 5 バイトのパディングと x64 の既定値は 6 バイトです。 他のターゲットに値を指定する必要があります。

## <a name="remarks"></a>コメント

ホットパッチ可能なイメージを生成するために、リンカーの順番は、.obj ファイル必要がありますしてコンパイルされている[/hotpatch (ホットパッチ可能なイメージの作成)](../../build/reference/hotpatch-create-hotpatchable-image.md)です。

コンパイルして単一の cl.exe、呼び出しでイメージを関連付ける **/hotpatch**意味 **/functionpadmin**です。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. 入力、 **/FUNCTIONPADMIN**オプション**追加オプション**です。 選択**OK**して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
