---
description: '詳細情報: オプション、ATL コントロールウィザード'
title: オプション、ATL コントロール ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.control.options
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
ms.openlocfilehash: 428f6ba1a4bee9cec60ca05b57d66d176c3f0deb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157894"
---
# <a name="options-atl-control-wizard"></a>オプション、ATL コントロール ウィザード

ウィザードのこのページを使用して、作成するコントロールの種類と、それに含まれるインターフェイスのサポートレベルを定義します。

## <a name="uielement-list"></a>UIElement の一覧

### <a name="control-type"></a>コントロール型

作成するコントロールの種類。

- **標準コントロール**: ActiveX コントロール。

- **複合コントロール**: (ダイアログボックスと同様に) 他の activex コントロールまたは Windows コントロールを格納できる activex コントロールです。 複合コントロールには、次のものが含まれます。

  - 複合コントロールを実装するダイアログボックスのテンプレート。

  - カスタムリソースレジストリ。呼び出されると、複合コントロールが自動的に登録されます。

  - 複合コントロールを実装する C++ クラス。

  - 複合コントロールによって公開される COM インターフェイス。

  - 複合コントロールを含む HTML テストページ。

    既定では、このコントロールは [CComControlBase:: m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) を true に設定して、これがウィンドウコントロールであることを示します。 シンクマップを実装します。 詳細については、「 [DHTML コントロールのサポート](../../atl/atl-support-for-dhtml-controls.md)」を参照してください。

- **Dhtml コントロール**: ATL DHTML コントロールは、HTML を使用してユーザーインターフェイスを指定します。 DHTML UI クラスには、COM マップが含まれています。 既定では、このコントロールは [CComControlBase:: m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) を true に設定して、これがウィンドウコントロールであることを示します。

   詳細については、「 [DHTML コントロールプロジェクトの要素の識別](../../atl/identifying-the-elements-of-the-dhtml-control-project.md)」を参照してください。

### <a name="minimal-control"></a>最小制御

では、ほとんどのコンテナーで絶対に必要なインターフェイスのみがサポートされています。 任意のコントロールの種類に対して **最小限のコントロール** を設定できます。最小限の標準コントロール、最小限の複合コントロール、または最小限の DHTML コントロールを作成できます。

### <a name="aggregation"></a>集計

作成するコントロールの集計サポートを追加します。 詳細については、「 [集計](../../atl/aggregation.md)」を参照してください。

- **はい**: 集計可能なコントロールを作成します。

- **いいえ**: 集計できないコントロールを作成します。

- **のみ**: 集計によってのみインスタンス化できるコントロールを作成します。

### <a name="threading-model"></a>スレッド モデル

コントロールによって使用されるスレッドモデルを指定します。

- **Single**: コントロールは、プライマリ COM スレッドでのみ実行されます。

- **アパートメント**: コントロールは、任意の1つのスレッドアパートメントで作成できます。 これが既定値です。

### <a name="interface"></a>インターフェイス

このコントロールがコンテナーに公開するインターフェイスの型。

- **Dual**: VTBL を通じて、または直接、プロパティとメソッドを公開するインターフェイスを作成し `IDispatch` ます。

- **Custom**: VTBL を通じて直接メソッドを公開するインターフェイスを作成します。

   [ **カスタム**] を選択した場合は、コントロールが **オートメーションと互換性** があることを指定できます。 [ **オートメーション互換**] を選択すると、ウィザードによって [OLEAUTOMATION](../../windows/attributes/oleautomation.md) 属性が IDL のインターフェイスに追加されます。このインターフェイスは oleaut32.dll のユニバーサルマーシャラーによってマーシャリングできます。 詳細については、Windows SDK の「 [マーシャリングの詳細](/windows/win32/com/marshaling-details) 」を参照してください。

   また、[ **オートメーション互換**] を選択した場合は、コントロール内のすべてのメソッドのすべてのパラメーターがバリアント互換である必要があります。

### <a name="support"></a>サポート

コントロールの追加のその他のサポートを設定します。

- **コネクションポイント**: オブジェクトのクラスを [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) から派生させ、ソースインターフェイスを公開できるようにすることで、オブジェクトの接続ポイントを有効にします。

- **ライセンス** 済み: [ライセンス](/windows/win32/com/licensing)のコントロールにサポートを追加します。 ライセンスされたコントロールは、クライアントコンピューターに正しいライセンスがある場合にのみホストできます。

## <a name="see-also"></a>関連項目

[ATL コントロールウィザード](../../atl/reference/atl-control-wizard.md)
