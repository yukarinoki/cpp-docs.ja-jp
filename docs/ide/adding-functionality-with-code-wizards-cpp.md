---
title: コード ウィザード (C++) による機能の追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes
dev_langs:
- C++
helpviewer_keywords:
- code wizards [C++]
- wizards [C++], code
- Visual C++ projects, adding functionality
- projects [C++], adding functionality
- class wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55a2bb282d19a48cfd510056e327e7abca4de4ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="adding-functionality-with-code-wizards-c"></a>コード ウィザード (C++) を使用した機能を追加します。
プロジェクトを作成した後はするプロジェクトの機能を変更または追加します。 このようなタスクには、新しいメンバー関数と変数、および追加のオートメーション メソッドおよびプロパティの追加、新しいクラスの作成が含まれます。 コード ウィザードは、これらすべての操作を実行できるように設計されています。  
  
> [!NOTE]
>  メッセージ ハンドラーを追加し、メッセージをマップし、できますを使用して MFC 仮想関数をオーバーライドします[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
## <a name="accessing-visual-c-code-wizards"></a>Visual C コード ウィザードにアクセスします。  
 Visual C コード ウィザードにアクセス可能な 3 つの場所。  
  
-   **プロジェクト** メニュー、**新しい項目の追加**コマンドでは、表示することができます、 `Add New Item`  ダイアログ ボックスは、新しいファイルをプロジェクトに追加することができます。 **クラスの追加**コマンドが表示されます、[クラスの追加](../ide/add-class-dialog-box.md)さらに、クラスの各型にするウィザードを開く ダイアログ ボックスは、プロジェクトに追加できます。 **リソースの追加**コマンドが表示されます、[リソースの追加](../windows/add-resource-dialog-box.md)ダイアログ ボックスで作成またはリソースを選択してプロジェクトに追加することができます。  
  
     クラス ビュー で、プロジェクトでは、クラスまたはインターフェイスを強調表示した場合、**プロジェクト**メニューには、次のコマンドも表示されます。  
  
    -   **インターフェイスを実装して**(、コントロール クラスからのみ)  
  
    -   **関数を追加します。**  
  
    -   **変数を追加します。**  
  
    -   **接続ポイントを追加**(ATL クラスのみ)  
  
    -   **メソッドを追加**(インターフェイスからのみ)  
  
    -   **プロパティを追加**(インターフェイスからのみ)  
  
    -   **イベントの追加**(、コントロール クラスからのみ)  
  
-   **ソリューション エクスプ ローラー**任意のフォルダーを右クリックしをクリックすると、**追加**、ショートカットからメニューを使用して新規または既存のファイル、フォルダー、項目、クラス、リソースを追加して、[Web 参照] をプロジェクトです。  
  
-   [クラス ビュー ウィンドウ](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)、適切なノードを右クリックしをクリックすると、**追加**、ショートカットからメニューを使用して関数、変数、クラス、プロパティ、メソッド、イベント、インターフェイスを追加するには接続ポイントまたはその他のコードをプロジェクトにします。  
  
    > [!NOTE]
    >  Visual Studio では、プロジェクトにインターフェイスを追加するウィザードが提供されません。 ATL プロジェクトをまたはインターフェイスを追加することができます、 [MFC プロジェクトへの ATL サポートの追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)単純なオブジェクトを使用して、追加することによって、 [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)です。 代わりに、プロジェクトの .idl ファイルを開き」と入力して、インターフェイスを作成します。  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     参照してください[インターフェイスを実装する](../ide/implementing-an-interface-visual-cpp.md)と[を追加するオブジェクトと ATL プロジェクトへのコントロールの](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)詳細についてはします。  
  
    |アクセス コード ウィザード|説明|  
    |-----------------------------|-----------------|  
    |新しい項目の追加|新しい項目の追加コード ウィザードは、ソース ファイルをプロジェクトに追加します。 必要に応じて、それらを探して、プロジェクトのビルド エンジンが期待されている場所のファイルを格納する追加のディレクトリが作成されます。 項目の追加アイコンから使用できるコード ウィザードは次のとおりです。<br /><br /> -C++ ソース ファイル (.cpp、.h、.idl、.rc、.srf、.def、.rgs) を追加します。<br />-Web 開発ファイル (*.htm;*.html、.asp、.css、.xml) を追加します。<br />-ユーティリティ ファイルとリソース ファイル (.bmp、.cur、.ico、.rct、.sql、.txt) を追加します。<br /><br /> これらのコード ウィザードは通常の情報を要求しないが、開発のツリーにファイルを追加します。 [プロパティ] ウィンドウで、ファイルの名前を変更することがあります。|  
    |ソリューション エクスプローラー|ソリューション エクスプ ローラーから使用できるコード ウィザードは、項目を右クリックすると、カーソルのフォーカスがここではによって異なります。 場合、**追加**開発ツリー内で 1 レベル上にカーソルを移動し、項目を右クリックすると、オプションが表示されないと、もう一度やり直してください。 コード ウィザードは場所にカーソルがあるかにかかわらず開発ツリーで、適切な場所に追加のコードを常に配置します。 ソリューション エクスプ ローラーから使用できるコード ウィザードは次のとおりです。<br /><br /> クラスを追加 (開きます、**クラスの追加** ダイアログ ボックスの新しいコード ウィザードを含む)。<br />-リソースの追加 (新規、インポート、またはカスタム)。<br />-Web 参照を追加します。|  
    |クラス ビュー|クラス ビューから入手できるコード ウィザードは、カーソルのフォーカス、項目を右クリックしたときの位置によって異なります。 場合、**追加**上の 1 つのレベル、クラス ツリーで、ポインターを移動し、項目を右クリックしたときにオプションが表示されないと、もう一度やり直してください。 コード ウィザードは場所にカーソルがあるかにかかわらず開発ツリーで、適切な場所に追加のコードを常に配置します。 クラス ビューから使用できるコード ウィザードは次のとおりです。<br /><br /> -   [メンバー関数を追加](../ide/adding-a-member-function-visual-cpp.md)です。<br />-   [メンバー変数を追加](../ide/adding-a-member-variable-visual-cpp.md)です。<br />-   [クラスの追加](../ide/adding-a-class-visual-cpp.md)です。<br />-   [インターフェイスを実装して](../ide/implement-interface-wizard.md)(、コントロール クラスからのみ)<br />-   [接続ポイントを追加](../ide/implement-connection-point-wizard.md)(ATL クラスのみ)<br />-   [メソッドを追加](../ide/add-method-wizard.md)(インターフェイスからのみ)<br />-   [プロパティを追加](../ide/names-add-property-wizard.md)(インターフェイスからのみ)<br />-   [イベントの追加](../ide/add-event-wizard.md)(、コントロール クラスからのみ)<br /><br /> クラスの追加の選択 を開きます、**クラスの追加** ダイアログ ボックスは、すべての新しいクラスの追加コード ウィザードに対するアクセスを提供します。|  
  
## <a name="see-also"></a>関連項目  
 [仮想関数のオーバーライド](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [クラス各部へ](../ide/navigating-the-class-structure-visual-cpp.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Visual C プロジェクトの種類](../ide/visual-cpp-project-types.md)   
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)