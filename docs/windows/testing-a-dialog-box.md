---
title: ダイアログ ボックスのテスト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes, testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 94d08cc865b6388010dc07ef965f60edbf6796ac
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42587521"
---
# <a name="testing-a-dialog-box"></a>ダイアログ ボックスのテスト

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

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)  
[ダイアログ エディター](../windows/dialog-editor.md)  
[[ダイアログ エディター] ツール バーの表示と非表示](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)