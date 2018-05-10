---
title: /Zc:externConstexpr (外部 constexpr 変数は有効にする) |Microsoft ドキュメント
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:externConstexpr
dev_langs:
- C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0cbce8366fdd7be62c8d71f838b298d77849dcdf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc:externConstexpr (外部 constexpr 変数は有効にする)

**/Zc:externConstexpr**コンパイラ オプションは C++ 標準に準拠しているし、の外部リンケージを許可するようにコンパイラに指示`constexpr`変数。 Visual Studio では、既定値は常に、`constexpr`変数内部リンケージを指定する場合でも、`extern`キーワード。

## <a name="syntax"></a>構文

> **/Zc:externConstexpr**[**-**]

## <a name="remarks"></a>コメント

**/Zc:externConstexpr**コンパイラ オプションは、コンパイラを使用して宣言された変数に外部リンケージを適用する`extern constexpr`です。 以前のバージョンの Visual Studio で、既定で場合 **/Zc:externConstexpr-** を指定すると、Visual Studio に内部リンケージを適用する`constexpr`変数場合であっても、`extern`キーワードを使用します。 **/Zc:externConstexpr**オプションは、Visual Studio 2017 更新 15.6 以降を使用します。 既定では無効になっているとします。 [寛容/-](permissive-standards-conformance.md)オプションが有効にしません **/Zc:externConstexpr**です。

ヘッダー ファイルには、宣言された変数が含まれている場合`extern constexpr`、マークする必要があります[__declspec(selectany)](../../cpp/selectany.md)リンクされているバイナリに 1 つのインスタンスに重複する宣言をマージするためにします。 それ以外の場合、リンカー エラー単一定義規則の違反をたとえば、LNK2005 を参照してください可能性があります。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 追加 **/Zc:externConstexpr**または **/Zc:externConstexpr-** を**追加オプション:** ウィンドウです。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)  
[auto キーワード](../../cpp/auto-keyword.md)