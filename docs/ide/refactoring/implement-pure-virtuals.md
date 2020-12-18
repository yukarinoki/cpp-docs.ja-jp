---
description: '詳細情報: 純粋仮想の実装'
title: 純粋仮想の実装
ms.date: 11/16/2016
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
ms.openlocfilehash: b35ebba556ed9bae6ded649caca000b7d3554480
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318755"
---
# <a name="implement-pure-virtuals"></a>純粋仮想の実装

**機能:** クラスですべての純粋仮想を実装するために必要なコードをすぐに生成できます。

**条件:** 純粋仮想関数のクラスからの継承が望まれるとき。

**理由:** すべての純粋仮想関数は 1 つずつ手動で実装できますが、この機能ではすべてのメソッド シグネチャが自動的に生成されます。

**方法:**

1. 基底クラスの純粋仮想関数を実装するクラスにテキストまたはマウス カーソルを置きます。

   ![強調表示されたコード](images/virtuals_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **[キーボード]**
     * **Ctrl + .** キーを押して、 **[クイック アクションとリファクタリング]** メニューをトリガーし、コンテキスト メニューから **[Implement all Pure Virtuals for class '*ClassName*’]\(クラス 'ClassName' のすべての純粋仮想を実装\)** を選択します。*ClassName* は、選択されたクラスの名前になります。
   * **マウス**
     * 右クリックして **[クイック アクションとリファクタリング]** メニューを選択し、コンテキスト メニューから **[Implement all Pure Virtuals for class '*ClassName*']\(クラス 'ClassName' のすべての純粋仮想を実装\)** を選択します。*ClassName* は、選択されたクラスの名前になります。

1. 純粋仮想メソッドのシグネチャが自動的に作成され、実装する準備が整います。

   ![純粋仮想の実装の結果](images/virtuals_result.png)
