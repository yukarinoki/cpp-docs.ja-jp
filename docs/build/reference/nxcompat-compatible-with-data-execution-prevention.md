---
title: /NXCOMPAT (データ実行防止との互換性)
ms.date: 12/29/2017
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: a8550337189f9c92a1c8a8d86f2f9b2b829bbc3e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813319"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (データ実行防止との互換性)

実行可能ファイルが、Windows データ実行防止機能と互換性があることを示します。

## <a name="syntax"></a>構文

> **/NXCOMPAT****[:NO]**

## <a name="remarks"></a>Remarks

既定では、 **/NXCOMPAT**にします。

**/NXCOMPAT:NO**データ実行防止と互換性がないと、実行可能ファイルを明示的に指定するために使用できます。

データ実行防止の詳細については、以下を参照してください。

- [データ実行防止 (DEP) 機能の詳細な説明](https://support.microsoft.com/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

- [データ実行防止](/windows/desktop/Memory/data-execution-prevention)

- [データ実行防止 (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. オプションを入力して、**追加オプション**ボックス。 選択**OK**または**適用**して変更を適用します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
