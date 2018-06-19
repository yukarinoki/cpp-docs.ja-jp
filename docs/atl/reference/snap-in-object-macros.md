---
title: スナップイン オブジェクト マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
dev_langs:
- C++
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba8a335bbe5424ca04f1db03a3f3ac4bf3cfa9ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363911"
---
# <a name="snap-in-object-macros"></a>スナップイン オブジェクト マクロ
これらのマクロは、スナップインの拡張機能のサポートを提供します。  
  
|||  
|-|-|  
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|スナップインでオブジェクトのスナップイン拡張データ クラスのマップの先頭を示します。|  
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|スナップインでオブジェクトのツールバーのマップの先頭をマークします。|  
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|スナップイン拡張クラスのデータ マップのスナップインでオブジェクトの末尾をマークします。|  
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|スナップインでオブジェクトのツールバーのマップの最後をマークします。|  
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|スナップイン拡張機能のデータ クラスのデータ メンバーを作成します。|  
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|スナップインでオブジェクトのスナップイン拡張データ クラスのマップにスナップイン拡張データ クラスを入力します。|  
|[SNAPINMENUID](#snapinmenuid)|スナップインでオブジェクトによって使用されるコンテキスト メニューの ID を宣言します。|  
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|スナップインでオブジェクトのツールバーのマップにツールバーを入力します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlsnap.h 
   
##  <a name="begin_extension_snapin_nodeinfo_map"></a>  BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP  
 スナップイン拡張データ クラスのマップの先頭を示します。  
  
```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```  
  
### <a name="parameters"></a>パラメーター  
 *classname*  
 [in]スナップイン拡張データ クラスの名前。  
  
### <a name="remarks"></a>コメント  
 スナップイン拡張マップを開始、`BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP`マクロ、スナップイン拡張データ型と型の各エントリを追加、 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロでマップを完了し、 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="begin_snapintoolbarid_map"></a>  BEGIN_SNAPINTOOLBARID_MAP  
 マップの先頭、ツールバー ID のスナップインでオブジェクトを宣言します。  
  
```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```  
  
### <a name="parameters"></a>パラメーター  
 `_class`  
 [in]スナップイン オブジェクト クラスを指定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]  
  
##  <a name="end_extension_snapin_nodeinfo_map"></a>  END_EXTENSION_SNAPIN_NODEINFO_MAP  
 データ クラスのマップのスナップイン拡張の末尾をマークします。  
  
```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```  
  
### <a name="remarks"></a>コメント  
 拡張スナップインでマップを開始、 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロ、拡張スナップインでデータの種類とそれぞれのエントリを追加、 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロマップを完了し、`END_EXTENSION_SNAPIN_NODEINFO_MAP`マクロです。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)です。  
  
##  <a name="end_snapintoolbarid_map"></a>  END_SNAPINTOOLBARID_MAP  
 マップの最後、ツールバー ID のスナップインでオブジェクトを宣言します。  
  
```
END_SNAPINTOOLBARID_MAP( _class )
```  
  
### <a name="parameters"></a>パラメーター  
 `_class`  
 [in]スナップイン オブジェクト クラスを指定します。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)です。  
  
##  <a name="extension_snapin_dataclass"></a>  EXTENSION_SNAPIN_DATACLASS  
 スナップイン拡張データ クラスにデータ メンバーを追加、 **ISnapInItemImpl**-クラスを派生します。  
  
```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```  
  
### <a name="parameters"></a>パラメーター  
 `dataClass`  
 [in]データ クラスのスナップイン拡張します。  
  
### <a name="remarks"></a>コメント  
 このクラスは、スナップイン拡張データのクラスのマップにも入力する必要があります。 スナップイン拡張データ クラス マップを開始、 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロ、スナップイン拡張データ型と型の各エントリを追加、 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロでマップを完了し、 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="extension_snapin_nodeinfo_entry"></a>  EXTENSION_SNAPIN_NODEINFO_ENTRY  
 データ クラスのマップのスナップイン拡張にスナップイン拡張データ クラスを追加します。  
  
```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```  
  
### <a name="parameters"></a>パラメーター  
 `dataClass`  
 [in]データ クラスのスナップイン拡張します。  
  
### <a name="remarks"></a>コメント  
 スナップイン拡張データ クラス マップを開始、 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロ、スナップイン拡張データ型と型の各エントリを追加、`EXTENSION_SNAPIN_NODEINFO_ENTRY`マクロ、でマップを完了し、[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロです。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)です。  
  
##  <a name="snapinmenuid"></a>  SNAPINMENUID  
 このマクロを使用すると、スナップイン オブジェクトのコンテキスト メニュー リソースを宣言できます。  
  
```
SNAPINMENUID( id )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]スナップインでオブジェクトのコンテキスト メニューを識別します。  
  
##  <a name="snapintoolbarid_entry"></a>  SNAPINTOOLBARID_ENTRY  
 このマクロを使用すると、スナップイン オブジェクトのツールバー ID マップにツールバー ID を入力します。  
  
```
SNAPINTOOLBARID_ENTRY( id )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]ツール バー コントロールを識別します。  
  
### <a name="remarks"></a>コメント  
 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)マクロは、ツールバー ID マップの開始をマーク; [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)マクロは、終了を示します。  
  
### <a name="example"></a>例  
 例を参照して[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)です。  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
