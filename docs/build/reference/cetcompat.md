---
title: /Cetcompat (中央のシャドウスタックと互換性あり)
ms.date: 02/19/2019
f1_keywords:
- /CETCOMPAT
helpviewer_keywords:
- /CETCOMPAT linker option
- /CETCOMPAT
ms.openlocfilehash: 2c807d91d69b967fd62e01a077711dede5f55c44
ms.sourcegitcommit: 7e011c68ca7547469544fac87001a33a37e1792e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84421302"
---
# <a name="cetcompat-cet-shadow-stack-compatible"></a>/Cetcompat (中央のシャドウスタックと互換性あり)

実行可能イメージを、制御フロー強制テクノロジ (中央管理) シャドウスタックと互換性のあるものとしてマークするかどうかを指定します。

## <a name="syntax"></a>構文

> **/Cetcompat** \[**: いいえ**]

## <a name="arguments"></a>引数

**違います**<br/>
実行可能ファイルが、中央のシャドウスタックと互換性があるとマークされていないことを指定します。

## <a name="remarks"></a>解説

制御フロー強制テクノロジ (中央値) シャドウスタックは、リターン指向プログラミング (ROP) ベースのマルウェア攻撃から保護する機能を提供するコンピュータープロセッサ機能です。 詳細については、「 [Intel Control Flow 強制テクノロジプレビュー](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf)」を参照してください。

**/Cetcompat**リンカーオプションは、バイナリをバイナリシャドウスタック互換としてマークするようにリンカーに指示します。 **/Cetcompat:** は、バイナリを、中央のシャドウスタックと互換性がないとしてマークします。 両方のオプションがコマンドラインで指定されている場合は、最後に指定されたものが使用されます。 このスイッチは、現在、x86 および x64 アーキテクチャにのみ適用されます。

**/Cetcompat**オプションは、Visual Studio 2019 Preview 3 ツールセットから使用できます。

### <a name="to-set-the-cetcompat-linker-option-in-visual-studio"></a>Visual Studio で/cetcompat リンカーオプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../working-with-project-properties.md)」を参照してください。

1. [**構成プロパティ**]  >  **リンカー**の  >  **[詳細設定**] プロパティページを選択します。

1. [中央値の**シャドウスタック互換**] プロパティを選択します。

1. ドロップダウンコントロールで、 **[はい] (/cetcompat)** を選択して EH 継続メタデータを有効にします。無効にするには、[**いいえ] (/cetcompat: no)** を選択します。


### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

このオプションには、プログラムに相当するものはありません。

## <a name="see-also"></a>関連項目

[リンカーオプション](linker-options.md)
