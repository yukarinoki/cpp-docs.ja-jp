---
title: オプション、ATL コントロール ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab1062d32aadc2ec4af68cda8bca02ac1a45a526
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364474"
---
# <a name="options-atl-control-wizard"></a>オプション、ATL コントロール ウィザード
「検索結果」の概要をここに挿入します。  
  
 ウィザードのこのページを使用すると、作成するコントロールの種類とが含まれているインターフェイスのサポートのレベルを定義します。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **コントロール型**  
 作成するコントロールの種類。  
  
-   **標準コントロール: ActiveX コントロール。**  
  
-   **複合コントロール**: ActiveX コントロール (ダイアログ ボックスに似ています) を含めることができる他の ActiveX コントロールまたは Windows のコントロールです。 複合コントロールは次のとおりです。  
  
    -   複合コントロールを実装するダイアログ ボックスのテンプレートです。  
  
    -   カスタム リソースの場合は、レジストリで、自動的に呼び出されたときに、複合コントロールを登録します。  
  
    -   複合コントロールを実装する C++ クラスです。  
  
    -   複合コントロールによって公開される COM インターフェイスです。  
  
    -   複合コントロールを含む HTML テスト ページ。  
  
     既定では、このコントロールの設定[CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly)にする場合は true、ウィンドウを持つコントロールであることを示します。 シンク マップを実装します。 詳細については、次を参照してください。 [DHTML コントロールのサポート](../../atl/atl-support-for-dhtml-controls.md)です。  
  
-   **DHTML コントロール**: An ATL DHTML コントロールが HTML を使用して、ユーザー インターフェイスを指定します。 DHTML UI クラスには、COM マップが含まれています。 既定では、このコントロールの設定[CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly)にする場合は true、ウィンドウを持つコントロールであることを示します。  
  
     詳細については、次を参照してください。 [DHTML コントロール プロジェクトの要素の識別](../../atl/identifying-the-elements-of-the-dhtml-control-project.md)です。  
  
 **最小限の制御**  
 ほとんどのコンテナーに必須のインターフェイスのみをサポートしています。 設定することができます**最小限の制御**コントロールの種類のいずれかの: 最小限の標準的な制御、最小限の複合コントロールまたは最小限に抑える DHTML コントロールを作成することができます。  
  
 **集計**  
 作成するコントロールの集計のサポートを追加します。 詳細については、次を参照してください。[集計](../../atl/aggregation.md)です。  
  
-   **[はい]**: 集計できるコントロールを作成します。  
  
-   **いいえ**: 集計が不可能なコントロールを作成します。  
  
-   **のみ**: 集約を介してのみインスタンス化するコントロールを作成します。  
  
 **スレッド処理モデル**  
 コントロールによってスレッド モデルが使用されることを指定します。  
  
-   **1 つ**: コントロールがプライマリ COM スレッドでのみ実行されます。  
  
-   **アパートメント**: 任意の 1 つのスレッドのアパートメントでのコントロールを作成することができます。 これが既定値です。  
  
 **Interface**  
 このコントロールがコンテナーに公開するインターフェイスの型。  
  
-   **デュアル**: プロパティとメソッドを介して公開されるインターフェイスを作成`IDispatch`VTBL を介して直接、します。  
  
-   **カスタム**: VTBL によって直接メソッドを公開するインターフェイスを作成します。  
  
     選択した場合**カスタム**、コントロールことを指定することができますし、**オートメーション互換性**です。 選択した場合**オートメーション互換性**、し、ウィザードの追加、 [oleautomation](../../windows/oleautomation.md)属性、IDL 内にあるインターフェイスを oleaut32.dll でユニバーサル、マーシャラーによってインターフェイスをマーシャ リングすることができます。 参照してください[マーシャ リングの詳細](http://msdn.microsoft.com/library/windows/desktop/ms692621)詳細については、Windows SDK に含まれています。  
  
     さらに、選択した場合**オートメーション互換性**、コントロールのすべてのメソッドのすべてのパラメーターである必要があります**バリアント**互換性。  
  
 **サポート**  
 コントロールの他のサポートを設定します。  
  
-   **コネクション ポイント**: オブジェクトのクラスから派生することで、オブジェクトのコネクション ポイントを有効に[入力したコネクション](../../atl/reference/iconnectionpointcontainerimpl-class.md)ソース インターフェイスを公開することができるとします。  
  
-   **ライセンス**: に、コントロールのサポートを追加[ライセンス](http://msdn.microsoft.com/library/windows/desktop/ms690543)です。 クライアント コンピューターに適切なライセンスがある場合にのみ、ライセンスされたコントロールをホストすることができます。  
  
## <a name="see-also"></a>関連項目  
 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)

