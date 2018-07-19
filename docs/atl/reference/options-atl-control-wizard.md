---
title: オプション、ATL コントロール ウィザード |Microsoft Docs
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
ms.openlocfilehash: a1fa026ecb0b25c17a793c31c3f64dcd0186f0e1
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880097"
---
# <a name="options-atl-control-wizard"></a>オプション、ATL コントロール ウィザード
「検索結果」の概要をここに挿入します。  
  
 ウィザードのこのページを使用して作成するコントロールの種類を定義して、インターフェイスのサポートのレベルが含まれます。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **コントロール型**  
 作成するコントロールの種類。  
  
-   **標準コントロール: ActiveX コントロール。**  
  
-   **複合コントロール**: ActiveX コントロール (ダイアログ ボックスに似ています) を含めることができる他の ActiveX コントロールまたは Windows のコントロール。 複合コントロールを次のとおりです。  
  
    -   複合コントロールを実装するダイアログ ボックスのテンプレート。  
  
    -   カスタム リソースの場合は、レジストリで、呼び出されたときに、複合コントロールを自動的に登録します。  
  
    -   複合コントロールを実装する C++ クラスです。  
  
    -   複合コントロールによって公開される COM インターフェイスです。  
  
    -   複合コントロールを含む HTML テスト ページ。  
  
     既定では、このコントロールの設定[CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly)ウィンドウ付きコントロールであることを示す true にします。 シンクのマップを実装します。 詳細については、次を参照してください。 [DHTML コントロールのサポート](../../atl/atl-support-for-dhtml-controls.md)します。  
  
-   **DHTML コントロール**: An ATL DHTML コントロールが HTML を使用して、ユーザー インターフェイスを指定します。 DHTML UI クラスには、COM マップが含まれています。 既定では、このコントロールの設定[CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly)ウィンドウ付きコントロールであることを示す true にします。  
  
     詳細については、次を参照してください。 [DHTML コントロール プロジェクトの要素の識別](../../atl/identifying-the-elements-of-the-dhtml-control-project.md)します。  
  
 **最小限の制御**  
 ほとんどのコンテナーで絶対に必要なインターフェイスのみをサポートしています。 設定できる**最小限の制御**コントロールの種類のいずれかの: 最小限の標準的な制御、最小限の複合コントロールまたは最小限の DHTML コントロールを作成することができます。  
  
 **集計**  
 作成するコントロールの集計のサポートを追加します。 詳細については、次を参照してください。[集計](../../atl/aggregation.md)します。  
  
-   **[はい]**: 集計が可能なコントロールを作成します。  
  
-   **いいえ**: 集計が不可能なコントロールを作成します。  
  
-   **のみ**: 集計をのみインスタンス化するコントロールを作成します。  
  
 **スレッド モデル**  
 スレッド処理モデルが、コントロールによって使用されることを指定します。  
  
-   **1 つ**: コントロールがプライマリ COM スレッドでのみ実行されます。  
  
-   **アパートメント**: 任意の 1 つのスレッド アパートメントでコントロールを作成できます。 これが既定値です。  
  
 **Interface**  
 このコントロールがコンテナーに公開するインターフェイスの型。  
  
-   **デュアル**: プロパティとメソッドを公開するインターフェイスを作成します。 `IDispatch` 、VTBL を介して直接、します。  
  
-   **カスタム**: VTBL によって直接メソッドを公開するインターフェイスを作成します。  
  
     選択した場合**カスタム**、コントロールがあるかを指定することができますし、 **Automation と互換性のある**します。 選択した場合**Automation と互換性のある**、し、ウィザードを追加、 [oleautomation](../../windows/oleautomation.md)属性、IDL でインターフェイスと oleaut32.dll でユニバーサル マーシャラーによってインターフェイスをマーシャ リングすることができます。 参照してください[マーシャ リングの詳細](http://msdn.microsoft.com/library/windows/desktop/ms692621)詳細については、Windows SDK に含まれています。  
  
     さらに、選択した場合**Automation と互換性のある**コントロールのすべてのメソッドのすべてのパラメーターはバリアントにする必要がありますし、互換性のあります。  
  
 **サポート**  
 コントロールの他のサポートを設定します。  
  
-   **接続ポイント**: オブジェクトの接続ポイントからの派生オブジェクトのクラスを作成することにより[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)とソース インターフェイスを公開することができます。  
  
-   **ライセンス**: コントロールのサポートが追加[ライセンス](http://msdn.microsoft.com/library/windows/desktop/ms690543)します。 クライアント コンピューターに適切なライセンスがある場合にのみ、ライセンスされたコントロールをホストすることができます。  
  
## <a name="see-also"></a>関連項目  
 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)

