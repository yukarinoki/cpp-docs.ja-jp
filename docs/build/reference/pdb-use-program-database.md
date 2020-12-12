---
description: 詳細については、「/PDB (プログラムデータベースの使用)」を参照してください。
title: /PDB (プログラム データベースの使用)
ms.date: 11/04/2016
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
ms.openlocfilehash: 221d5d81dc3578e99751334b2e0a0a61aaaed356
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226104"
---
# <a name="pdb-use-program-database"></a>/PDB (プログラム データベースの使用)

```
/PDB:filename
```

## <a name="arguments"></a>引数

*filename*<br/>
リンカーによって作成されるプログラムデータベース (PDB) のユーザー指定の名前。 既定の名前を置き換えます。

## <a name="remarks"></a>解説

既定では、 [/debug](debug-generate-debug-info.md) を指定すると、デバッグ情報を保持するプログラムデータベース (PDB) がリンカーによって作成されます。 PDB の既定のファイル名には、プログラムの基本名と拡張子 .pdb が使用されます。

PDB ファイルの名前を指定するには、/PDB:*filename* を使用します。 /DEBUG が指定されていない場合、/PDB オプションは無視されます。

PDB ファイルには、最大 2 GB まで指定できます。

詳細については、「 [リンカー入力としての .Pdb ファイル](dot-pdb-files-as-linker-input.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **デバッグ** ] プロパティページをクリックします。

1. " **プログラムデータベースファイルの生成** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
