---
title: /ERRORREPORT (内部リンカー エラーの報告)
description: /Errorreportを使用する方法について説明します。
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
ms.openlocfilehash: 7d16904da8490018235278347f23e37339739415
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742737"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (内部リンカー エラーの報告)

**/Errorreport**オプションは非推奨とされます。 Windows Vista 以降では、エラー報告は [Windows エラー報告 (WER)](/windows/win32/wer/windows-error-reporting) 設定によって制御されます。

## <a name="syntax"></a>構文

> **/Errorreport:** \[**なし** \|**プロンプト** \|**キュー** \|**送信**]

## <a name="remarks"></a>注釈

**/Errorreport**引数は、Windows エラー報告サービスの設定によってオーバーライドされます。 レポートが Windows エラー報告によって有効になっている場合、リンカーは内部エラーのレポートを Microsoft に自動的に送信します。 Windows エラー報告で無効になっている場合、レポートは送信されません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. **構成プロパティ**の  >  **Linker**  >  **[詳細**設定] プロパティページを開きます。

1. **エラー報告**のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーリファレンス](linking.md)\
[MSVC リンカー オプション](linker-options.md)
