---
description: 詳細情報:/スタブ (MS-DOS スタブファイル名)
title: /STUB (MS-DOS スタブ ファイル名)
ms.date: 11/04/2016
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
ms.openlocfilehash: 34f3cd71ce66cb6695a58707fd84de79f7a14b1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230303"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (MS-DOS スタブ ファイル名)

```
/STUB:filename
```

## <a name="arguments"></a>引数

*filename*<br/>
MS-DOS アプリケーション。

## <a name="remarks"></a>解説

/スタブオプションは、MS-DOS スタブプログラムを Win32 プログラムにアタッチします。

ファイルが MS-DOS で実行される場合、スタブプログラムが呼び出されます。 通常、適切なメッセージが表示されます。ただし、任意の有効な MS-DOS アプリケーションをスタブプログラムにすることができます。

コロンの後にスタブプログラムの *ファイル名* を指定します (:)コマンドラインを実行します。 リンカーはファイル *名* を確認し、ファイルが実行可能ファイルでない場合はエラーメッセージを発行します。 プログラムは .exe ファイルである必要があります。.com ファイルはスタブプログラムに対して無効です。

このオプションを使用しない場合、リンカーは、次のメッセージを発行する既定のスタブプログラムをアタッチします。

```
This program cannot be run in MS-DOS mode.
```

仮想デバイスドライバーを構築するときに、ファイル名によって、ユーザーは IMAGE_DOS_HEADER 構造 (WINNT に定義されて *いる) を* 含むファイル名を指定できます。H) は、既定のヘッダーではなく、VXD で使用されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [ **追加オプション** ] ボックスにオプションを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
