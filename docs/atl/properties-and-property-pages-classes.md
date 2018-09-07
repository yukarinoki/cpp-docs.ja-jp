---
title: プロパティとプロパティ ページ クラス (ATL) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.properties
dev_langs:
- C++
helpviewer_keywords:
- property pages, classes
- properties [ATL], classes
- properties [ATL]
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c71ca9412c9db86421c586c0602eb8e6548df622
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766754"
---
# <a name="properties-and-property-pages-classes"></a>プロパティとプロパティ ページ クラス

次のクラスは、プロパティやプロパティ ページをサポートします。

- [CComDispatchDriver](../atl/reference/atl-typedefs.md#ccomdispatchdriver)を取得またはオブジェクトのプロパティを設定、`IDispatch`ポインター。

- [CStockPropImpl](../atl/reference/cstockpropimpl-class.md) ATL でサポートされているストック プロパティを実装します。

- [IPerPropertyBrowsingImpl](../atl/reference/iperpropertybrowsingimpl-class.md)オブジェクトのプロパティ ページの情報にアクセスします。

- [IPersistPropertyBagImpl](../atl/reference/ipersistpropertybagimpl-class.md)クライアントが指定したプロパティ バッグ内のオブジェクトのプロパティを格納します。

- [IPropertyPageImpl](../atl/reference/ipropertypageimpl-class.md)プロパティ シート内の特定のプロパティ ページを管理します。

- [IPropertyPage2Impl](../atl/reference/ipropertypage2impl-class.md)と同様に`IPropertyPageImpl`、プロパティ ページで、特定のプロパティを選択するクライアントにもできます。

- [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md)オブジェクトによってサポートされるプロパティ ページの Clsid を取得します。

## <a name="related-articles"></a>関連トピック

[ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)

[ATL COM プロパティ ページ](../atl/atl-com-property-pages.md)

## <a name="see-also"></a>関連項目

[クラスの概要](../atl/atl-class-overview.md)   
[プロパティ マップに関するマクロ](../atl/reference/property-map-macros.md)

