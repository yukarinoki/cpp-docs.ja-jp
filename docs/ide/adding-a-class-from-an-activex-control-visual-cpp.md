---
title: ActiveX コントロール (Visual C) からのクラスの追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 793adf38da33808371a0df71f671c3e29da75326
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>ActiveX コントロールからのクラスの追加 (Visual C++)
このウィザードを使用すると、使用可能な ActiveX コントロールのインターフェイスからの MFC クラスを作成します。 MFC クラスを追加することができます、 [MFC アプリケーション](../mfc/reference/creating-an-mfc-application.md)、 [MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md)、または[MFC ActiveX コントロール](../mfc/reference/creating-an-mfc-activex-control.md)です。  
  
> [!NOTE]
>  ActiveX コントロールからクラスを追加する有効な Automation では、MFC プロジェクトを作成する必要はありません。  
  
 ActiveX コントロールは、コンポーネント オブジェクト モデル (COM: Component Object Model) に基づく再利用可能なソフトウェア コンポーネントです。多岐にわたる OLE の機能をサポートしており、さまざまなソフトウェアの要件に合わせてカスタマイズできます。 ActiveX コントロールは、通常の ActiveX コントロール コンテナーと World Wide Web ページで、インターネット上の両方に使用する設計されています。  
  
### <a name="to-add-an-mfc-class-from-an-activex-control"></a>ActiveX コントロールからの MFC クラスを追加するには  
  
1.  いずれかで**ソリューション エクスプ ローラー**または[クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)、ActiveX コントロール クラスを追加するプロジェクトの名前を右クリックします。  
  
2.  ショートカット メニューをクリックして**追加**、クリックして**クラスの追加**です。  
  
3.  [クラスの追加](../ide/add-class-dialog-box.md)ダイアログ ボックスの [テンプレート] ペインで、クリックして**ActiveX コントロールからの MFC クラス**、順にクリック**開く**を表示する、 [ActiveX からのクラスの追加ウィザードの制御](../ide/add-class-from-activex-control-wizard.md)です。  
  
 ウィザードで、ActiveX コントロールにおける 1 つ以上のインターフェイスを追加することができます。 同様に、1 つのウィザード セッションで 1 つ以上の ActiveX コントロールからクラスを作成することができます。  
  
 クラスを追加するには、システムに登録されている ActiveX コントロールからまたはタイプ ライブラリ ファイル (.tlb、.olb、.dll、.ocx、または .exe) 最初を登録せずに、システム内にある ActiveX コントロールからクラスを追加することができます。 参照してください[OLE コントロールの登録](../mfc/reference/registering-ole-controls.md)ActiveX コントロールを登録する方法の詳細についてはします。  
  
 派生した MFC クラスを作成するウィザード[CWnd](../mfc/reference/cwnd-class.md)またはから[COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)、選択された ActiveX コントロールから追加する各インターフェイスに対してです。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [COM と ATL の概要](../atl/introduction-to-com-and-atl.md)