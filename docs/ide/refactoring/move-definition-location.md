---
title: 定義の場所の移動 | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5058e0b3bab1fb5fb5e8d52b55e3fa7c37fd8a4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430060"
---
# <a name="move-definition-location"></a>定義の場所の移動
**機能:** それに対応するヘッダー ファイルに関数定義をすぐに移動できます。

**条件:** ヘッダー ファイルへの移動が望まれる関数があるとき。

**理由:** 関数は手動で移動できますが、この機能では関数が自動的に移動され、必要に応じてヘッダー ファイルが作成されます。

**方法:**

1. 移動する関数の上にテキストまたはマウス カーソルを置きます。

   ![強調表示されたコード](images/movedefinition_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **キーボード**
     * **Ctrl + .** キーを押して、 **[クイック アクションとリファクタリング]** メニューをトリガーし、コンテキスト メニューから **[定義の場所の移動]** を選択します。
   * **マウス**
     * 右クリックして **[クイック アクションとリファクタリング]** メニューを選択し、コンテキスト メニューから **[定義の場所の移動]** を選択します。

1. 関数が該当するヘッダー ファイルに移動します。ポップアップ プレビュー ウィンドウで確認できます。  ヘッダー ファイルが存在しない場合、それも作成され、プロジェクトに置かれます。

   ![宣言/定義の作成の結果](images/movedefinition_result.png)
