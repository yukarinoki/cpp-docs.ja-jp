---
title: COM インターフェイス (Visual C) の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.com.creating.interfaces
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, creating
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2844e9051c5e6adf14085bcd7bfcd8096c6f8f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-com-interface-visual-c"></a>COM インターフェイスの作成 (Visual C++)
Visual C には、COM オブジェクトとオートメーション クラスを COM インターフェイス定義とディスパッチ インターフェイスを使用するプロジェクトを作成するには、ウィザードとテンプレートが用意されています。  
  
 これらのウィザードを使用して、次の 3 つの一般的なタスクを実行できます。  
  
-   [MFC プロジェクトへの ATL サポートの追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     MFC プロジェクトを使用して、作成した後に、MFC アプリケーションに ATL サポートを追加、 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)を実行して、 **MFC に ATL サポートを追加**コード ウィザード。 このサポートは、MFC の実行可能ファイルまたは DLL プロジェクトに追加する単純なの COM オブジェクトにのみ適用されます。 これらの ATL オブジェクトでは、複数のインターフェイスがあります。  
  
-   [MFC ActiveX コントロールの作成](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     開く、 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)ディスパッチ インターフェイスと、それぞれ、.idl ファイルと、コントロール クラスで定義されているイベント マップ ActiveX コントロールを作成します。  
  
-   [ATL コントロールの追加](../atl/reference/adding-an-atl-control.md)  
  
     組み合わせを使用して、 [ATL プロジェクト ウィザード](../atl/reference/atl-project-wizard.md)と[ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)ATL の ActiveX コントロールを作成します。  
  
     前述のとおり、ATL サポートを追加した MFC プロジェクトに ATL コントロールを追加できます。 さらに、選択した場合**ATL コントロール**で、**クラスの追加**ダイアログ ボックスで、していないまだ ATL サポートを追加 MFC プロジェクトへ、Visual Studio に ATL サポートを追加することを確認するダイアログ ボックスが表示されます、MFC プロジェクトです。  
  
     このウィザードは、プロジェクトのクラスの IDL ソースと COM マップを生成します。  
  
 開くには、ATL プロジェクトを作成したら、[クラスの追加](../ide/add-class-dialog-box.md) ダイアログ ボックスからの COM インターフェイスをプロジェクトに追加するには、追加のウィザードおよびテンプレートの選択を提供します。 次のウィザードでは、オブジェクトの 1 つまたは複数のインターフェイスを確立できます。  
  
-   [ATL COM+ 1.0 コンポーネント ウィザード](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)  
  
-   [ATL Active Server Page コンポーネント ウィザード](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)  
  
 クラス ビュー で、オブジェクトのコントロール クラスを右クリックし、COM コントロールに新しいインターフェイスを実装するさらに、[インターフェイスの実装](../ide/implement-interface-wizard.md)です。  
  
> [!NOTE]
>  Visual Studio では、プロジェクトにインターフェイスを追加するウィザードが提供されません。 ATL プロジェクトをまたはインターフェイスを追加することができます、 [MFC プロジェクトへの ATL サポートの追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)単純なオブジェクトを使用して、追加することによって、 [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)です。 代わりに、プロジェクトの .idl ファイルを開き」と入力して、インターフェイスを作成します。  
  
```  
interface IMyInterface {  
};  
  
```  
  
 参照してください[インターフェイスを実装する](../ide/implementing-an-interface-visual-cpp.md)と[を追加するオブジェクトと ATL プロジェクトへのコントロールの](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)詳細についてはします。  
  
 Visual C では、いくつかの方法を表示して[COM インターフェイスを編集](../ide/editing-a-com-interface.md)プロジェクトに対して定義されています。 [クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)のすべてのインターフェイスまたはディスパッチ インターフェイスの C++ プロジェクトに .idl ファイルで定義されているアイコンが表示されます。  
  
 ATL ベースの COM オブジェクトのクラス、クラス ビューは、ATL クラスおよび実装するインターフェイスとの間のリレーションシップを表示する ATL クラスの COM マップを読み取ります。  
  
 クラス ビュー、そのショートカット メニューでインターフェイスで次のように操作できます。  
  
-   ATL オブジェクトを MFC ベースのアプリケーションに追加します。  
  
-   メソッド、プロパティ、およびイベントを追加します。  
  
-   アイテムをダブルクリックして、項目のインターフェイス コードに直接ジャンプします。  
  
## <a name="see-also"></a>関連項目  
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)