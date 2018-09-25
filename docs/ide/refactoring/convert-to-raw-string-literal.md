---
title: 生文字列に変換 | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75037ea542a5bd2160d9a89138b12f82867002a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388447"
---
# <a name="convert-to-raw-string-literal"></a>生文字列に変換
**機能:** あらゆる文字列を C++ 生文字に変換できます。

**条件:** エスケープ文字として処理すべきではないエスケープ文字を含む文字列があるとき。

**理由:** エスケープ文字が 2 つあるとき、それが原因で文字列が読みにくい、誤解を招くことが多々あります。  生文字列を利用することで、文字列がはるかに読みやすくなります。

**方法:**

1. 変換するエスケープ文字の上にテキストまたはマウス カーソルを置きます。

   ![強調表示されたコード](images/stringliteral_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **キーボード**
     * **Ctrl + .** キーを押して、 **[クイック アクションとリファクタリング]** メニューをトリガーし、コンテキスト メニューから **[生文字列に変換]** を選択します。
   * **マウス**
     * コードを右クリックし、**[クイック アクションとリファクタリング]** メニューを選択し、コンテキスト メニューから **[生文字列に変換]** を選択します。
     * 左の余白に表示されている![電球](images/bulb.png)アイコンをクリックし、コンテキスト メニューから **[生文字列に変換]** を選択します。

1. 直後に文字列が生文字列に変換されます。

   ![生文字列の結果](images/stringliteral_result.png)