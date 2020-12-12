---
description: 詳細については、次を参照してください:/NATVIS (PDB に Natvis を追加)
title: /NATVIS (PDB への Natvis の追加)
ms.date: 08/10/2017
f1_keywords:
- /natvis
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
ms.openlocfilehash: 7703915591a59a558c8580dd64b9be22d281d784
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190524"
---
# <a name="natvis-add-natvis-to-pdb"></a>/NATVIS (PDB への Natvis の追加)

> /NATVIS:*ファイル名*

## <a name="parameters"></a>パラメーター

*filename*<br/>
PDB ファイルに追加する Natvis ファイル。 Natvis ファイル内のデバッガーの視覚化を PDB に埋め込みます。

## <a name="remarks"></a>解説

/NATVIS オプションは、Natvis ファイル *filename* に定義されているデバッガーの視覚化を、LINK によって生成される PDB ファイルに埋め込みます。 これにより、デバッガーは natvis ファイルとは別に視覚化を表示できます。 複数の/NATVIS オプションを使用して、生成された PDB ファイルに複数の Natvis ファイルを埋め込むことができます。

[/Debug](debug-generate-debug-info.md)オプションを使用して PDB ファイルが作成されていない場合、LINK は/NATVIS を無視します。 Natvis ファイルの作成と使用の詳細については、「 [Visual Studio デバッガーでのネイティブオブジェクトのカスタムビューの作成](/visualstudio/debugger/create-custom-views-of-native-objects)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**リンカー** ] フォルダーの [**コマンドライン**] プロパティページを選択します。

1. [ **追加のオプション** ] テキストボックスに/NATVIS オプションを追加します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- このオプションには、プログラムに相当するものはありません。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
