---
title: 変更した ATL DHTML コントロールのテスト |Microsoft ドキュメント
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
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b140788cd409aa5a11f93689e96fa40c1a167dfe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360346"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>変更した ATL DHTML コントロールのテスト
今すぐ動作を確認する、新しいコントロールを試します。  
  
#### <a name="to-build-and-test-the-modified-control"></a>作成および変更のコントロールをテストするには  
  
1.  プロジェクトをリビルドし、テスト コンテナーで開きます。 参照してください[プロパティのテストおよびテスト コンテナーでイベント](../mfc/testing-properties-and-events-with-test-container.md)テスト コンテナーにアクセスする方法についてはします。  
  
     追加したボタンをすべて表示するコントロールのサイズを変更します。  
  
2.  HTML を変更して挿入した 2 つのボタンを調べます。 各ボタンで特定したラベルを持つ[ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md):**更新**と**HelloHTML**です。  
  
3.  動作を確認する 2 つの新しいボタンをテストします。  
  
 UI の部分ではないメソッドをテストします。  
  
1.  境界線がアクティブになるように、コントロールを強調表示します。  
  
2.  **コントロール** メニューのをクリックして**メソッドの呼び出し**です。  
  
 ラベルの付いたリスト内のメソッド**メソッド名**メソッドが、コンテナーが呼び出すことができます:`MethodInvoked`と`GoToURL`です。 その他のすべてのメソッドは、UI によって制御されます。  
  
1.  呼び出すし、をクリックする方法を選択`Invoke`メソッドのメッセージ ボックスを表示するか、www.microsoft.com に移動します。  
  
2.  **メソッドの呼び出し**ダイアログ ボックスで、をクリックして**閉じる**です。  
  
 さまざまな要素と ATL DHTML コントロールを構成するファイルの詳細については、次を参照してください。 [DHTML コントロール プロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)です。  
  
## <a name="see-also"></a>関連項目  
 [DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)

