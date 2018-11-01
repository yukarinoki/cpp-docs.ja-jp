---
title: ダイアログ ボックス (C++) のテスト
ms.date: 11/04/2016
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
ms.openlocfilehash: 101a2b556b2593953bfa6482f96d5b1aadc38d1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625066"
---
# <a name="testing-a-dialog-box-c"></a>ダイアログ ボックス (C++) のテスト

ダイアログ ボックスを設計する際には、プログラムをコンパイルせずに実行時の動作をシミュレートし、テストできます。 このモードでは、次を行うことができます。

- テキストの入力、コンボ ボックスの一覧での選択、オプションのオンとオフの切り替え、コマンドの選択。

- タブ オーダーのテスト。

- オプション ボタンやチェック ボックスなど、コントロールのグループ化のテスト。

- ダイアログ ボックスにあるコントロールのキーボード ショートカットのテスト。

   > [!NOTE]
   > ウィザードを使用したダイアログ ボックスのコードへの接続は、シミュレーションに含まれません。

通常、テストするダイアログ ボックスはメイン プログラム ウィンドウの相対位置に表示されます。 ダイアログ ボックスの設定した場合**Absolute Align**プロパティを**True**画面の左上隅に対して相対的な位置にあるダイアログ ボックスが表示されます。

### <a name="to-test-a-dialog-box"></a>ダイアログ ボックスをテストするには

1. ときに、**ダイアログ**エディターがアクティブなウィンドウ、メニュー バーで、選択**形式** > **テスト ダイアログ**します。

2. シミュレーションを終了するには、キーを押します**Esc**、かのみを選んで、**閉じる**テストしているダイアログ ボックスでボタンをクリックします。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[ダイアログ エディター](../windows/dialog-editor.md)<br/>
[[ダイアログ エディター] ツール バーの表示と非表示](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)