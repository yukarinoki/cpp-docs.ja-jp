---
title: auto ストレージ クラス指定子
ms.date: 11/04/2016
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
ms.openlocfilehash: e39b37e2dc91dce31b6871d721875c75b8ebd629
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223760"
---
# <a name="auto-storage-class-specifier"></a>`auto` ストレージ クラス指定子

**`auto`** ストレージ クラス指定子を使用すると、自動変数 (ローカルな有効期間を持つ変数) を宣言できます。 **`auto`** 変数は、それが宣言されているブロック内でのみ参照できます。 **`auto`** 変数の宣言には、「[初期化](../c-language/initialization.md)」に説明されているように、初期化子を含めることができます。 **`auto`** ストレージ クラスと一緒に指定された変数は自動的に初期化されないため、宣言するときに明示的に初期化するか、ブロック内のステートメントの初期値を代入する必要があります。 初期化されていない **`auto`** 変数の値は未定義です。 ( **`auto`** または **`register`** ストレージ クラスのローカル変数は、初期化子が与えられた場合にスコープに入るたびに初期化されます)。

内部 **`static`** 変数 (ローカルまたはブロック スコープを持つ静的変数) は外部項目または **`static`** 項目のアドレスで初期化できますが、 **`auto`** 項目のアドレスが定数ではないため、別の **`auto`** 項目のアドレスではできません。

## <a name="see-also"></a>関連項目

[`auto` キーワード](../cpp/auto-keyword.md)
