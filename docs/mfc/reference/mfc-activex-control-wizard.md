---
title: MFC ActiveX コントロール ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.ctl.overview
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45af43a98244e90f52075817fc9e17a905cbf065
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375064"
---
# <a name="mfc-activex-control-wizard"></a>MFC ActiveX コントロール ウィザード
ActiveX コントロールは、特定の種類の[オートメーション サーバー](../../mfc/automation-servers.md); が再利用可能なコンポーネントです。 ActiveX コントロールをホストしているアプリケーションは、[オートメーション クライアント](../../mfc/automation-clients.md)を制御するのです。 目標は、このような再利用可能なコンポーネントを作成するの場合は、コントロールを作成するこのウィザードを使用します。 参照してください[MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md)詳細についてはします。  
  
 オートメーション サーバー MFC アプリケーションを使用して、作成する代わりに、 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)です。  
  
 このウィザードで作成された ActiveX コントロールは、ユーザー インターフェイスを持つことができますも表示されていることができます。 このオプションを指定することができます、[コントロール設定](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)ウィザードのページです。 タイマー コントロールは、非表示にすると、ActiveX コントロールの例です。  
  
 ActiveX コントロールは、複雑なユーザー インターフェイスを持つことができます。 カプセル化されたフォームのようないくつかのコントロールがあります: 多く含む 1 つのコントロール フィールド、それぞれ独自の右にある Windows のコントロールです。 たとえば、MFC ActiveX コントロールとして実装された自動パーツ オブジェクトは、フォームのようなユーザー インターフェイスを使用するユーザーを読み取ったし、部品番号、構成の名前、およびその他の情報を編集を提供する可能性があります。 参照してください[MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md)詳細についてはします。  
  
 ActiveX オブジェクトのコンテナーを作成する必要がある場合は、次を参照してください。 [ActiveX コントロール コンテナーを作成する](../../mfc/reference/creating-an-mfc-activex-control-container.md)です。  
  
 MFC スターター プログラムには、C++ ソース (.cpp) ファイル、リソース (.rc) ファイル、およびプロジェクト (.vcxproj) ファイルが含まれています。 これらの初期ファイルで生成されたコードは、MFC に基づいています。  
  
 次のサンプル一覧は、タスクおよび ActiveX コントロールの機能強化の種類を示しています。  
  
-   [ActiveX コントロールを最適化します。](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [ActiveX コントロールへのストック イベントの追加](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [カスタム イベントの追加](../../mfc/mfc-activex-controls-adding-custom-events.md)  
  
-   [ストック メソッドの追加](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [カスタム メソッドの追加](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [ストック プロパティの追加](../../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [カスタム プロパティの追加](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [ActiveX コントロール コンテナーで ActiveX コントロールのプログラミング](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## <a name="overview"></a>概要  
 このウィザード ページでは、MFC ActiveX コントロール プロジェクトを作成するのには、現在のアプリケーション設定について説明します。 既定では、このウィザードでは、次のようなウィザード プロジェクトが作成されます。  
  
-   既定のプロジェクトには、実行時ライセンスまたはヘルプ ファイルを生成されません。 既定の設定を変更することができます、[アプリケーション設定](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)ページ。 ActiveX コントロール ウィザードのこのページで選択した内容のみが反映されます、**概要**ページ。  
  
-   プロジェクトには、コントロール クラスと、プロジェクトの名前に基づいて、プロパティ ページ クラスが含まれています。 プロジェクト名とファイル名の名前を編集することができます、[コントロール名](../../mfc/reference/control-names-mfc-activex-control-wizard.md)ページ。  
  
-   コントロールがない既存の Windows コントロールに基づくが、これが表示され、ユーザー インターフェイスを持つを含めた場合にアクティブ化、**に関する** ダイアログ ボックス。 既定の設定を変更することができます、[コントロール設定](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)ページ。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ プロジェクトの作成および管理](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual C プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [概念](../../atl/active-template-library-atl-concepts.md)

