---
title: ATL プロジェクトで新しいインターフェイスの追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.interface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2c9d0ef4c14760d596a4aa26fa2a929da26c67b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356746"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL プロジェクトで新しいインターフェイスの追加
インターフェイスをオブジェクトやコントロールを追加する場合は、そのインターフェイスで各メソッドのスタブ関数を作成します。 オブジェクトやコントロールでは、既存のタイプ ライブラリ内にあるインターフェイスのみを追加できます。 また、インターフェイスを追加するクラスを実装する必要があります、 [BEGIN_COM_MAP](com-map-macros.md#begin_com_map)マクロまたは、プロジェクトが考えられる場合があります、`coclass`属性。  
  
 2 つの方法のいずれかのコントロールに新しいインターフェイスを追加することができます: 手動でまたはクラス ビュー で、コード ウィザードを使用します。  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>クラス ビュー で、既存のオブジェクトやコントロールをインターフェイスを追加するコード ウィザードを使用するには  
  
1.  [クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)コントロールのクラス名を右クリックします。 たとえば、フル コントロールまたは複合コントロール、または、ヘッダー ファイルで、BEGIN_COM_MAP マクロを実装するその他のコントロール クラスにします。  
  
2.  ショートカット メニューをクリックして**追加**、クリックして**インターフェイスの実装**です。  
  
3.  実装するインターフェイスを選択して、[インターフェイス実装ウィザード](../../ide/implement-interface-wizard.md)です。 インターフェイスが、使用可能なタイプ ライブラリ内に存在しない場合、必要があります、手動で追加する .idl ファイルにします。  
  
### <a name="to-add-a-new-interface-manually"></a>新しいインターフェイスを手動で追加するには  
  
1.  .Idl ファイルを新しいインターフェイスの定義を追加します。  
  
2.  オブジェクトまたはインターフェイスからコントロールを派生します。  
  
3.  新規作成[COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)インターフェイスのプロジェクトに属性が場合の追加、`coclass`属性。  
  
4.  インターフェイスのメソッドを実装します。  
  
## <a name="see-also"></a>関連項目  
 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
 [Visual C プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

