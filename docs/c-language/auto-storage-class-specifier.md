---
title: auto ストレージ クラス指定子
ms.date: 11/04/2016
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
ms.openlocfilehash: 7f70ee1944e07ebcbd32b8110eee27fa6631be63
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509315"
---
# <a name="auto-storage-class-specifier"></a>`auto` ストレージ クラス指定子

**`auto`** ストレージ クラス指定子を使用すると、自動変数 (ローカルな有効期間を持つ変数) を宣言できます。 **`auto`** 変数は、それが宣言されているブロック内でのみ参照できます。 **`auto`** 変数の宣言には、「[初期化](../c-language/initialization.md)」に説明されているように、初期化子を含めることができます。 **`auto`** ストレージ クラスと一緒に指定された変数は自動的に初期化されないため、宣言するときに明示的に初期化するか、ブロック内のステートメントの初期値を代入する必要があります。 初期化されていない **`auto`** 変数の値は未定義です。 ( **`auto`** または **`register`** ストレージ クラスのローカル変数は、初期化子が与えられた場合にスコープに入るたびに初期化されます)。

内部 **`static`** 変数 (ローカルまたはブロック スコープを持つ静的変数) は外部項目または **`static`** 項目のアドレスで初期化できますが、 **`auto`** 項目のアドレスが定数ではないため、別の **`auto`** 項目のアドレスではできません。

## <a name="see-also"></a>関連項目

[`auto` キーワード](../cpp/auto-cpp.md)
