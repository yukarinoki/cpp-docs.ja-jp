---
title: オプション、ATL コントロール ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.control.options
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
ms.openlocfilehash: e607e35b2b3970f329692ba8d2c612d7f6a6591b
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522312"
---
# <a name="options-atl-control-wizard"></a>オプション、ATL コントロール ウィザード

ウィザードのこのページを使用して作成するコントロールの種類を定義して、インターフェイスのサポートのレベルが含まれます。

## <a name="uielement-list"></a>UIElement の一覧

### <a name="control-type"></a>コントロール型

作成するコントロールの種類。

- **標準コントロール**: ActiveX コントロール。

- **複合コントロール**: ActiveX コントロール (ダイアログ ボックスに似ています) を含めることができる他の ActiveX コントロールまたは Windows のコントロール。 複合コントロールを次のとおりです。

  - 複合コントロールを実装するダイアログ ボックスのテンプレート。

  - カスタム リソースの場合は、レジストリで、呼び出されたときに、複合コントロールを自動的に登録します。

  - 複合コントロールを実装する C++ クラスです。

  - 複合コントロールによって公開される COM インターフェイスです。

  - 複合コントロールを含む HTML テスト ページ。

    既定では、このコントロールの設定[CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly)ウィンドウ付きコントロールであることを示す true にします。 シンクのマップを実装します。 詳細については、次を参照してください。 [DHTML コントロールのサポート](../../atl/atl-support-for-dhtml-controls.md)します。

- **DHTML コントロール**: An ATL DHTML コントロールが HTML を使用して、ユーザー インターフェイスを指定します。 DHTML UI クラスには、COM マップが含まれています。 既定では、このコントロールの設定[CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly)ウィンドウ付きコントロールであることを示す true にします。

   詳細については、次を参照してください。 [DHTML コントロール プロジェクトの要素の識別](../../atl/identifying-the-elements-of-the-dhtml-control-project.md)します。

### <a name="minimal-control"></a>最小限の制御

ほとんどのコンテナーで絶対に必要なインターフェイスのみをサポートしています。 設定できる**最小限の制御**コントロールの種類のいずれかの: 最小限の標準的な制御、最小限の複合コントロールまたは最小限の DHTML コントロールを作成することができます。

### <a name="aggregation"></a>集約

作成するコントロールの集計のサポートを追加します。 詳細については、次を参照してください。[集計](../../atl/aggregation.md)します。

- **[はい]**: 集計が可能なコントロールを作成します。

- **いいえ**: 集計が不可能なコントロールを作成します。

- **のみ**: 集計をのみインスタンス化するコントロールを作成します。

### <a name="threading-model"></a>スレッド モデル

スレッド処理モデルが、コントロールによって使用されることを指定します。

- **1 つ**: コントロールがプライマリ COM スレッドでのみ実行されます。

- **アパートメント**: 任意の 1 つのスレッド アパートメントでコントロールを作成できます。 これが既定値です。

### <a name="interface"></a>Interface

このコントロールがコンテナーに公開するインターフェイスの型。

- **デュアル**: プロパティとメソッドを公開するインターフェイスを作成します。 `IDispatch` 、VTBL を介して直接、します。

- **カスタム**: VTBL によって直接メソッドを公開するインターフェイスを作成します。

   選択した場合**カスタム**、コントロールがあるかを指定することができますし、 **Automation と互換性のある**します。 選択した場合**Automation と互換性のある**、し、ウィザードを追加、 [oleautomation](../../windows/oleautomation.md)属性、IDL でインターフェイスと oleaut32.dll でユニバーサル マーシャラーによってインターフェイスをマーシャ リングすることができます。 参照してください[マーシャ リングの詳細](/windows/desktop/com/marshaling-details)詳細については、Windows SDK に含まれています。

   さらに、選択した場合**Automation と互換性のある**コントロールのすべてのメソッドのすべてのパラメーターはバリアントにする必要がありますし、互換性のあります。

### <a name="support"></a>サポート

コントロールの他のサポートを設定します。

- **接続ポイント**: オブジェクトの接続ポイントからの派生オブジェクトのクラスを作成することにより[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)とソース インターフェイスを公開することができます。

- **ライセンス**: コントロールのサポートが追加[ライセンス](/windows/desktop/com/licensing)します。 クライアント コンピューターに適切なライセンスがある場合にのみ、ライセンスされたコントロールをホストすることができます。

## <a name="see-also"></a>関連項目

[ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)

