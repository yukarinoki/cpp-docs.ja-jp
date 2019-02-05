---
title: ダイアログ ボックス (C++) の設計
ms.date: 11/04/2016
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
- dialog boxes [C++], size
- dialog boxes [C++], positioning
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
ms.openlocfilehash: 4a879f6bb1cdcd4b4897e510fb21d04500dfd3f2
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742688"
---
# <a name="designing-a-dialog-box-c"></a>ダイアログ ボックス (C++) の設計

場所と C++ のダイアログ ボックスと場所のサイズと、内のコントロールのサイズは、ダイアログ単位で測定されます。 個々 のコントロールと、ダイアログ ボックスの値は、Visual Studio のステータス バーの選択した場合の右下に表示されます。

ダイアログ ボックスを設計するときにもシミュレートし、プログラムをコンパイルせずに、実行時の動作をテストします。 このモードでは、次を行うことができます。

- テキストの入力、コンボ ボックスの一覧での選択、オプションのオンとオフの切り替え、コマンドの選択。

- タブ オーダーのテスト。

- オプション ボタンやチェック ボックスなど、コントロールのグループ化のテスト。

- ダイアログ ボックスにあるコントロールのキーボード ショートカットのテスト。

   > [!NOTE]
   > ウィザードを使用したダイアログ ボックスのコードへの接続は、シミュレーションに含まれません。

通常、テストするダイアログ ボックスはメイン プログラム ウィンドウの相対位置に表示されます。 ダイアログ ボックスの設定した場合**Absolute Align**プロパティを**True**画面の左上隅に対して相対的な位置にあるダイアログ ボックスが表示されます。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)します。

## <a name="to-specify-the-location-and-size-of-a-dialog-box"></a>ダイアログ ボックスのサイズと場所を指定するには

設定できる 3 つのプロパティがある、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window) ダイアログ ボックスを画面に表示を指定します。 **Center** 、値を設定する場合、プロパティはブール値。 **True**、画面の中央で、ダイアログ ボックスが表示されます。 設定した場合**False**、設定することができます、 **XPos**と**YPos**プロパティ ダイアログ ボックスが表示され、画面上の場所を明示的に定義します。 位置プロパティとして定義されている表示領域の左上隅からのオフセット値を`{X=0, Y=0}`します。 位置もに基づいて、 **Absolute Align**プロパティ: 場合**True**、座標は画面場合**False**座標は、ダイアログ ボックス所有者のウィンドウです。

## <a name="to-test-a-dialog-box"></a>ダイアログ ボックスをテストするには

1. ときに、**ダイアログ**エディターがアクティブなウィンドウ、メニュー バーで、選択**形式** > **テスト ダイアログ**します。

1. シミュレーションを終了するには、キーを押します**Esc**、かのみを選んで、**閉じる** ダイアログ ボックスでテストしているボタンをクリックします。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[ダイアログ エディター](../windows/dialog-editor.md)<br/>
[[ダイアログ エディター] ツール バーの表示と非表示](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)