---
title: 定義の場所に移動 |Microsoft ドキュメント
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
ms.openlocfilehash: 44211105429e33c136999a7877ac6ee42af29f17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="move-definition-location"></a>定義の場所の移動
**新機能:** すぐに対応するヘッダー ファイルに関数定義を移動することができます。

**いつ：** ヘッダー ファイルに移動する関数があります。  

**理由:** 関数を手動で移動する可能性がありますが、この機能は、自動的に移動、必要な場合は、ヘッダー ファイルを作成します。

**方法:**

1. この関数は、移動するテキストまたはマウス カーソルを置きます。

   ![強調表示されたコード](images/movedefinition_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **キーボード**
     * **Ctrl + .** キーを押して、 トリガーを**クイック アクションとリファクタリング**メニュー**定義の場所を移動**コンテキスト メニューからです。
   * **マウス**
     * 右クリックし、選択、**クイック アクションとリファクタリング**メニュー**定義の場所を移動**コンテキスト メニュー。

1. 関数は、ポップアップ プレビュー ウィンドウに表示されますが、対応するヘッダー ファイルに移動されます。  ヘッダー ファイルが存在しない場合がも作成され、プロジェクトに配置します。

   ![宣言を作成/定義の結果](images/movedefinition_result.png)
