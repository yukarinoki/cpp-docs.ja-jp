---
description: 詳細情報:/nologo (著作権情報の非表示) (C/c + +)
title: /nologo (著作権情報の非表示) (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.SuppressStartupBanner
- VC.Project.VCCLCompilerTool.SuppressStartupBanner
helpviewer_keywords:
- -nologo compiler option [C++]
- /nologo compiler option [C++]
- nologo compiler option [C++]
- banners, suppressing startup
ms.assetid: 75930d8b-b11c-4db8-99e5-b52f97da0693
ms.openlocfilehash: a924eaf18a772b9495e1a493855fd72e9b79dd83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196608"
---
# <a name="nologo-suppress-startup-banner-cc"></a>/nologo (著作権情報の非表示) (C/C++)

コンパイラの起動時に著作権情報のバナーを表示しないようにし、コンパイル中に情報メッセージを表示しません。

## <a name="syntax"></a>構文

```
/nologo
```

## <a name="remarks"></a>解説

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **全般** ] プロパティページをクリックします。

1. " **スタートアップバナー** を表示しない" プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SuppressStartupBanner%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
