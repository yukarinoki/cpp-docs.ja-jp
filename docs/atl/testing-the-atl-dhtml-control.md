---
title: ATL DHTML コントロールのテスト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls
- DHTML controls, testing
ms.assetid: 0e4b4358-80ce-4505-8b06-ef4f30b1d1f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be4bb44455fb97a61cb4af608667bd5c05f2756a
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766293"
---
# <a name="testing-the-atl-dhtml-control"></a>ATL DHTML コントロールのテスト

プロジェクトを作成した後は、ビルドし、サンプル コントロールをテストします。 これを実行する前に、クラス ビューとソリューション エクスプ ローラーを使用して、プロジェクトを調べます。 プロジェクトの要素のより詳細に説明が記載されて[DHTML コントロール プロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)します。

#### <a name="to-build-and-test-the-atl-dhtml-control"></a>ビルドと ATL DHTML コントロールのテスト

1. プロジェクトをビルドします。 **ビルド** メニューのをクリックして**ソリューションのビルド**します。

2. ビルドが完了したら、テスト コンテナーを開きます。 参照してください[テスト プロパティとテスト コンテナーでイベント](../mfc/testing-properties-and-events-with-test-container.md)テスト コンテナーにアクセスする方法についてはします。

3. テスト コンテナーから、**編集** メニューのをクリックして**新しいコントロールを挿入**します。

4. **コントロールの挿入** ダイアログ ボックスで、リスト ボックスから、コントロールを選択します。 ただし、その名前は、ATL コントロール ウィザードで指定した短い名前に基づきます。 **[OK]** をクリックします。

5. コントロールを確認します。 スクロール バーがあることに注意してください。 スクロール バーをアクティブ化するのにコントロールのサイズを変更するのにには、コントロールのハンドルを使用します。

6. コントロールのボタンをテストします。 背景色は、ボタンの色に変更します。

7. テスト コンテナーを閉じます。

次に、 [DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md)します。

## <a name="see-also"></a>関連項目

[DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)

