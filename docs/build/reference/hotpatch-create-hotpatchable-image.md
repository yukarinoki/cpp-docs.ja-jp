---
description: 詳細については、次を参照してください:/hotpatch (Hotpatchable イメージの作成)
title: /hotpatch (ホットパッチ可能なイメージの作成)
ms.date: 11/12/2018
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: 2fc5fe629afcb1e721943b852c6f92351900ab7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199871"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (ホットパッチ可能なイメージの作成)

イメージをホットパッチできるようにします。

## <a name="syntax"></a>構文

```
/hotpatch
```

## <a name="remarks"></a>解説

コンパイルで **/hotpatch** を使用すると、コンパイラは各関数の最初の命令が少なくとも2バイトであることを確認します。これはホットパッチに必要です。

イメージを hotpatchable するための準備を完了するには、 **/hotpatch** を使用してコンパイルした後、 [/functionpadmin (Create hotpatchable image)](functionpadmin-create-hotpatchable-image.md) を使用してリンクする必要があります。 cl.exe の1回の呼び出しを使用してイメージをコンパイルおよびリンクする場合、 **/hotpatch** は **/functionpadmin** を意味します。

命令は ARM アーキテクチャでは常に2バイト以上であるため、x64 コンパイルは **/hotpatch** が指定されているかのように常に処理されるため、これらのターゲットに対してコンパイルするときに **/hotpatch** を指定する必要はありません。ただし、hotpatchable イメージを作成するには、 **/functionpadmin** を使用してリンクする必要があります。 **/Hotpatch** コンパイラオプションは、x86 コンパイルにのみ影響します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **C/c + +** ] フォルダーを選択します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. [ **追加オプション** ] ボックスにコンパイラオプションを追加します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
