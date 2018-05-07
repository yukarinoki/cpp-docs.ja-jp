---
title: プロパティとイベント テスト コンテナーでのテスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbf2b7c26b7fc44a526381f4fb3e4dee5c94ba8d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="testing-properties-and-events-with-test-container"></a>テスト コンテナーでのプロパティとイベントのテスト
Visual C に付属して、テスト コンテナー アプリケーションは、テストおよびデバッグの ActiveX コントロールの ActiveX コントロール コンテナーです。 テスト コンテナーには、コントロールの機能をテストするには、プロパティを変更して、メソッドを呼び出し、そのイベントを発生させるコントロール開発者ができるようにします。 テスト コンテナーがデータ バインディングの通知のログを表示し、ActiveX コントロールの永続化の機能をテストするための機能も提供します。 ストリームまたはほかのプロパティを保存、再読み込み、および格納されたストリームのデータを調べることができます。 このセクションでは、テスト コンテナーの基本的な機能を使用する方法について説明します。 詳細については、選択、**ヘルプ**テスト コンテナーの実行中のメニュー。  
  
### <a name="to-access-the-activex-control-test-container"></a>ActiveX コントロール テスト コンテナーへのアクセス  
  
1.  ビルド、 [TSTCON サンプル: ActiveX コントロール テスト コンテナー](../visual-cpp-samples.md)です。  
  
### <a name="to-test-your-activex-control"></a>ActiveX コントロールをテストするには  
  
1.  **編集**テスト コンテナーのメニューをクリックして**新しいコントロールを挿入**です。  
  
2.  **コントロールの挿入**ボックスで、目的のコントロールを選択し、をクリックして**OK**です。 コントロールは、コントロールのコンテナーに表示されます。  
  
    > [!NOTE]
    >  コントロールが表示されていない場合、**コントロールの挿入** ダイアログ ボックスで、登録されているかどうかを確認、**コントロールの登録**コマンドを**ファイル**のテスト メニューコンテナーです。  
  
 この時点で、コントロールのプロパティまたはイベントをテストすることができます。  
  
#### <a name="to-test-properties"></a>プロパティをテストするには  
  
1.  **コントロール** メニューのをクリックして**メソッドの呼び出し**です。  
  
2.  **メソッド名**ドロップダウン リストで、PropPut メソッドをテストするプロパティを選択します。  
  
3.  変更、**パラメーター値**または**パラメーターの型** をクリックし、**値の設定**ボタンをクリックします。  
  
4.  をクリックして**Invoke**オブジェクトに新しい値を適用します。  
  
     これで、プロパティには、新しい値が含まれています。  
  
#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>イベントをテストし、イベント情報の保存先を指定します。  
  
1.  **オプション** メニューのをクリックして**ログ**です。  
  
2.  イベント情報の出力先を指定します。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [方法 : ActiveX コントロールをデバッグする](/visualstudio/debugger/how-to-debug-an-activex-control)

