---
title: 増分 (インクリメンタル リンク) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /incremental
- VC.Project.VCLinkerTool.LinkIncremental
dev_langs:
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- -INCREMENTAL linker option
- INCREMENTAL linker option
- link incrementally option
- LINK tool [C++], options for full linking
- incremental linking
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7495b3dda7b79f45045176fc949016f89c92506a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376482"
---
# <a name="incremental-link-incrementally"></a>/INCREMENTAL (インクリメンタル リンクを行う)
```  
/INCREMENTAL[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 リンカーによる、インクリメンタル リンクの処理方法を制御します。  
  
 既定では、インクリメンタル リンクは実行されます。 既定で設定されたインクリメンタル リンクを無効にするには、/INCREMENTAL:NO と指定します。  
  
 インクリメンタル リンクされたプログラムは、機能的には、非インクリメンタル リンクされているプログラムです。 ただし、以降のインクリメンタル リンクでインクリメンタル リンクされた実行可能ファイル、スタティック ライブラリ、またはダイナミック リンク ライブラリ ファイル用に準備には。  
  
-   非インクリメンタル リンクされたプログラムよりも大きいためのコードとデータの埋め込みです。 余白は、ファイルを再作成しない限り関数とデータのサイズが増加するようにリンカーを使用できます。  
  
-   ジャンプ サンクを使って、新しいアドレスに関数を再配置する場合があります。  
  
    > [!NOTE]
    >  最終リリース ビルドに埋め込みやサンクが含まれていないことを確認してください、プログラムを非インクリメンタル リンクします。  
  
 既定の設定に関係なくインクリメンタル リンクを行うには、/INCREMENTAL と指定します。 このオプションを選択すると、リンカーは、リンクを実行できない場合に警告を発行し、プログラムを非インクリメンタル リンクします。 一部のオプションや状況によっては、/INCREMENTAL が無効になる場合もあります。  
  
 大半のプログラムでは、インクリメンタル リンクができます。 ただし、変更箇所が大きすぎたり、インクリメンタル リンクと矛盾するオプションが指定されていると、実行できません。 フル リンクを実行するには、次のいずれかを行います。  
  
-   インクリメンタル リンクをオフ (/INCREMENTAL:NO) にする。  
  
-   /OPT:REF オプションを指定する。  
  
-   /OPT:ICF オプションを指定する。  
  
-   /OPT:LBR オプションを指定する。  
  
-   /ORDER オプションを指定する。  
  
 /INCREMENTAL が暗黙的に指定すると[/debug](../../build/reference/debug-generate-debug-info.md)を指定します。  
  
 以下の場合もフル リンクが行われます。  
  
-   インクリメンタル ステータス (.ilk) ファイルが見つからない場合。 LINK では、以降のインクリメンタル リンク用に新しい .ilk ファイルを作成します。  
  
-   .ilk ファイルに対する書き込み権限がない場合。 (リンクを無視する .ilk ファイルとリンク非増分します。)  
  
-   出力ファイル .exe または .dll が見つからない場合。  
  
-   .ilk、.exe、または .dll のタイムスタンプを変更した場合。  
  
-   LINK オプションを変更した場合。 ビルド間で LINK オプションを変更すると、ほとんどの場合、フル リンクが行われます。  
  
-   オブジェクト (.obj) ファイルを追加または省略した場合。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**リンカー**フォルダーです。  
  
3.  **[全般]** プロパティ ページをクリックします。  
  
4.  変更、**インクリメンタル リンクを有効にする**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)