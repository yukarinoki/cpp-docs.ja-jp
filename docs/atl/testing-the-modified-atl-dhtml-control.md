---
title: 変更した ATL DHTML コントロールのテスト
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
ms.openlocfilehash: f0fec3e2430fd5956e3cc48cd64532efee30926d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501674"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>変更した ATL DHTML コントロールのテスト

今すぐ動作を確認する新しいコントロールを試します。

## <a name="to-build-and-test-the-modified-control"></a>ビルドし、変更されたコントロールをテストするには

1. プロジェクトをリビルドして開くために**テスト コンテナー**します。 参照してください[テスト プロパティとテスト コンテナーでイベント](../mfc/testing-properties-and-events-with-test-container.md)にアクセスする方法については**テスト コンテナー**します。

   すべての追加したボタンを表示するコントロールのサイズを変更します。

1. HTML を変更して挿入した 2 つのボタンを確認します。 各ボタンで特定したラベルである[ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md):**更新**と**HelloHTML**します。

1. そのしくみを確認する 2 つの新しいボタンをテストします。

UI の一部ではないメソッドをテストできます。

1. 境界線がアクティブになるように、コントロールを強調表示します。

1. **コントロール** メニューのをクリックして**メソッドの呼び出し**します。

ラベル リスト内のメソッド**メソッド名**メソッドが、コンテナーを呼び出すことができます:`MethodInvoked`と`GoToURL`します。 その他のすべてのメソッドは、UI によって制御されます。

1. 呼び出すし、をクリックする方法を選択`Invoke`メソッドのメッセージ ボックスを表示するか、www.microsoft.com に移動します。

1. **メソッドの呼び出し**ダイアログ ボックスで、をクリックして**閉じる**します。

さまざまな要素と ATL DHTML コントロールを構成するファイルの詳細については、次を参照してください。 [DHTML コントロール プロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)します。

## <a name="see-also"></a>関連項目

[DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)
