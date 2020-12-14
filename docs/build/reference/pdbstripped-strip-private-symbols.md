---
description: 詳細情報:/PDBSTRIPPED (プライベートシンボルの削除)
title: /PDBSTRIPPED (プライベート シンボルの除去)
ms.date: 11/04/2016
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
ms.openlocfilehash: 27e70281ad12f4401ad6557ead9be11a38684472
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226039"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (プライベート シンボルの除去)

```
/PDBSTRIPPED:pdb_file_name
```

## <a name="arguments"></a>引数

*pdb_file_name*<br/>
リンカーによって作成される、削除されたプログラムデータベース (PDB) のユーザー指定の名前。

## <a name="remarks"></a>解説

/PDBSTRIPPED オプションは、PDB ファイル ([/debug](debug-generate-debug-info.md)、 [/Z7](z7-zi-zi-debug-information-format.md)、/Zd、または/zi) を生成する任意のコンパイラオプションまたはリンカーオプションを使用してプログラムイメージをビルドするときに、2番目のプログラムデータベース (PDB) ファイルを作成します。 2 番目の PDB ファイルでは、顧客に提供しないシンボルが省かれています。 2番目の PDB ファイルには次のもののみが含まれます。

- パブリックシンボル

- オブジェクトファイルの一覧と、それらが参加する実行可能ファイルの部分

- フレームポインターの最適化 (FPO) スタックの走査に使用されるデバッグレコード

削除された PDB ファイルには次のものが含まれません。

- 型情報

- 行番号の情報

- オブジェクトごとのファイルの CodeView シンボル (関数、ローカル、静的データなど)

/PDBSTRIPPED. を使用すると、完全な PDB ファイルが生成されます。

PDB ファイルを作成しない場合、/PDBSTRIPPED は無視されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **デバッグ** ] プロパティページをクリックします。

1. " **プライベートシンボルの削除** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
