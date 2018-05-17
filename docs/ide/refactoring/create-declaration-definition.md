---
title: 宣言を作成/定義 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60d583ec47a3f9c5b61599a5945e3cfa0d375b1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="create-declaration--definition"></a>宣言/定義の作成
**新機能:** 宣言または関数の定義をすぐに生成することができます。

**いつ：** Delcaration、またはその逆を行う必要がある関数があります。  

**理由:** 宣言/定義の手動で作成しますが、これが作成されますが、自動的に必要な場合は、ヘッダー/コード ファイルを作成します。

**方法:**

1. 宣言または定義を作成する関数にテキストまたはマウス カーソルを置きます。

   ![強調表示されたコード](images/createdefinition_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **キーボード**
     * **Ctrl + .** キーを押して、 トリガーに、**クイック アクションとリファクタリング**メニュー**作成宣言/定義**コンテキスト メニューからです。
   * **マウス**
     * 右クリックし、選択、**クイック アクションとリファクタリング**メニュー**作成宣言/定義**コンテキスト メニューからです。

1. 関数の宣言と定義は、ポップアップ プレビュー ウィンドウに表示ソースまたはヘッダー ファイルに作成されます。  ソースまたはヘッダー ファイルが存在しない場合がも作成され、プロジェクトに配置します。

   ![宣言を作成/定義の結果](images/createdefinition_result.png)
