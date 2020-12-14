---
description: 詳細について:/INCLUDE (シンボル参照の強制)
title: /INCLUDE (シンボルの明示的な参照)
ms.date: 11/04/2016
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
ms.openlocfilehash: 4938f5e92f91718f522df103303e6382005d463c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191304"
---
# <a name="include-force-symbol-references"></a>/INCLUDE (シンボルの明示的な参照)

```
/INCLUDE:symbol
```

## <a name="parameters"></a>パラメーター

*表す*<br/>
シンボルテーブルに追加するシンボルを指定します。

## <a name="remarks"></a>解説

/INCLUDE オプションは、指定されたシンボルをシンボルテーブルに追加するようにリンカーに指示します。

複数のシンボルを指定するには、コンマ (,)、セミコロン (;)、またはシンボル名の間にスペースを入力します。 コマンドラインで、シンボルごとに/INCLUDE: once を指定し `symbol` ます。

`symbol`シンボル定義を含むオブジェクトをプログラムに追加することで、リンカーが解決されます。 この機能は、他の方法でプログラムにリンクしないライブラリオブジェクトを含める場合に便利です。

このオプションを使用してシンボルを指定すると、そのシンボルの削除は [/opt: REF](opt-optimizations.md)によってオーバーライドされます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **入力** ] プロパティページをクリックします。

1. " **シンボル参照の強制** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
