---
title: ATL COM オブジェクトの基礎
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: 651413534ed44143e2a0fdaf00bdabd6e5d57010
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319556"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM オブジェクトの基礎

次の図は、ATL COM オブジェクトの定義に使用されるクラスとインターフェイスの間の関係を示しています。

![ATL構造](../atl/media/vc307y1.gif "ATL 構造")

> [!NOTE]
> この図は、`CComObject`メンバー変数として`CYourClass`、`CComAggObject`一`CComPolyObject`方`CYourClass`で、から派生し、含まれているを示しています。

ATL COM オブジェクトを定義するには、3 つの方法があります。 標準オプションは、 から`CComObject``CYourClass`派生したクラスを使用することです。 2 番目のオプションは、クラスを使用して集約オブジェクト`CComAggObject`を作成することです。 3 番目のオプションは、`CComPolyObject`クラスを使用することです。 `CComPolyObject`ハイブリッドとして機能します: 最初に`CComObject`作成する方法に応じて`CComAggObject`、クラスまたはクラスとして機能します。 `CComPolyObject`クラスの使用方法の詳細については、「 [CComPolyObject クラス](../atl/reference/ccompolyobject-class.md)」を参照してください。

標準 ATL COM を使用する場合は、外側のオブジェクトと内部オブジェクトの 2 つのオブジェクトを使用します。 外部クライアントは、外部オブジェクトで定義されているラッパー関数を通じて内部オブジェクトの機能にアクセスします。 外側のオブジェクトの型`CComObject`は です。

集約オブジェクトを使用する場合、外部オブジェクトは内部オブジェクトの機能のラッパーを提供しません。 代わりに、外部オブジェクトは、外部クライアントから直接アクセスされるポインターを提供します。 このシナリオでは、外側のオブジェクトは 型`CComAggObject`です。 内部オブジェクトは外部オブジェクトのメンバー変数で、型`CYourClass`です。

クライアントは内部オブジェクトと対話するために外部オブジェクトを経由する必要がないため、通常は集約されたオブジェクトの方が効率的です。 また、集約オブジェクトのインターフェイスがクライアントから直接使用できることを考えると、外部オブジェクトは集約オブジェクトの機能を認識する必要はありません。 ただし、すべてのオブジェクトを集約できるわけではありません。 集約されるオブジェクトは、集約を念頭に置いて設計する必要があります。

ATL は、次の 2 つのフェーズで[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)を実装します。

- [メソッドを](../atl/reference/ccomobject-class.md)実装します[CComAggObject](../atl/reference/ccomaggobject-class.md)。 [CComPolyObject](../atl/reference/ccompolyobject-class.md) `IUnknown`

- [の](../atl/reference/ccomobjectroot-class.md)参照カウントと外部ポインター[を管理します](../atl/reference/ccomobjectrootex-class.md)`IUnknown`。

ATL COM オブジェクトのその他の側面は、他のクラスによって処理されます。

- [CComCoClass は](../atl/reference/ccomcoclass-class.md)、オブジェクトの既定のクラス ファクトリと集計モデルを定義します。

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md)は、オブジェクト上の`IDispatch Interface`任意のデュアル インターフェイスの部分の既定の実装を提供します。

- [エラー](../atl/reference/isupporterrorinfoimpl-class.md)情報を呼び出しチェーン`ISupportErrorInfo`に正しく伝達できるインターフェイスを実装します。

## <a name="in-this-section"></a>このセクションの内容

[CComObjectRootEx の実装](../atl/implementing-ccomobjectrootex.md)<br/>
実装`CComObjectRootEx`用の COM マップ エントリの例を示します。

[CComObject、CComAggObject、CComPolyObject の実装](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
**DECLARE__AGGREGATABLE\*** マクロが 、 `CComAggObject`、`CComPolyObject`および`CComObject`の使用に与える影響について説明します。

[IDispatch と IErrorInfo のサポート](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
インターフェイスのサポートに使用する ATL 実装`IDispatch`クラス`IErrorInfo`を一覧表示します。

[IDispEventImpl のサポート](../atl/supporting-idispeventimpl.md)<br/>
クラスのコネクション ポイントを実装する手順について説明します。

[既定のクラス ファクトリと集計モデルの変更](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
既定のクラス ファクトリと集計モデルを変更するために使用するマクロを表示します。

[集約オブジェクトの作成](../atl/creating-an-aggregated-object.md)<br/>
集約オブジェクトを作成する手順を示します。

## <a name="related-sections"></a>関連項目

[ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)<br/>
ATL COM オブジェクトの作成について説明します。

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)
