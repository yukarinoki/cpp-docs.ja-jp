---
description: 詳細については、次を参照してください:/INCREMENTAL (インクリメンタルリンク)
title: /INCREMENTAL (インクリメンタル リンクを行う)
ms.date: 11/04/2016
f1_keywords:
- /incremental
- VC.Project.VCLinkerTool.LinkIncremental
helpviewer_keywords:
- /INCREMENTAL linker option
- -INCREMENTAL linker option
- INCREMENTAL linker option
- link incrementally option
- LINK tool [C++], options for full linking
- incremental linking
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
ms.openlocfilehash: 4b115bd88bed5b012c29c3d0e61d471aa869b78a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191291"
---
# <a name="incremental-link-incrementally"></a>/INCREMENTAL (インクリメンタル リンクを行う)

```
/INCREMENTAL[:NO]
```

## <a name="remarks"></a>解説

リンカーによる、インクリメンタル リンクの処理方法を制御します。

既定では、インクリメンタル リンクは実行されます。 既定で設定されたインクリメンタル リンクをオーバーライドするには、/INCREMENTAL:NO と指定します。

インクリメンタルリンクされたプログラムは、非インクリメンタルリンクされていないプログラムと機能的には同等です。 ただし、それ以降の増分リンクのために準備されているため、インクリメンタルリンクされた実行可能ファイル、スタティックライブラリ、またはダイナミックリンクライブラリファイルは次のとおりです。

- は、コードとデータが埋め込まれているため、インクリメンタルリンクされていないプログラムより大きくなっています。 埋め込みにより、リンカーはファイルを再作成することなく、関数およびデータのサイズを増やすことができます。

- ジャンプ サンクを使って、新しいアドレスに関数を再配置する場合があります。

   > [!NOTE]
   > 最終リリースビルドに埋め込みまたはサンクが含まれないようにするには、プログラムを段階的にリンクしないようにします。

既定の設定に関係なくインクリメンタル リンクを行うには、/INCREMENTAL と指定します。 このオプションを選択すると、リンカーはインクリメンタルリンクできない場合に警告を発行し、プログラムを段階的にリンクしません。 一部のオプションや状況によっては、/INCREMENTAL がオーバーライドされる場合もあります。

大半のプログラムでは、インクリメンタル リンクができます。 ただし、変更箇所が大きすぎたり、インクリメンタル リンクと矛盾するオプションが指定されていると、実行できません。 フル リンクを実行するには、次のいずれかを行います。

- インクリメンタル リンクをオフ (/INCREMENTAL:NO) にする。

- /OPT:REF オプションを指定する。

- /OPT:ICF オプションを指定する。

- /OPT:LBR オプションを指定する。

- /ORDER オプションを指定する。

/INCREMENTAL は、 [/debug](debug-generate-debug-info.md) が指定されている場合に暗黙的に指定されます。

以下の場合もフル リンクが行われます。

- インクリメンタル ステータス (.ilk) ファイルが見つからない場合。 LINK では、以降のインクリメンタル リンク用に新しい .ilk ファイルを作成します。

- .ilk ファイルに対する書き込み権限がない場合。 (リンクは、.ilk ファイルを無視し、リンクを非インクリメンタルにします)。

- 出力ファイル .exe または .dll が見つからない場合。

- .ilk、.exe、または .dll のタイムスタンプを変更した場合。

- LINK オプションを変更した場合。 ビルド間で LINK オプションを変更すると、ほとんどの場合、フル リンクが行われます。

- オブジェクト (.obj) ファイルを追加または省略した場合。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーを選択します。

1. **[全般]** プロパティ ページをクリックします。

1. " **インクリメンタルリンクを有効にする** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
