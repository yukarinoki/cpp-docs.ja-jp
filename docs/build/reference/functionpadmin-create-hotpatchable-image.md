---
title: /FUNCTIONPADMIN (ホットパッチ可能なイメージの作成)
ms.date: 03/09/2018
f1_keywords:
- /functionpadmin
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
ms.openlocfilehash: c1e84f308796eabcaea61518e3731f633c2f67e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474894"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (ホットパッチ可能なイメージの作成)

ホットパッチ用のイメージを準備します。

## <a name="syntax"></a>構文

> **/FUNCTIONPADMIN**[**:**_space_]

### <a name="arguments"></a>引数

*space*<br/>
(バイト単位) の各関数の先頭に追加するパディングの量。 X86 上でこの既定値は 5 バイトの埋め込みと x64 の既定値は 6 バイト。 他のターゲットに値を指定する必要があります。

## <a name="remarks"></a>Remarks

ホットパッチ可能なイメージを生成するために、リンカーのためには、.obj ファイルする必要がありますでコンパイルされている[/hotpatch (ホットパッチ可能なイメージの作成)](../../build/reference/hotpatch-create-hotpatchable-image.md)します。

コンパイルして、cl.exe の 1 つの呼び出しを使用してイメージをリンクするときに **/hotpatch**意味 **/functionpadmin**します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. 入力、 **/FUNCTIONPADMIN**オプション**追加オプション**します。 **OK** を選択して変更を保存してください。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
