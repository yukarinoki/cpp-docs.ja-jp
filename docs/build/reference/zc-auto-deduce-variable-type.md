---
title: /Zc:auto (変数の型の推測)
ms.date: 02/28/2018
f1_keywords:
- /Zc:auto
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
ms.openlocfilehash: 03bbe3d9da0530d4fe3c540d46d1a597fbe9dd2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549306"
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (変数の型の推測)

**/Zc:auto [-]** コンパイラ オプションを使用する方法をコンパイラに指示、 [auto キーワード](../../cpp/auto-keyword.md)変数を宣言します。 既定のオプションを指定する場合 **/Zc:auto**コンパイラはその初期化式から、宣言された変数の型を推論します。 指定した場合 **/Zc:auto-** コンパイラは自動ストレージ クラスに変数を割り当てます。

## <a name="syntax"></a>構文

> **/Zc:auto**[**-**]

## <a name="remarks"></a>Remarks

C++ 基準は、`auto` キーワードの元の意味と改定された意味を定義します。 Visual C 2010 では、前に、キーワードは、自動ストレージ クラスの変数を宣言します。つまり、変数を持つローカルな有効期間。 Visual C 2010 以降では、キーワードは宣言の初期化式から変数の型を推論します。 使用して、 **/Zc:auto [-]** の元のまたは改訂後の意味を使用するようにコンパイラに指示するコンパイラ オプション、`auto`キーワード。 **/Zc:auto**オプションが既定でオンです。 [/Permissive -](permissive-standards-conformance.md)オプションは既定の設定を変更してされません **/Zc:auto**します。

場合、コンパイラは、適切な診断メッセージを発行の使用、`auto`キーワードが現在を満たしていない **/Zc:auto**コンパイラ オプション。 詳細については、次を参照してください。 [auto キーワード](../../cpp/auto-keyword.md)します。 Visual C の準拠の問題の詳細については、次を参照してください。[非標準動作](../../cpp/nonstandard-behavior.md)します。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 追加 **/Zc:auto**または **/Zc:auto-** を**追加オプション:** ウィンドウ。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
[auto キーワード](../../cpp/auto-keyword.md)
