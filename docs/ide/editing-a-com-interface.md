---
title: COM インターフェイスの編集 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.com.editing.interfaces
dev_langs:
- C++
helpviewer_keywords:
- methods [C++], adding to COM interfaces
- COM interfaces, editing
- properties [C++], adding to COM interfaces
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd7a61593a1024c00c0fd0de6bd62ff3ee9323b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338683"
---
# <a name="editing-a-com-interface"></a>COM インターフェイスの編集
クラス ビューのショートカット メニューからコマンドを使用することで、Visual C++ プロジェクトで COM インターフェイスの新しいメソッドとプロパティを定義できます。 さらに、ツールボックスから、ActiveX コントロールのイベントを定義することができます。  
  
 ATL ベースと MFC ベースの COM オブジェクト クラスでは、インターフェイスの編集と同時にクラス実装を編集することができます。  
  
> [!NOTE]
>  **[クラスの追加]** ダイアログ ボックス外で定義されたインターフェイスの場合、Visual C++ はメソッドまたはプロパティを .idl ファイルに追加し、メソッドを実装するクラスにスタブを追加します。インターフェイスが手動で追加されている場合でも同様です。  
  
 次の 3 つのウィザードは、既存のインターフェイスをカスタマイズするのに役立ちます。 クラス ビューからは以下を利用できます。  
  
|ウィザード|プロジェクトの種類|  
|------------|------------------|  
|[プロパティ追加ウィザード](../ide/names-add-property-wizard.md)|ATL をサポートする ATL プロジェクトまたは MFC プロジェクト。 プロパティを追加するインターフェイスを右クリックします。<br /><br /> Visual C++ ではプロジェクトの種類が検出され、適宜、プロパティ追加ウィザードでオプションが変更されます。<br /><br /> -   [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)を使用して作成されたプロジェクトのディスパッチ インターフェイスの場合、プロパティ追加ウィザードを起動すると、MFC に固有のオプションが提供されます。<br />-   MFC ActiveX コントロール インターフェイスの場合、プロパティ追加ウィザードではストック メソッドとプロパティの一覧が提供されます。これをそのまま使用することも、ご利用のコントロール用にカスタマイズすることもできます。<br />-   他のすべてのインターフェイスの場合、プロパティ追加ウィザードではほとんどの状況で役立つオプションが提供されます。|  
|[メソッド追加ウィザード](../ide/add-method-wizard.md)|ATL をサポートする ATL プロジェクトまたは MFC プロジェクト。 メソッドを追加するインターフェイスを右クリックします。<br /><br /> Visual C++ ではプロジェクトの種類が検出され、適宜、メソッド追加ウィザードでオプションが変更されます。<br /><br /> -   [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)を使用して作成されたプロジェクトのディスパッチ インターフェイスの場合、メソッド追加ウィザードを起動すると、MFC に固有のオプションが提供されます。<br />-   MFC ActiveX コントロール インターフェイスの場合、メソッド追加ウィザードではストック メソッドとプロパティの一覧が提供されます。これをそのまま使用することも、ご利用のコントロール用にカスタマイズすることもできます。<br />-   他のすべてのインターフェイスの場合、**メソッド追加**ウィザードではほとんどの状況で役立つオプションが提供されます。|  
  
 さらに、クラス ビューでオブジェクトのコントロール クラスを右クリックし、[[インターフェイスの実装]](../ide/implement-interface-wizard.md) をクリックすることで、COM コントロールに新しいインターフェイスを実装できます。  
  
## <a name="see-also"></a>参照  
 [リソース ファイルの操作](../windows/working-with-resource-files.md)   
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C++ プロジェクトの種類](../ide/visual-cpp-project-types.md)