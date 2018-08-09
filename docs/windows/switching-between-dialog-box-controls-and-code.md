---
title: ダイアログ ボックスのコントロールとコード間の切り替え |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog editor, accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog editor, switching between controls and code
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b288e97030cad7e38caf19fb47f7a058c3ead61d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643109"
---
# <a name="switching-between-dialog-box-controls-and-code"></a>ダイアログ ボックス コントロールとコード間の切り替え
MFC アプリケーションで、ハンドラーのコードに移動する、またはハンドラー関数スタブをすばやく作成するためのダイアログ ボックス コントロールをダブルクリックできます。  
  
 コントロールを選択すると、をクリックして、**イベント コントロール**ボタンまたは**メッセージ**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)Windows メッセージおよびイベントの完全な一覧を表示するには選択した項目に使用できます。 作成または編集ハンドラー関数の一覧から選択します。  
  
### <a name="to-jump-to-code-from-the-dialog-editor"></a>ダイアログ エディターからコードに移動するには  
  
1.  最後に実装されたメッセージ処理関数の宣言にジャンプ ダイアログ ボックス内のコントロールをダブルクリックします。 (ATL ベースのダイアログ クラスでは、常にジャンプするコンス トラクターの定義。)  
  
### <a name="to-view-events-for-a-control"></a>コントロールのイベントを表示するには  
  
1.  コントロールを選択すると、をクリックして、**イベント コントロール**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
    > [!NOTE]
    >  クリックすると、**イベント コントロール**ボタン、 *ダイアログ ボックス*し展開すると、個々 のコントロールのイベントの編集 ダイアログ ボックスにフォーカスが公開のすべてのコントロールの一覧があります。  
  
     右クリックして選択できます ダイアログ ボックスの 1 つのコントロールにフォーカスした場合、**イベント ハンドラーの追加**ショートカット メニューから。 これにより、ハンドラーを追加するクラスを指定することができます。 詳細については、次を参照してください。[イベント ハンドラーの追加](../ide/adding-an-event-handler-visual-cpp.md)します。  
  
### <a name="to-view-messages-for-a-dialog-box"></a>メッセージ ダイアログ ボックスを表示するには  
  
1.  ダイアログ ボックスを選択して、をクリックして、**メッセージ**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ エディター](../windows/dialog-editor.md)