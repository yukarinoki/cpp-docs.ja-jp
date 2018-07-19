---
title: /NXCOMPAT (データ実行防止と互換性のある) |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /NXCOMPAT
dev_langs:
- C++
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb4f8a91545a196bc92fdc0ec44e89a7d5680185
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374805"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (データ実行防止との互換性)

実行可能ファイルに、Windows データ実行防止機能と互換性があることを示します。

## <a name="syntax"></a>構文

> **/NXCOMPAT****[: いいえ]**

## <a name="remarks"></a>コメント

既定では、 **/NXCOMPAT**にします。

**/NXCOMPAT:NO**データ実行防止と互換性がないと、実行可能ファイルを明示的に指定するために使用できます。

データ実行防止の詳細については、以下を参照してください。

- [データ実行防止 (DEP) 機能の詳細な説明](http://go.microsoft.com/fwlink/p/?linkid=157771)

- [データ実行防止](http://go.microsoft.com/fwlink/p/?linkid=157770)

- [データ実行防止 (Windows Embedded)](http://go.microsoft.com/fwlink/p/?linkid=157768)

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. オプションを入力して、**追加オプション**ボックス。 選択**OK**または**適用**変更を適用します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)  
[リンカー オプション](../../build/reference/linker-options.md)  
