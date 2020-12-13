---
description: '詳細情報: ATL COM オブジェクトの基礎'
title: ATL COM オブジェクトの基礎
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: 0a94d57701770b00eb2c2d5aed675b8cc19e9e58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152937"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM オブジェクトの基礎

次の図は、ATL COM オブジェクトの定義に使用されるクラスとインターフェイスの関係を示しています。

![ATL 構造体](../atl/media/vc307y1.gif "ATL 構造")

> [!NOTE]
> この図 `CComObject` は、がから派生 `CYourClass` `CComAggObject` し、 `CComPolyObject` `CYourClass` メンバー変数として含まれていることを示しています。

ATL COM オブジェクトを定義するには、次の3つの方法があります。 標準オプションでは、 `CComObject` から派生したクラスを使用し `CYourClass` ます。 2つ目の方法では、クラスを使用して集計オブジェクトを作成し `CComAggObject` ます。 3番目のオプションは、クラスを使用することです `CComPolyObject` 。 `CComPolyObject` ハイブリッドとして機能します。 `CComObject` `CComAggObject` 最初の作成方法に応じて、クラスまたはクラスとして機能できます。 クラスの使用方法の詳細については `CComPolyObject` 、「 [CComPolyObject クラス](../atl/reference/ccompolyobject-class.md)」を参照してください。

標準の ATL COM を使用する場合は、外部オブジェクトと内部オブジェクトという2つのオブジェクトを使用します。 外部クライアントは、外側のオブジェクトで定義されているラッパー関数を介して、内部オブジェクトの機能にアクセスします。 外側のオブジェクトの型は `CComObject` です。

集計されたオブジェクトを使用する場合、外側のオブジェクトは内部オブジェクトの機能のラッパーを提供しません。 外部のオブジェクトは、外部クライアントによって直接アクセスされるポインターを提供します。 このシナリオでは、外側のオブジェクトの型は `CComAggObject` です。 内部オブジェクトは、外部オブジェクトのメンバー変数であり、型 `CYourClass` です。

内部オブジェクトを操作するために、クライアントが外部オブジェクトを経由する必要がないため、通常、集計されたオブジェクトはより効率的です。 また、集約されたオブジェクトのインターフェイスをクライアントが直接使用できるようにすると、外側のオブジェクトは集約されたオブジェクトの機能を知る必要がありません。 ただし、すべてのオブジェクトを集計することはできません。 オブジェクトを集計するには、集計を念頭に置いて設計する必要があります。

ATL は、次の2つのフェーズで [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) を実装します。

- [CComObject](../atl/reference/ccomobject-class.md)、 [CComAggObject](../atl/reference/ccomaggobject-class.md)、または [CComPolyObject](../atl/reference/ccompolyobject-class.md) は、メソッドを実装し `IUnknown` ます。

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) または [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) は、の参照カウントと外部ポインターを管理 `IUnknown` します。

ATL COM オブジェクトのその他の側面は、他のクラスによって処理されます。

- [CComCoClass](../atl/reference/ccomcoclass-class.md) は、オブジェクトの既定のクラスファクトリと集計モデルを定義します。

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) は `IDispatch Interface` 、オブジェクトの任意のデュアルインターフェイスの部分の既定の実装を提供します。

- [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) は、 `ISupportErrorInfo` エラー情報を呼び出しチェーンに正しく反映できるようにするインターフェイスを実装します。

## <a name="in-this-section"></a>このセクションの内容

[CComObjectRootEx の実装](../atl/implementing-ccomobjectrootex.md)<br/>
を実装するための COM マップエントリの例を示し `CComObjectRootEx` ます。

[CComObject、CComAggObject、CComPolyObject の実装](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
**DECLARE_ \* _AGGREGATABLE** マクロが、、およびの使用にどのように影響するかについて説明 `CComObject` `CComAggObject` `CComPolyObject` します。

[IDispatch と IErrorInfo のサポート](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
およびインターフェイスをサポートするために使用する ATL 実装クラスの一覧を示し `IDispatch` `IErrorInfo` ます。

[IDispEventImpl のサポート](../atl/supporting-idispeventimpl.md)<br/>
クラスの接続ポイントを実装する手順について説明します。

[既定のクラスファクトリと集計モデルの変更](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
既定のクラスファクトリと集計モデルを変更するために使用するマクロを表示します。

[集計オブジェクトの作成](../atl/creating-an-aggregated-object.md)<br/>
集計されたオブジェクトを作成する手順を示します。

## <a name="related-sections"></a>関連項目

[ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)<br/>
ATL COM オブジェクトの作成に関する情報を提供します。

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)
