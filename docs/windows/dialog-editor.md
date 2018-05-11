---
title: ダイアログ エディター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
dev_langs:
- C++
helpviewer_keywords:
- resource editors, Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes, editing
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b8cb99b2002dab3fb04ffa8c5b117a49d23adc1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="dialog-editor"></a>ダイアログ エディター
ダイアログ エディターを使用すると、ダイアログ ボックス リソースの作成や編集ができます。 リソース ビュー ウィンドウで、ダイアログの .rc ファイルをダブルクリックして、ダイアログ エディターを開きます (**ビュー&#124;リソース ビュー**)。 リソース ビューは Express Edition では使用できないことに注意してください。  
  
 ダイアログ ボックスまたはダイアログ ボックス テンプレートを新規作成する場合の最初のステップの 1 つは、ダイアログ ボックスにコントロールを追加することです。 ダイアログ エディターでは、コントロールを特定のサイズ、形状、またはアラインメントに収まるように調整したり、ダイアログ ボックス内での操作のために移動したりできます。 また、コントロールは簡単に削除できます。  
  
 ダイアログ ボックスをテンプレートとして格納すると、後で再利用できます。 また、ダイアログ ボックスのデザインと実装コードの編集の間の切り替えも簡単です。  
  
 さらに、ダイアログ エディターでは、単一または複数のコントロールのプロパティを編集できます。 タブ オーダー、つまり Tab キーが押されたときにコントロールがフォーカスを取得する順序を変更したり、ユーザーがキーボードを使用してコントロールを選択できるように、アクセス キー (キーの組み合わせ) を定義したりできます。 事前に設定されているアクセス キーの一覧については、「 [ダイアログ エディターのアクセラレータ キー](../windows/accelerator-keys-for-the-dialog-editor.md)」を参照してください。  
  
 ダイアログ エディターでは、ActiveX コントロールなどのカスタム コントロールを使用することもできます。 さらに、 [フォーム ビュー](../mfc/reference/cformview-class.md)、 [レコード ビュー](../data/record-views-mfc-data-access.md)、または [ダイアログ バー](../mfc/dialog-bars.md)も編集できます。  
  
 Visual Studio 2015 以降では、ダイアログ エディターを使用して、コントロールを移動して、ユーザーがダイアログのサイズを変更する方法を指定する、動的なレイアウトを定義します。 詳細については、「 [Dynamic Layout](../mfc/dynamic-layout.md)」を参照してください。  
  
-   [ダイアログ ボックスの新規作成](../windows/creating-a-new-dialog-box.md)  
  
-   [ユーザーが実行時に終了できないダイアログ ボックスの作成](../windows/creating-a-dialog-box-that-users-cannot-exit.md)  
  
-   [[ダイアログ エディター] ツール バーの表示と非表示](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)  
  
-   [ダイアログ エディターとコードの切り替え](../windows/switching-between-dialog-box-controls-and-code.md)  
  
-   [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)  
  
-   [ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)  
  
-   [ダイアログ ボックスのテスト](../windows/testing-a-dialog-box.md)  
  
-   [ダイアログ エディターのアクセラレータ キー](../windows/accelerator-keys-for-the-dialog-editor.md)  
  
-   [ダイアログ エディターのトラブルシューティング](../windows/troubleshooting-the-dialog-editor.md)  
  
    > [!TIP]
    >  ダイアログ エディターをさまざまな状況で使用している場合は、マウスの右ボタンをクリックすると、頻繁に使用するコマンドのショートカット メニューを表示できます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース エディター](../windows/resource-editors.md)   
 [コントロール](../mfc/controls-mfc.md)   
 [コントロール クラス](../mfc/control-classes.md)   
 [ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)   
 [ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)

