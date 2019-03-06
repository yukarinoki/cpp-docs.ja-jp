---
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
ms.openlocfilehash: 4b6490186e2faf289844f7fb6b84f5a1c27b10a5
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423505"
---
# <a name="def-specify-module-definition-file"></a>/DEF (モジュール定義ファイルの指定)

```
/DEF:filename
```

## <a name="arguments"></a>引数

*ファイル名*<br/>
モジュール定義ファイル (.def) がリンカーに渡されるの名前。

## <a name="remarks"></a>Remarks

/DEF オプションは、モジュール定義ファイル (.def) をリンカーに渡します。 1 つだけの .def ファイルは、リンクを指定できます。 詳細については、.def ファイルは、次を参照してください。[モジュール定義ファイル](../../build/reference/module-definition-dot-def-files.md)します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**入力**プロパティ ページ。

1. 変更、**モジュール定義ファイル**プロパティ。

開発環境での .def ファイルを指定するには、と他のファイル プロジェクトに追加してから/DEF オプションにファイルを指定ください。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
