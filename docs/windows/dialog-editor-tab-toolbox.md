---
title: ダイアログ エディターのタブ、ツールボックス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls ino dialog boxes
- custom controls [Visual Studio], dialog boxes
- controls [C++], standard
- Dialog editor, creating controls
- controls [C++], adding to dialog boxes
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb7da9e08d44435570180859c1614f7817595833
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882577"
---
# <a name="dialog-editor-tab-toolbox"></a>[ダイアログ エディター] タブ ([ツールボックス])
ダイアログ エディターのタブに表示されます、[ツールボックス ウィンドウ](/visualstudio/ide/reference/toolbox)ダイアログ エディターで作業する場合。 新しいダイアログ ボックスにコントロールを追加するを作成する ダイアログ ボックスに、ツールボックスからコントロールをドラッグします。 (詳細については、次を参照してください。 [ ダイアログ ボックスにコントロールを追加する](adding-a-control-to-a-dialog-box.md))。 次いでコントロールの移動、またはサイズと形状の変更ができます。  
  
 ツールボックスで使用できる標準コントロールは次のとおりです。  
  
-   [ボタン コントロール](../mfc/reference/cbutton-class.md)  
  
-   [チェック ボックス コントロール](../mfc/reference/styles-used-by-mfc.md#button-styles)  
  
-   [コンボ ボックス コントロール](../mfc/reference/ccombobox-class.md)  
  
-   [エディット コントロール](../mfc/reference/cedit-class.md)  
  
-   グループ ボックス  
  
-   [リスト ボックス コントロール](../mfc/reference/clistbox-class.md)  
  
-   [ラジオ ボタン コントロール](../mfc/reference/styles-used-by-mfc.md#button-styles)  
  
-   [スタティック テキスト コントロール](../mfc/reference/cstatic-class.md)  
  
-   [画像コントロール](../mfc/reference/cpictureholder-class.md)  
  
-   [リッチ エディット 2.0 コントロール](../mfc/using-cricheditctrl.md)  
  
-   [スクロール バー コントロール](../mfc/reference/cscrollbar-class.md)  
  
 [Windows コモン コントロール](../mfc/controls-mfc.md)ツールボックスで使用可能なアプリケーションで高度な機能を提供します。 Windows コモン コントロールには以下が含まれます。  
  
-   [スライダー コントロール](../mfc/slider-control-styles.md)  
  
-   [スピン コントロール](../mfc/using-cspinbuttonctrl.md)  
  
-   [プログレス コントロール](../mfc/styles-for-the-progress-control.md)  
  
-   [ホット キー コントロール](../mfc/using-a-hot-key-control.md)  
  
-   [リスト コントロール](../mfc/list-control-and-list-view.md)  
  
-   [ツリー コントロール](../mfc/tree-control-styles.md)  
  
-   [タブ コントロール](../mfc/tab-controls-and-property-sheets.md)  
  
-   [アニメーション コントロール](../mfc/using-an-animation-control.md)  
  
-   [日時指定コントロール](../mfc/creating-the-date-and-time-picker-control.md)  
  
-   [月間予定表コントロールします。](../mfc/month-calendar-control-examples.md)  
  
-   [IP アドレス コントロール](../mfc/reference/cipaddressctrl-class.md)  
  
-   [拡張コンボ ボックス コントロール](../mfc/creating-an-extended-combo-box-control.md)  
  
-   [カスタム コントロール](custom-controls-in-the-dialog-editor.md)  
  
 選択すると、ダイアログ ボックスにカスタム コントロールを追加できます、**カスタム コントロール**ダイアログ ボックスにドラッグして、ツールボックスのアイコン。 Syslink コントロールを追加するには、カスタム コントロールを追加し、変更するコントロールの**クラス**プロパティを**Syslink**です。 これにより、プロパティが更新され、Syslink コントロールのプロパティが表示されます。 MFC ラッパー クラスについては、次を参照してください。 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)です。  
  
 必要な場合も[ ダイアログ ボックスに ActiveX コントロールを追加](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)です。  
  
 また、より簡単に使用できるようにツールボックス ウィンドウをカスタマイズすることもできます。 詳細については、「[ツールボックスの使用](/visualstudio/ide/using-the-toolbox)」を参照してください。  

 MFC での RichEdit 1.0 コントロールの使用の詳細については、次を参照してください[MFC での RichEdit 1.0 コントロールの使用。](../windows/using-the-richedit-1-0-control-with-mfc.md)  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [コントロール](../mfc/controls-mfc.md)   
 [コントロール クラス](../mfc/control-classes.md)   
 [ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)   
 [スクロール バー スタイル](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)   
 [リッチ エディット コントロールの例](../mfc/rich-edit-control-examples.md)   
 [ダイアログ ボックス コントロールのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)

