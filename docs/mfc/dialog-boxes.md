---
title: ダイアログ ボックス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modeless dialog boxes [MFC], MFC dialog boxes
- MFC, dialog boxes
- modal dialog boxes [MFC], MFC dialog boxes
- CDialog class [MFC], MFC dialog boxes
- MFC dialog boxes
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c8de283d81aa9d260b891f285f06555dc67895f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dialog-boxes"></a>ダイアログ ボックス
Windows アプリケーションの頻繁にユーザーとの通信ダイアログ ボックスを使用します。 クラス[CDialog](../mfc/reference/cdialog-class.md)  ダイアログ ボックスを管理するには、Visual C ダイアログ エディター簡単にダイアログ ボックスを設計およびそのダイアログ テンプレート リソースを作成して、コード ウィザードの初期化処理を簡略化のインターフェイスを提供し、検証コントロール ダイアログ ボックスでは、ユーザーが入力した値を収集しています。  
  
 ダイアログ ボックスではなどのコントロールを含めます。  
  
-   Windows コモン コントロールは、ボックス、プッシュ ボタン、リスト ボックス、コンボ ボックス、ツリー コントロール、リスト コントロール、および進行状況インジケーターなど、編集します。  
  
-   ActiveX コントロール。  
  
-   オーナー描画コントロール: ダイアログ ボックスを描画するために担当しているコントロール。  
  
 ほとんどのダイアログ ボックスは、ユーザーをプログラムの他の部分を使用する前に、ダイアログ ボックスを閉じるを必要とするモーダルでは。 ですが、ユーザー ダイアログ ボックスが開いている間、他のウィンドウで作業できるように、モードレス ダイアログ ボックスを作成すること。 MFC クラスを含むダイアログ ボックスの両方の種類をサポートしている`CDialog`です。 コントロールの配置し、で作成された、ダイアログ テンプレート リソースを使用して管理されている、[ダイアログ エディター](../windows/dialog-editor.md)です。  
  
 [プロパティ シート](../mfc/property-sheets-mfc.md)とも呼ばれるタブ ダイアログ ボックスは個別のダイアログ ボックス コントロールの「ページ」が含まれているダイアログ ボックス。 各ページには、ファイル フォルダーの上部にある「タブ」があります。 タブをクリックすると、ダイアログ ボックスの前にそのページが表示されます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [例: メニュー コマンドによるダイアログ ボックスの表示](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)  
  
-   [フレームワークのダイアログ ボックス コンポーネント](../mfc/dialog-box-components-in-the-framework.md)  
  
-   [モーダルとモードレスのダイアログ ボックス](../mfc/modal-and-modeless-dialog-boxes.md)  
  
-   [プロパティ シートとプロパティ ページ](../mfc/property-sheets-and-property-pages-mfc.md) ダイアログ ボックス  
  
-   [ダイアログ リソースの作成](../mfc/creating-the-dialog-resource.md)  
  
-   [コード ウィザードによるダイアログ クラスの作成](../mfc/creating-a-dialog-class-with-code-wizards.md)  
  
-   [ダイアログ ボックスのライフ サイクル](../mfc/life-cycle-of-a-dialog-box.md)  
  
-   [ダイアログ データ エクス (チェンジ DDX) および検証 (DDV)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)  
  
-   [クラスに Windows メッセージの割り当てください。](../mfc/mapping-windows-messages-to-your-class.md)  
  
-   [通常オーバーライドされるメンバー関数](../mfc/commonly-overridden-member-functions.md)  
  
-   [通常追加されるメンバー関数](../mfc/commonly-added-member-functions.md)  
  
-   [コモン ダイアログ クラス](../mfc/common-dialog-classes.md)  
  
-   [OLE のダイアログ ボックス](../mfc/dialog-boxes-in-ole.md)  
  
-   ユーザー インターフェイスが、ダイアログ ボックスは、アプリケーションを作成します。 を参照してください、 [CMNCTRL1](../visual-cpp-samples.md)または[CMNCTRL2](../visual-cpp-samples.md)サンプル プログラム。 アプリケーションのウィザードでは、このオプションを提供します。  
  
-   [サンプル](../mfc/dialog-sample-list.md)  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
