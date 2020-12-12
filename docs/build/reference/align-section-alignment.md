---
description: 詳細情報:/ALIGN (セクションの配置)
title: /ALIGN (セクションの配置)
ms.date: 12/29/2017
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.openlocfilehash: d8a9af473252a2eff8957c5d2b4c54c7f7c862aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187261"
---
# <a name="align-section-alignment"></a>/ALIGN (セクションの配置)

## <a name="syntax"></a>構文

> **/Align**[**:**_number_]

### <a name="arguments"></a>引数

*number*<br/>
アラインメントの値 (バイト単位)。

## <a name="remarks"></a>解説

**/Align** オプションは、プログラムのリニアアドレス空間内の各セクションの配置を指定します。 *Number* 引数はバイト単位で、2の累乗でなければなりません。 既定値は 4K (4096) です。 配置によって無効なイメージが生成された場合、リンカーは警告を発行します。

デバイスドライバーなどのアプリケーションを作成する場合を除き、配置を変更する必要はありません。

Align パラメーターを使用して、特定のセクションのアラインメントを [/SECTION](section-specify-section-attributes.md) オプションに変更することができます。

指定するアラインメント値は、最大のセクションアラインメントより小さくすることはできません。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] の [  >  **リンカー**  >  **コマンドライン**] プロパティページをクリックします。

1. [ **追加オプション** ] ボックスにオプションを入力します。 **[OK]** または [**適用**] を選択して変更を適用します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
