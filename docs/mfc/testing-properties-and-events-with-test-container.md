---
description: 詳細については、「テストコンテナーでのプロパティとイベントのテスト」を参照してください。
title: テスト コンテナーでのプロパティとイベントのテスト
ms.date: 11/04/2016
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
ms.openlocfilehash: 61cccbda723fb1cfac0ca3fc696639849bde9dd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216224"
---
# <a name="testing-properties-and-events-with-test-container"></a>テスト コンテナーでのプロパティとイベントのテスト

Visual C++ に付属しているテストコンテナーアプリケーションは、ActiveX コントロールをテストおよびデバッグするための ActiveX コントロールコンテナーです。 テストコンテナーを使用すると、コントロールの開発者は、プロパティを変更し、メソッドを呼び出して、そのイベントを発生させることで、コントロールの機能をテストできます。 テストコンテナーは、データバインディング通知のログを表示できます。また、ActiveX コントロールの永続化機能をテストするための機能も備えています。プロパティをストリームに保存したり、サブストレージに再読み込みしたり、格納されているストリームデータを調べたりすることができます。 このセクションでは、テストコンテナーの基本的な機能を使用する方法について説明します。 詳細については、テストコンテナーの実行中に [ **ヘルプ** ] メニューを選択してください。

### <a name="to-access-the-activex-control-test-container"></a>ActiveX コントロールテストコンテナーにアクセスするには

1. TSTCON サンプルをビルドします。 [ActiveX コントロールテストコンテナー](../overview/visual-cpp-samples.md)。

### <a name="to-test-your-activex-control"></a>ActiveX コントロールをテストするには

1. テストコンテナーの [ **編集** ] メニューの [ **新しいコントロールの挿入**] をクリックします。

1. [ **コントロールの挿入** ] ボックスで、目的のコントロールを選択し、[ **OK]** をクリックします。 コントロールがコントロールコンテナーに表示されます。

    > [!NOTE]
    >  [**コントロールの挿入**] ダイアログボックスにコントロールが表示されていない場合は、テストコンテナーの [**ファイル**] メニューから [**コントロールの登録**] コマンドを使用して、コントロールを登録していることを確認してください。

この時点で、コントロールのプロパティまたはイベントをテストできます。

#### <a name="to-test-properties"></a>プロパティをテストするには

1. [ **コントロール** ] メニューの [ **メソッドの呼び出し**] をクリックします。

1. [ **メソッド名** ] ボックスの一覧で、テストするプロパティの PropPut メソッドを選択します。

1. パラメーターの **値** または **パラメーターの型** を変更し、[ **値の設定** ] ボタンをクリックします。

1. [ **呼び出し** ] をクリックして、オブジェクトに新しい値を適用します。

   プロパティに新しい値が含まれるようになりました。

#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>イベントをテストし、イベント情報の出力先を指定します。

1. [ **オプション** ] メニューの [ **ログ記録**] をクリックします。

1. イベント情報の出力先を指定します。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[方法: ActiveX コントロールをデバッグする](/visualstudio/debugger/how-to-debug-an-activex-control)
