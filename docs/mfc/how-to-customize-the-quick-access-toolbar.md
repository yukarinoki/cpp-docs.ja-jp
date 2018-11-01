---
title: '方法: クイック アクセス ツール バーをカスタマイズする'
ms.date: 11/04/2016
helpviewer_keywords:
- quick access toolbar [MFC], customization
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
ms.openlocfilehash: d9bdc523218c7fad217d066eabd518aaff011df3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558484"
---
# <a name="how-to-customize-the-quick-access-toolbar"></a>方法: クイック アクセス ツール バーをカスタマイズする

クイック アクセス ツールバー (QAT) は、アプリケーション ボタンの横にある、またはカテゴリ タブの下に表示されるコマンドのセットが含まれるカスタマイズ可能なツールバーです。 次の図は、一般的なクイック アクセス ツールバーを示します。

![MFC リボンのクイック アクセス ツールバー](../mfc/media/quick_access_toolbar.png "quick_access_toolbar")

クイック アクセス ツールバーをカスタマイズするでを開く、**プロパティ**ウィンドウは、そのコマンドを変更し、リボン コントロールをプレビューします。

### <a name="to-open-the-quick-access-toolbar-in-the-properties-window"></a>[プロパティ] ウィンドウで、クイック アクセス ツールバーを開く

1. Visual Studio での**ビュー**  メニューのをクリックして**リソース ビュー**します。

1. **リソース ビュー**、デザイン画面上に表示するリボン リソースをダブルクリックします。

1. デザイン画面で、クイック アクセス ツールバーのメニューを右クリックし をクリックし、**プロパティ**します。

## <a name="quick-access-toolbar-properties"></a>クイック アクセス ツールバーのプロパティ

次の表では、クイック アクセス ツールバーのプロパティを定義します。

|プロパティ|定義|
|--------------|----------------|
|QAT Position|アプリケーションの起動時には、クイック アクセス ツールバーの位置を指定します。 位置には、いずれかを指定できる**上**または**下**リボン コントロール。|
|QAT 項目|クイック アクセス ツールバーを使用できるコマンドを指定します。|

#### <a name="to-add-or-remove-commands-on-the-quick-access-toolbar"></a>追加またはクイック アクセス ツールバーにコマンドを削除するには

1. **プロパティ**ウィンドウで、をクリックして**QAT Items**、省略記号ボタンをクリックし、 **([...])**.

1. **QAT 項目エディター**  ダイアログ ボックスで、使用、**追加**と**削除**クイック アクセス ツールバーのコマンドのリストを変更するボタン。

1. クイック アクセス ツールバーとクイック アクセス ツールバーのメニューの両方に表示するコマンドを実行する場合に、コマンドの横にあるボックスをオンにします。 コマンドをメニューにのみ表示する場合、ボックスをオフにします。

## <a name="previewing-the-ribbon"></a>リボンのプレビュー

クイック アクセス ツールバーのコマンドは、デザイン サーフェイスは表示されません。 それらを表示するには、リボンのプレビューか、アプリケーションを実行する必要があります。

#### <a name="to-preview-the-ribbon-control"></a>リボン コントロールをプレビューするには

- **Ribbon エディター ツールバー**、 をクリックして**ribbon のテスト**します。

## <a name="see-also"></a>関連項目

[リボン デザイナー (MFC)](../mfc/ribbon-designer-mfc.md)

