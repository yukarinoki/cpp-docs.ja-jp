---
title: イメージのテキストのフォントの変更 (アイコン用イメージ エディター)
ms.date: 11/04/2016
helpviewer_keywords:
- fonts, changing on an image
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
ms.openlocfilehash: 2bbd8096a2957099acc8c06d501f3ad407b9a974
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495525"
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>イメージのテキストのフォントの変更 (アイコン用イメージ エディター)

次の手順では、する方法の例を示します。

- Windows アプリケーションのアイコンにテキストを追加します。

- テキストのフォントを操作します。

### <a name="to-change-the-font-of-text-on-an-image"></a>イメージのテキストのフォントを変更するには

1. C++ Windows フォーム アプリケーションを作成します。 詳細については、次を参照してください。 [Windows アプリケーション プロジェクトを作成する](/previous-versions/visualstudio/visual-studio-2010/42wc9kk5)します。 `app.ico`ファイルは、既定では、プロジェクトに追加されます。

2. **ソリューション エクスプ ローラー**、app.ico ファイルをダブルクリックします。 [イメージ エディター](../windows/image-editor-for-icons.md)が開きます。

3. **イメージ**メニューの **ツール**選び**テキスト ツール**します。 [テキスト ツール ダイアログ ボックス](../windows/text-tool-dialog-box-image-editor-for-icons.md)が表示されます。

4. **テキスト ツール**ダイアログ ボックスに「`C++`空のテキスト領域にします。 このテキストの左上隅にあるサイズ変更可能なボックスに表示されます`app.ico`の**イメージ エディター**します。

5. **イメージ エディター**、サイズ変更可能なボックス、テキストの読みやすさを向上させるために、app.ico の中央にドラッグします。

6. **テキスト ツール**ダイアログ ボックスで、をクリックして、**フォント**ボタンをクリックします。 [テキスト ツール フォント ダイアログ ボックス](../windows/text-tool-font-dialog-box-image-editor-for-icons.md)が表示されます。

7. **テキスト ツール フォント**ダイアログ ボックスで、 **Times New Roman**記載されている利用可能なフォントの一覧から、**フォント**ボックスの一覧。

8. 選択**太字**でリストされている利用可能なフォント スタイルの一覧から、**フォント スタイル**ボックスの一覧。

9. 選択**10**ポイントで示されたサイズの使用可能な一覧から、**サイズ**ボックスの一覧。

10. をクリックして、 **OK**ボタンをクリックします。 **テキスト ツール フォント** ダイアログ ボックスが閉じ、新しいフォントの設定は、テキストに適用されます。

11. をクリックして、**閉じる**のボタンでは、**テキスト ツール** ダイアログ ボックス。 サイズ変更可能なテキストを囲むボックスから消え、**イメージ エディター**します。

## <a name="see-also"></a>関連項目

[グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[ツール バー](../windows/toolbar-image-editor-for-icons.md)