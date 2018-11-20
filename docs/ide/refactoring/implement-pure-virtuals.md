---
title: 純粋仮想の実装
ms.date: 11/16/2016
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
ms.openlocfilehash: 59e4519f57a1d9bd9ba1cee1ed6ae41bea785a9f
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51692668"
---
# <a name="implement-pure-virtuals"></a>純粋仮想の実装

**機能:** クラスですべての純粋仮想を実装するために必要なコードをすぐに生成できます。

**条件:** 純粋仮想関数のクラスからの継承が望まれるとき。

**理由:** すべての純粋仮想関数は 1 つずつ手動で実装できますが、この機能ではすべてのメソッド シグネチャが自動的に生成されます。

**方法:**

1. 基底クラスの純粋仮想関数を実装するクラスにテキストまたはマウス カーソルを置きます。

   ![強調表示されたコード](images/virtuals_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **キーボード**
     * **Ctrl + .** キーを押して、 **[クイック アクションとリファクタリング]** メニューをトリガーし、コンテキスト メニューから **[Implement all Pure Virtuals for class '*ClassName*’]\(クラス 'ClassName' のすべての純粋仮想を実装\)** を選択します。*ClassName* は、選択されたクラスの名前になります。
   * **マウス**
     * 右クリックして **[クイック アクションとリファクタリング]** メニューを選択し、コンテキスト メニューから **[Implement all Pure Virtuals for class '*ClassName*']\(クラス 'ClassName' のすべての純粋仮想を実装\)** を選択します。*ClassName* は、選択されたクラスの名前になります。

1. 純粋仮想メソッドのシグネチャが自動的に作成され、実装する準備が整います。

   ![純粋仮想の実装の結果](images/virtuals_result.png)
