---
description: 詳細情報:/functionpadmin (Create Hotpatchable Image)
title: /FUNCTIONPADMIN (ホットパッチ可能なイメージの作成)
ms.date: 03/09/2018
f1_keywords:
- /functionpadmin
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
ms.openlocfilehash: f86adb2001adacf1b6c8a03a90b7452505841c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192006"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (ホットパッチ可能なイメージの作成)

ホットパッチ用のイメージを準備します。

## <a name="syntax"></a>構文

> **/Functionpadmin**[**:**_space_]

### <a name="arguments"></a>引数

*行間*<br/>
各関数の先頭に追加する埋め込みの量 (バイト単位)。 X86 では、これは既定で5バイトの余白で、x64 では既定で6バイトに設定されます。 他のターゲットでは、値を指定する必要があります。

## <a name="remarks"></a>解説

リンカーで hotpatchable イメージを生成するには、.obj ファイルが [/hotpatch (Create Hotpatchable image)](hotpatch-create-hotpatchable-image.md)を使用してコンパイルされている必要があります。

cl.exe の1回の呼び出しでイメージをコンパイルしてリンクすると、 **/hotpatch** は **/functionpadmin** を意味します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[リンカー]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. **追加のオプション** で、 **/functionpadmin** オプションを入力します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
