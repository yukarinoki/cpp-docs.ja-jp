---
description: 詳細情報:/LIBPATH (追加 Libpath)
title: /LIBPATH (追加ライブラリのパス)
ms.date: 11/04/2016
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
ms.openlocfilehash: 5db7a0f80cb741a65bac5a4dbb7fd79e28b67459
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191031"
---
# <a name="libpath-additional-libpath"></a>/LIBPATH (追加ライブラリのパス)

```
/LIBPATH:dir
```

## <a name="parameters"></a>パラメーター

*dir*<br/>
LIB 環境オプションで指定されたパスを検索する前に、リンカーが検索するパスを指定します。

## <a name="remarks"></a>解説

/LIBPATH オプションを使用して、環境ライブラリパスをオーバーライドします。 リンカーは、まずこのオプションで指定されたパスを検索し、次に LIB 環境変数で指定されたパスを検索します。 入力する/LIBPATH オプションごとにディレクトリを1つだけ指定できます。 複数のディレクトリを指定する場合は、複数の/LIBPATH オプションを指定する必要があります。 リンカーは、指定されたディレクトリを順番に検索します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **全般** ] プロパティページをクリックします。

1. [ **追加のライブラリディレクトリ** のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
