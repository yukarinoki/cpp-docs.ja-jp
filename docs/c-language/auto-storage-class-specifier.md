---
title: auto ストレージ クラス指定子 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca42eb26cc6bb08cd8a05e31b23e004b1cbeb8b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057432"
---
# <a name="auto-storage-class-specifier"></a>auto ストレージ クラス指定子

**auto** ストレージ クラス指定子は、自動変数 (ローカルな有効期間を持つ変数) を宣言します。 **auto** 変数は、宣言されたブロック内でのみ表示されます。 **auto** 変数の宣言には、「[初期化](../c-language/initialization.md)」に説明されているように、初期化子を含めることができます。 **auto** ストレージ クラスと一緒に指定された変数は自動的に初期化されないため、宣言するときに明示的に初期化するか、ブロック内のステートメントの初期値を代入する必要があります。 初期化されていない **auto** 変数の値は未定義です (**auto** または **register** ストレージ クラスのローカル変数は、初期化子が与えられた場合にスコープに入るたびに初期化されます)。

内部 **static** 変数 (ローカルまたはブロック スコープを持つ静的変数) は外部項目または **static** 項目のアドレスで初期化できますが、**auto** 項目のアドレスが定数ではないため、別の **auto** 項目のアドレスではできません。

## <a name="see-also"></a>参照

[auto キーワード](../cpp/auto-keyword.md)