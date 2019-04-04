---
title: /bigobj (.obj ファイル内のセクションの数を増やす)
ms.date: 03/26/2019
f1_keywords:
- /bigobj
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
ms.openlocfilehash: 46399dc0c1ff552b4fc963b686ac6aa6df8b6f71
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508716"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (.obj ファイル内のセクションの数を増やす)

**/bigobj**のセクションでは、オブジェクト ファイルを格納できる数を増やします。

## <a name="syntax"></a>構文

> **/bigobj**

## <a name="remarks"></a>Remarks

既定では、オブジェクト ファイルが最大 65,279 を保持できます (ほぼ 2 ^16) セクションではアドレス指定できます。 この制限は、プラットフォームが指定されているターゲットに関係なく適用されます。 **/bigobj** 4,294,967,296 するアドレスの量が増加 (2 ^32)。

ほとんどのモジュールには、複数の 65,279 セクションが含まれる .obj ファイルが生成されません。 ただし、コンピューターによって生成されたコードの場合、またはテンプレートのライブラリを多用するコードは、多くのセクションを保持できる .obj ファイルを必要があります。 **/bigobj**がユニバーサル Windows プラットフォーム (UWP) プロジェクトで既定で有効になって、コンピューターによって生成された XAML コードに含まれるヘッダーの数が多いためです。 UWP アプリ プロジェクトでこのオプションを無効にした場合、コードはコンパイラ エラー C1128 を生成可能性があります。

PE COFF オブジェクト ファイル形式については、次を参照してください。 [PE 形式](/windows/desktop/debug/pe-format)Windows ドキュメント。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 入力、 **/bigobj**コンパイラ オプションで、**追加オプション**ボックス。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
