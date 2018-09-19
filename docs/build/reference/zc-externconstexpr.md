---
title: '/Zc: externconstexpr (外部 constexpr 変数の有効化) |マイクロソフトのドキュメント'
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
ms.openlocfilehash: 34aea466a3e673c3eebb3b415d544d9299fed615
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713142"
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc: externconstexpr (外部 constexpr 変数の有効化)

**/Zc: externconstexpr**コンパイラ オプション、C++ 標準に準拠しているし、外部リンケージを許可するようにコンパイラに指示`constexpr`変数。 既定では、Visual Studio が常にでは、`constexpr`変数の内部リンケージを指定する場合でも、`extern`キーワード。

## <a name="syntax"></a>構文

> **/Zc:externConstexpr**[**-**]

## <a name="remarks"></a>Remarks

**/Zc: externconstexpr**コンパイラ オプションは、コンパイラを使用して宣言された変数に外部リンケージを適用する`extern constexpr`します。 以前のバージョンの Visual Studio で、既定で場合 **/Zc:externConstexpr-** を指定すると、Visual Studio に内部リンケージを適用する`constexpr`変数場合でも、`extern`キーワードを使用します。 **/Zc: externconstexpr**オプションは、Visual Studio 2017 Update 15.6 以降を使用します。 既定で無効であるとします。 [/Permissive -](permissive-standards-conformance.md)オプションが有効にしない **/zc: externconstexpr**します。

ヘッダー ファイルには、宣言された変数が含まれている場合`extern constexpr`、マークする必要があります[__declspec(selectany)](../../cpp/selectany.md) 1 つのインスタンスでは、リンクされたバイナリに重複する宣言をマージするためにします。 それ以外の場合、リンカー エラーの単一定義規則の違反 LNK2005 などを参照してください可能性があります。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 追加 **/zc: externconstexpr**または **/Zc:externConstexpr-** を**追加オプション:** ウィンドウ。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)
[auto キーワード](../../cpp/auto-keyword.md)