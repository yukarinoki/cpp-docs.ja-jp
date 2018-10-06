---
title: /NXCOMPAT (データ実行防止と互換性のある) |Microsoft Docs
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
ms.openlocfilehash: 431cd954845041a7a186a967c83df7ffb1aac788
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821674"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (データ実行防止との互換性)

実行可能ファイルが、Windows データ実行防止機能と互換性があることを示します。

## <a name="syntax"></a>構文

> **/NXCOMPAT****[: NO]**

## <a name="remarks"></a>Remarks

既定では、 **/NXCOMPAT**にします。

**/NXCOMPAT:NO**データ実行防止と互換性がないと、実行可能ファイルを明示的に指定するために使用できます。

データ実行防止の詳細については、以下を参照してください。

- [データ実行防止 (DEP) 機能の詳細な説明](https://support.microsoft.com/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

- [データ実行防止](/windows/desktop/Memory/data-execution-prevention)

- [データ実行防止 (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. オプションを入力して、**追加オプション**ボックス。 選択**OK**または**適用**して変更を適用します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
