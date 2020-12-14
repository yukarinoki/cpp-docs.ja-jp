---
description: 詳細情報:/DEF (Module-Definition ファイルの指定)
title: /DEF (モジュール定義ファイルの指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
ms.openlocfilehash: 3b9178004621a55f999f7c2636eaa5b697d2de98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201704"
---
# <a name="def-specify-module-definition-file"></a>/DEF (モジュール定義ファイルの指定)

```
/DEF:filename
```

## <a name="arguments"></a>引数

*filename*<br/>
リンカーに渡されるモジュール定義ファイル (.def) の名前です。

## <a name="remarks"></a>解説

/DEF オプションを指定すると、モジュール定義ファイル (.def) がリンカーに渡されます。 リンク先として指定できる .def ファイルは1つだけです。 .Def ファイルの詳細については、「 [モジュール定義ファイル](module-definition-dot-def-files.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **入力** ] プロパティページをクリックします。

1. **モジュール定義ファイル** のプロパティを変更します。

開発環境内から .def ファイルを指定するには、そのファイルを他のファイルと共にプロジェクトに追加し、そのファイルを/DEF オプションに指定する必要があります。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
