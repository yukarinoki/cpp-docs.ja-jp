---
title: ATL COM オブジェクトの基礎 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7873b7006962449a40a8e67d118b6699ac61f263
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762094"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM オブジェクトの基礎

次の図は、クラスおよび ATL COM オブジェクトの定義に使用するインターフェイス間の関係を示しています。

![ATL 構造](../atl/media/vc307y1.gif "vc307y1")

> [!NOTE]
>  この図では`CComObject`から派生`CYourClass`一方`CComAggObject`と`CComPolyObject`含める`CYourClass`メンバー変数として。

ATL COM オブジェクトを定義する 3 つの方法はあります。 標準的なオプションは、使用する、`CComObject`クラスから派生した`CYourClass`します。 2 番目のオプションが集約オブジェクトを使用して作成するには、`CComAggObject`クラス。 3 番目のオプションは、使用する、`CComPolyObject`クラス。 `CComPolyObject` ハイブリッドとして機能します: として機能できます、`CComObject`クラスか、または、`CComAggObject`最初の作成方法によって、クラス。 使用する方法についての詳細、`CComPolyObject`クラスを参照してください[CComPolyObject クラス](../atl/reference/ccompolyobject-class.md)します。

2 つのオブジェクトを使用する標準の ATL COM を使用する場合: 外側のオブジェクトと内部オブジェクト。 外部のクライアント、外側のオブジェクトで定義されているラッパー関数を使用して内部オブジェクトの機能にアクセスします。 外側のオブジェクトが型`CComObject`します。

集約オブジェクトを使用する場合、外側のオブジェクトは、内部オブジェクトの機能のラッパーを提供しません。 代わりに、外側のオブジェクトは、外部クライアントから直接アクセスできるポインターを提供します。 このシナリオでは、外側のオブジェクトの型は`CComAggObject`します。 内部オブジェクトは外側のオブジェクトのメンバー変数と型である`CYourClass`します。

クライアントは、内部オブジェクトと対話する外側のオブジェクトを経由する必要はありません、ため、集約オブジェクトは方が効率的です。 また、外側のオブジェクトはありません集約オブジェクトの機能を認識する集約オブジェクトのインターフェイスは、クライアントに直接使用できます。 ただし、すべてのオブジェクトを集計することができます。 集計オブジェクト、集計を考慮して設計が必要です。

ATL 実装[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)で 2 つのフェーズ。

- [CComObject](../atl/reference/ccomobject-class.md)、 [CComAggObject](../atl/reference/ccomaggobject-class.md)、または[CComPolyObject](../atl/reference/ccompolyobject-class.md)実装、`IUnknown`メソッド。

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)の外側のポインター、参照カウントを管理`IUnknown`します。

ATL COM オブジェクトの他の側面は、他のクラスによって処理されます。

- [CComCoClass](../atl/reference/ccomcoclass-class.md)オブジェクトの既定のクラス ファクトリと集計モデルを定義します。

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md)の既定の実装を提供します、`IDispatch Interface`デュアル インターフェイス オブジェクト上の部分。

- [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md)実装、`ISupportErrorInfo`エラー情報に確実にインターフェイスを正しく呼び出しチェーンの上位伝達できます。

## <a name="in-this-section"></a>このセクションの内容

[CComObjectRootEx の実装](../atl/implementing-ccomobjectrootex.md)  
実装するための COM マップ エントリの例を表示する`CComObjectRootEx`します。

[CComObject、CComAggObject、CComPolyObject の実装](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
について説明しますが、どのように**DECLARE_\*_AGGREGATABLE**マクロの使用に影響`CComObject`、`CComAggObject`と`CComPolyObject`します。

[IDispatch と IErrorInfo のサポート](../atl/supporting-idispatch-and-ierrorinfo.md)  
サポートするために使用する ATL 実装クラスの一覧、`IDispatch`と`IErrorInfo`インターフェイス。

[IDispEventImpl のサポート](../atl/supporting-idispeventimpl.md)  
クラスの接続ポイントを実装する手順について説明します。

[既定のクラス ファクトリと集計モデルの変更](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
使用して、既定のクラス ファクトリと集計モデルを変更するには、どのようなマクロを表示します。

[集計オブジェクトの作成](../atl/creating-an-aggregated-object.md)  
集約オブジェクトを作成する手順を一覧表示します。

## <a name="related-sections"></a>関連項目

[ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)  
ATL COM オブジェクトを作成する方法について説明します。

[ATL](../atl/active-template-library-atl-concepts.md)  
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)

