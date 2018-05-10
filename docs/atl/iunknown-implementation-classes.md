---
title: IUnknown の実装クラス (ATL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.Iunknown
dev_langs:
- C++
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d67b2a7b9769acd7d6e596e4fcdf1aec30bbf74
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="iunknown-implementation-classes"></a>IUnknown の実装クラス
次のクラスを実装**IUnknown**とメソッドの関連。  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)集計と非集計の両方のオブジェクトに対する参照カウントを管理します。 スレッド処理モデルを指定できます。  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md)集計と非集計の両方のオブジェクトに対する参照カウントを管理します。 既定のサーバーのモデルのスレッドを使用します。  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) Implements **IUnknown**集約オブジェクト。  
  
-   [CComObject](../atl/reference/ccomobject-class.md) Implements **IUnknown**非集約オブジェクト。  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) Implements **IUnknown**集計および非集約オブジェクト。 使用して`CComPolyObject`両方はなくなります`CComAggObject`と`CComObject`モジュールでします。 1 つ`CComPolyObject`オブジェクトは、集計と非集計の両方のケースを処理します。  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) Implements **IUnknown**モジュールのロック カウントを変更することがなく、非集約オブジェクト。  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) Implements **IUnknown**ティアオフ インターフェイスです。  
  
-   [ティアオフ](../atl/reference/ccomcachedtearoffobject-class.md)Implements **IUnknown** 「キャッシュされた」ティアオフ インターフェイスです。  
  
-   [した](../atl/reference/ccomcontainedobject-class.md)Implements **IUnknown**の集計またはティアオフ インターフェイスの内部オブジェクトです。  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md)管理オブジェクトを確認するモジュールの参照カウントは削除されません。  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md)のスケルトンの実装を使用して、一時的な COM オブジェクトを作成**IUnknown**です。  
  
## <a name="related-articles"></a>関連トピック  
 [ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../atl/atl-class-overview.md)   
 [集計とクラス ファクトリ マクロ](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM マップ マクロ](../atl/reference/com-map-macros.md)   
 [COM マップに関するグローバル関数](../atl/reference/com-map-global-functions.md)

