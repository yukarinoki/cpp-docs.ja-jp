---
title: 関数を抽出する | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fc4d48c972bca9352f326085574e4cf4df83aea
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33333158"
---
# <a name="extract-function"></a>関数を抽出する
**機能:** コードのフラグメントを独自の関数に変換できます。

**条件:** 関数に、別の関数から呼び出される必要がある既存のコードのフラグメントがあるとき。  

**理由:** コードのコピー/貼り付けはできるが、重複につながるおそれがあるため。  他の関数から自由に呼び出すことができる独自の関数に、そのフラグメントをリファクタリングすることをお勧めします。

**方法:**

1. 抽出するコードを強調表示します。

   ![強調表示されたコード](images/extractfunction_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **キーボード**
     * **Ctrl + R** キーを押し、次に **Ctrl + M** キーを押します。  選ばれているプロファイルによってキーボード ショートカットが異なる場合があることに注意してください。
     * **Ctrl + .** キーを押して、 **[クイック アクションとリファクタリング]** メニューをトリガーし、コンテキスト メニューから **[Extract 関数 (試験段階)]** を選びます。
   * **マウス**
     * **[編集] > [リファクター] > [Extract 関数 (試験段階)]** の順に選びます。
     * コードを右クリックして **[クイック アクションとリファクタリング]** メニューを選び、コンテキスト メニューから **[Extract 関数 (試験段階)]** を選びます。
     * 左の余白に表示されている![電球](images/bulb.png)アイコンをクリックし、コンテキスト メニューから **[Extract 関数 (試験段階)]** を選びます。

1. **[関数/メソッドの抽出 (試験的)]** ウィンドウで、新しい関数名を入力し、コードを配置する場所を選んで、**[OK]** ボタンをクリックします。  

   ![関数の抽出](images/extractfunction_dialog.png)

1. 指定した場所に新しい関数が作成され、関数のプロトタイプが対応するヘッダー ファイルで宣言されて、元のコードはその関数の呼び出しに変更されます。

   ![関数の抽出の結果](images/extractfunction_result.png)