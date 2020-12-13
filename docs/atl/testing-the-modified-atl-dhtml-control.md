---
description: 詳細については、「変更された ATL DHTML コントロールのテスト」を参照してください。
title: 変更された ATL DHTML コントロールのテスト
ms.date: 11/06/2018
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
ms.openlocfilehash: a797eab308ad7fb8c5c7b72566ec3d57a169370b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138334"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>変更された ATL DHTML コントロールのテスト

新しいコントロールを試してみて、現在の動作を確認してください。

## <a name="to-build-and-test-the-modified-control"></a>変更されたコントロールをビルドしてテストするには

1. プロジェクトをリビルドし、 **テストコンテナー** で開きます。 **テストコンテナー** にアクセスする方法の詳細については [、「テストコンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md)」を参照してください。

   コントロールのサイズを変更して、追加したすべてのボタンを表示します。

1. HTML を変更して、挿入した2つのボタンを確認します。 各ボタンには、「 [ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md): **Refresh** と **HelloHTML**」で特定したラベルが表示されます。

1. 2つの新しいボタンをテストして、それらがどのように動作するかを確認します。

次に、UI の一部ではないメソッドをテストします。

1. 境界線がアクティブになるように、コントロールを強調表示します。

1. **コントロール** メニューで、[**メソッドの呼び出し**] を選択します。

   リストに示されているメソッド **名** のメソッドは、コンテナーが呼び出すことができるメソッド `MethodInvoked` と `GoToURL` です。 その他のすべてのメソッドは、UI によって制御されます。

1. 呼び出すメソッドを選択し、[ **呼び出し** ] を選択して、メソッドのメッセージボックスを表示するか、に移動し `www.microsoft.com` ます。

1. [ **メソッドの呼び出し** ] ダイアログボックスで、[ **閉じる**] を選択します。

ATL DHTML コントロールを構成するさまざまな要素およびファイルの詳細については、「 [Dhtml コントロールプロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)」を参照してください。

## <a name="see-also"></a>関連項目

[DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)
