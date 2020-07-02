---
title: /Cetcompat (中央のシャドウスタックと互換性あり)
ms.date: 06/30/2020
f1_keywords:
- /CETCOMPAT
helpviewer_keywords:
- /CETCOMPAT linker option
- /CETCOMPAT
ms.openlocfilehash: 35078ac9e6177e34562db14b30f4ef8f987d98bc
ms.sourcegitcommit: 83ea5df40917885e261089b103d5de3660314104
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85813564"
---
# <a name="cetcompat-cet-shadow-stack-compatible"></a>/Cetcompat (中央のシャドウスタックと互換性あり)

実行可能イメージを、制御フロー強制テクノロジ (中央管理) シャドウスタックと互換性のあるものとしてマークするかどうかを指定します。

## <a name="syntax"></a>構文

> **`/CETCOMPAT`**\
> **`/CETCOMPAT:NO`**

## <a name="arguments"></a>引数

**`NO`**<br/>
実行可能ファイルが、中央のシャドウスタックと互換性があるとマークされないように指定します。

## <a name="remarks"></a>Remarks

制御フロー強制テクノロジ (中央値) シャドウスタックは、リターン指向プログラミング (ROP) ベースのマルウェア攻撃に対して防御する機能を提供するコンピュータープロセッサ機能です。 詳細については、「 [Intel Control Flow 強制テクノロジプレビュー](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf)」を参照してください。

**`/CETCOMPAT`** リンカーオプションは、バイナリをバイナリシャドウスタック互換としてマークするようにリンカーに指示します。 **`/CETCOMPAT:NO`** バイナリを、中央のシャドウスタックと互換性がないとしてマークします。 両方のオプションがコマンドラインで指定されている場合は、最後に指定されたものが使用されます。 このスイッチは、現在、x86 および x64 アーキテクチャにのみ適用されます。

この **`/CETCOMPAT`** オプションは、Visual Studio 2019 以降で使用できます。

### <a name="to-set-the-cetcompat-linker-option-in-visual-studio"></a>`/CETCOMPAT`Visual Studio でリンカーオプションを設定するには

Visual Studio 2019 バージョン16.7 以降:

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../working-with-project-properties.md)」を参照してください。

1. [**構成プロパティ**]  >  **リンカー**の  >  **[詳細設定**] プロパティページを選択します。

1. [中央値の**シャドウスタック互換**] プロパティを選択します。

1. ドロップダウンコントロールで、 **`Yes (/CETCOMPAT)`** EH 継続メタデータを有効にするか、無効にするかを選択し **`No (/CETCOMPAT:NO)`** ます。

以前のバージョンの Visual Studio 2019 では、次のようになります。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../working-with-project-properties.md)」を参照してください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **コマンドライン**] プロパティページを選択します。

1. [**追加オプション]** の [編集コントロール] で、[追加] を選択し *`/CETCOMPAT`* て EH 継続メタデータを有効にするか、 *`/CETCOMPAT:NO`* 明示的に無効にします。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

このオプションには、プログラムに相当するものはありません。

## <a name="see-also"></a>関連項目

[リンカーのオプション](linker-options.md)
