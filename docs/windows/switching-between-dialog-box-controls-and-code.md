---
title: ダイアログ ボックス (C++) のコントロールとコード間の切り替え
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog Editor [C++], accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog Editor [C++], switching between controls and code
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
ms.openlocfilehash: 4d48386e93fcea6d30fee6c57c288944bbd8d9ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644302"
---
# <a name="switching-between-dialog-box-c-controls-and-code"></a>ダイアログ ボックス (C++) のコントロールとコード間の切り替え

MFC アプリケーションで、ハンドラーのコードに移動する、またはハンドラー関数スタブをすばやく作成するためのダイアログ ボックス コントロールをダブルクリックできます。

コントロールを選択すると、をクリックして、**イベント コントロール**ボタンまたは**メッセージ**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)Windows メッセージおよびイベントの完全な一覧を表示するには選択した項目に使用できます。 作成または編集ハンドラー関数の一覧から選択します。

### <a name="to-jump-to-code-from-the-dialog-editor"></a>ダイアログ エディターからコードに移動するには

1. 最後に実装されたメッセージ処理関数の宣言にジャンプ ダイアログ ボックス内のコントロールをダブルクリックします。 (ATL ベースのダイアログ クラスでは、常にジャンプするコンス トラクターの定義。)

### <a name="to-view-events-for-a-control"></a>コントロールのイベントを表示するには

1. コントロールを選択すると、をクリックして、**イベント コントロール**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

   > [!NOTE]
   > クリックすると、**イベント コントロール**ボタン、 * ダイアログ ボックス*し展開すると、個々 のコントロールのイベントの編集 ダイアログ ボックスにフォーカスが公開のすべてのコントロールの一覧があります。

   右クリックして選択できます ダイアログ ボックスの 1 つのコントロールにフォーカスした場合、**イベント ハンドラーの追加**ショートカット メニューから。 これにより、ハンドラーを追加するクラスを指定することができます。 詳細については、次を参照してください。[イベント ハンドラーの追加](../ide/adding-an-event-handler-visual-cpp.md)します。

### <a name="to-view-messages-for-a-dialog-box"></a>メッセージ ダイアログ ボックスを表示するには

1. ダイアログ ボックスを選択して、をクリックして、**メッセージ**ボタン、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ エディター](../windows/dialog-editor.md)