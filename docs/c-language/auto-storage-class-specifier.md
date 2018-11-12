---
title: auto ストレージ クラス指定子
ms.date: 11/04/2016
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
ms.openlocfilehash: 926322fa55a14cc736dc41fbebd5c276ad61f020
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619909"
---
# <a name="auto-storage-class-specifier"></a>auto ストレージ クラス指定子

**auto** ストレージ クラス指定子は、自動変数 (ローカルな有効期間を持つ変数) を宣言します。 **auto** 変数は、宣言されたブロック内でのみ表示されます。 **auto** 変数の宣言には、「[初期化](../c-language/initialization.md)」に説明されているように、初期化子を含めることができます。 **auto** ストレージ クラスと一緒に指定された変数は自動的に初期化されないため、宣言するときに明示的に初期化するか、ブロック内のステートメントの初期値を代入する必要があります。 初期化されていない **auto** 変数の値は未定義です (**auto** または **register** ストレージ クラスのローカル変数は、初期化子が与えられた場合にスコープに入るたびに初期化されます)。

内部 **static** 変数 (ローカルまたはブロック スコープを持つ静的変数) は外部項目または **static** 項目のアドレスで初期化できますが、**auto** 項目のアドレスが定数ではないため、別の **auto** 項目のアドレスではできません。

## <a name="see-also"></a>参照

[auto キーワード](../cpp/auto-keyword.md)