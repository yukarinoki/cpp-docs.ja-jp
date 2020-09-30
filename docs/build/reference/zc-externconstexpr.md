---
title: '/Zc: externConstexpr (外部 constexpr 変数の有効化)'
ms.date: 02/28/2018
f1_keywords:
- /Zc:externConstexpr
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
ms.openlocfilehash: db5a8892bcc11538c3ff883a0e9a3a27db0ee14f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502805"
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>`/Zc:externConstexpr` (Extern constexpr 変数の有効化)

**`/Zc:externConstexpr`** コンパイラオプションは、コンパイラに対して C++ 標準に準拠し、変数の外部リンケージを許可するように指示し **`constexpr`** ます。 既定では、キーワードを指定した場合でも、Visual Studio は常に **`constexpr`** 変数内部リンケージを提供し **`extern`** ます。

## <a name="syntax"></a>構文

> **`/Zc:externConstexpr`**[**`-`**]

## <a name="remarks"></a>注釈

コンパイラオプションにより、 **`/Zc:externConstexpr`** コンパイラはを使用して宣言された変数に外部リンケージを適用し `extern constexpr` ます。 以前のバージョンの Visual Studio では、既定では、またはが指定されている場合 **`/Zc:externConstexpr-`** 、 **`constexpr`** **`extern`** キーワードが使用されている場合でも、visual studio は変数への内部リンケージを適用します。 この **`/Zc:externConstexpr`** オプションは、Visual Studio 2017 更新プログラム15.6 以降で使用できます。 既定では、とはオフになっています。 [`/permissive-`](permissive-standards-conformance.md)オプションでは、は有効になりません **`/Zc:externConstexpr`** 。

宣言された変数がヘッダーファイルに含まれている場合は、 `extern constexpr` [`__declspec(selectany)`](../../cpp/selectany.md) 重複する宣言をリンクされたバイナリ内の1つのインスタンスにマージするために、その変数をマークする必要があります。 そうしないと、1つの定義ルールの違反について、リンカーエラー (たとえば、LNK2005) が表示されることがあります。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **`/Zc:externConstexpr`** **`/Zc:externConstexpr-`** [**追加オプション:** ] ペインにまたはを追加します。

## <a name="see-also"></a>関連項目

[`/Zc` 互換性](zc-conformance.md)<br/>
[`auto` キーワード](../../cpp/auto-cpp.md)
