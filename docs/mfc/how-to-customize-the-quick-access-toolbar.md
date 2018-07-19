---
title: '方法: クイック アクセス ツールバーをカスタマイズする |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- quick access toolbar [MFC], customization
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0faa3a0fb66c4379824a6be190175b10e0415474
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349647"
---
# <a name="how-to-customize-the-quick-access-toolbar"></a>方法: クイック アクセス ツール バーをカスタマイズする
クイック アクセス ツールバー (QAT) は、アプリケーション ボタンの横にある、またはカテゴリ タブの下に表示されるコマンドのセットを含むカスタマイズ可能なツールバーです。 次の図は、一般的なクイック アクセス ツールバーを示しています。  
  
 ![MFC リボンのクイック アクセス ツールバー](../mfc/media/quick_access_toolbar.png "quick_access_toolbar")  
  
 クイック アクセス ツールバーをカスタマイズするで開く、**プロパティ**ウィンドウで、そのコマンドを変更し、リボン コントロールをプレビューします。  
  
### <a name="to-open-the-quick-access-toolbar-in-the-properties-window"></a>開くには、[プロパティ] ウィンドウで、クイック アクセス ツールバー  
  
1.  Visual Studio での**ビュー**  メニューのをクリックして**リソース ビュー**です。  
  
2.  **リソース ビュー**、デザイン画面に表示するリボン リソースをダブルクリックします。  
  
3.  デザイン画面で、クイック アクセス ツールバーのメニューを右クリックし、をクリックして**プロパティ**です。  
  
## <a name="quick-access-toolbar-properties"></a>クイック アクセス ツールバーのプロパティ  
 次の表では、クイック アクセス ツールバーのプロパティを定義します。  
  
|プロパティ|定義|  
|--------------|----------------|  
|QAT Position|アプリケーションの起動時には、クイック アクセス ツールバーの位置を指定します。 位置には、いずれかを指定できる**上**または**下**リボン コントロール。|  
|QAT Items|クイック アクセス ツールバーで利用可能なコマンドを指定します。|  
  
#### <a name="to-add-or-remove-commands-on-the-quick-access-toolbar"></a>追加またはクイック アクセス ツールバーのコマンドを削除するには  
  
1.  **プロパティ**ウィンドウで、をクリックして**QAT Items**、省略記号ボタンをクリックして **([...])**.  
  
2.  **QAT Items エディター**ダイアログ ボックスで、使用、**追加**と**削除**クイック アクセス ツールバーのコマンドの一覧を変更するボタンです。  
  
3.  クイック アクセス ツールバーとメニューの クイック アクセス ツールバーの両方に表示するコマンドを実行する場合に、コマンドの横にあるボックスをオンにします。 メニューにのみ表示するコマンドを実行する場合、ボックスをオフにします。  
  
## <a name="previewing-the-ribbon"></a>リボンのプレビュー  
 クイック アクセス ツールバーのコマンドは、デザイン サーフェイスは表示されません。 表示するには、リボンのプレビューか、アプリケーションを実行する必要があります。  
  
#### <a name="to-preview-the-ribbon-control"></a>リボン コントロールをプレビューするには  
  
-   **Ribbon エディター ツールバー**をクリックして**Ribbon のテスト**です。  
  
## <a name="see-also"></a>関連項目  
 [リボン デザイナー (MFC)](../mfc/ribbon-designer-mfc.md)

