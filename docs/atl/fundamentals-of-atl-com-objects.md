---
title: ATL COM オブジェクトの基本 |Microsoft ドキュメント
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
ms.openlocfilehash: 955f8f6be96feeaf0f22f02c125dcdeaceb8e7f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358292"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM オブジェクトの基本事項
次の図は、クラスと ATL COM オブジェクトの定義に使用されるインターフェイス間の関係を示しています。  
  
 ![ATL 構造](../atl/media/vc307y1.gif "vc307y1")  
  
> [!NOTE]
>  この図では`CComObject`から派生した`CYourClass`一方`CComAggObject`と`CComPolyObject`含める`CYourClass`メンバー変数とします。  
  
 ATL COM オブジェクトを定義する 3 つの方法はあります。 標準のオプションは使用する、`CComObject`クラスから派生する`CYourClass`です。 2 番目のオプションを使用して集約オブジェクトを作成する、`CComAggObject`クラスです。 3 番目のオプションは、使用する、`CComPolyObject`クラスです。 `CComPolyObject` ハイブリッドの役割を果たします: として機能できます、`CComObject`クラスか、または、`CComAggObject`最初の作成方法に応じて、クラスです。 使用する方法についての詳細、`CComPolyObject`クラスを参照してください[CComPolyObject クラス](../atl/reference/ccompolyobject-class.md)です。  
  
 2 つのオブジェクトを使用する標準の ATL COM を使用する場合: 外部オブジェクトと、内部オブジェクトです。 外部クライアント、外部オブジェクトで定義されているラッパー関数を使用して内部オブジェクトの機能にアクセスします。 外部オブジェクトの型が`CComObject`です。  
  
 集約オブジェクトを使用する場合、外部オブジェクトは、内部オブジェクトの機能のラッパーを提供しません。 代わりに、外側のオブジェクトは、外部クライアントがアクセスして直接のポインターを提供します。 このシナリオで、外部オブジェクトは、型の`CComAggObject`します。 内部オブジェクトは、外部のオブジェクトのメンバー変数と型である`CYourClass`です。  
  
 クライアントは、内部オブジェクトと対話する外部のオブジェクトを通過する必要はありません、ため集約オブジェクトは通常はより効率的です。 また、外部のオブジェクトはありません集約オブジェクトの機能を認識する集約オブジェクトのインターフェイスはクライアントで直接利用できること。 ただし、すべてのオブジェクトを集計できます。 集計されるオブジェクトは、集約ことに注意を設計する必要があります。  
  
 ATL を実装する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 2 つのフェーズで。  
  
-   [CComObject](../atl/reference/ccomobject-class.md)、[すると](../atl/reference/ccomaggobject-class.md)、または[CComPolyObject](../atl/reference/ccompolyobject-class.md)を実装する、 **IUnknown**メソッドです。  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)の外側のポインター、参照カウントを管理する**IUnknown**です。  
  
 ATL COM オブジェクトの他の側面は、他のクラスによって処理されます。  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md)オブジェクトの既定のクラス ファクトリと集計モデルを定義します。  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md)の既定の実装を提供、`IDispatch Interface`デュアル インターフェイス オブジェクト上の部分です。  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md)を実装する、 **ISupportErrorInfo**インターフェイスにより、エラー情報を呼び出しチェーンを正しく反映させることができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [CComObjectRootEx の実装](../atl/implementing-ccomobjectrootex.md)  
 実装するための COM マップ エントリの例を示します`CComObjectRootEx`です。  
  
 [CComObject、CComAggObject、CComPolyObject の実装](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 について説明しますが、どのように**DECLARE_\*_AGGREGATABLE**マクロの使用に影響`CComObject`、 `CComAggObject`、および`CComPolyObject`です。  
  
 [IDispatch と IErrorInfo のサポート](../atl/supporting-idispatch-and-ierrorinfo.md)  
 クラスの一覧、ATL の実装をサポートするために使用する、`IDispatch`と**IErrorInfo**インターフェイスです。  
  
 [IDispEventImpl のサポート](../atl/supporting-idispeventimpl.md)  
 クラスのコネクション ポイントを実装する手順について説明します。  
  
 [既定のクラス ファクトリと集計モデルの変更](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 使用して、既定のクラス ファクトリと集計モデルを変更するには、どのようなマクロを表示します。  
  
 [集計オブジェクトの作成](../atl/creating-an-aggregated-object.md)  
 集約オブジェクトを作成するための手順を一覧表示します。  
  
## <a name="related-sections"></a>関連項目  
 [ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)  
 ATL COM オブジェクトを作成する方法についてを説明します。  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。  
  
## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)

