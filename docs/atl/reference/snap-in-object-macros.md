---
description: '詳細情報: Snap-In オブジェクトマクロ'
title: オブジェクトマクロの Snap-In
ms.date: 11/04/2016
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
ms.openlocfilehash: d775c1d5f66f16fb63b9a7adeda2bc8e74046acf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157686"
---
# <a name="snap-in-object-macros"></a>オブジェクトマクロの Snap-In

これらのマクロは、スナップイン拡張機能のサポートを提供します。

|名前|説明|
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Snap-In オブジェクトのスナップイン拡張データクラスマップの開始をマークします。|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Snap-In オブジェクトのツールバーマップの開始をマークします。|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Snap-In オブジェクトのスナップイン拡張データクラスマップの終了をマークします。|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Snap-In オブジェクトのツールバーマップの終了をマークします。|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|スナップイン拡張機能のデータクラスのデータメンバーを作成します。|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|スナップイン拡張データクラスを Snap-In オブジェクトのスナップイン拡張機能データクラスマップに入力します。|
|[SNAPINMENUID](#snapinmenuid)|Snap-In オブジェクトによって使用されるコンテキストメニューの ID を宣言します。|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Snap-In オブジェクトのツールバーマップにツールバーを入力します。|

## <a name="requirements"></a>要件

**ヘッダー:** atlsnap. h

## <a name="begin_extension_snapin_nodeinfo_map"></a><a name="begin_extension_snapin_nodeinfo_map"></a> BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

スナップイン拡張データクラスマップの開始をマークします。

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>パラメーター

*classname*<br/>
からスナップイン拡張データクラスの名前。

### <a name="remarks"></a>解説

BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP マクロを使用してスナップイン拡張機能マップを起動し、各スナップイン拡張データ型のエントリを [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) マクロで追加し、 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) マクロを使用してマップを完了します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="begin_snapintoolbarid_map"></a><a name="begin_snapintoolbarid_map"></a> BEGIN_SNAPINTOOLBARID_MAP

Snap-In オブジェクトのツールバー ID マップの開始を宣言します。

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>パラメーター

*_class*<br/>
からSnap-In オブジェクトクラスを指定します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

## <a name="end_extension_snapin_nodeinfo_map"></a><a name="end_extension_snapin_nodeinfo_map"></a> END_EXTENSION_SNAPIN_NODEINFO_MAP

スナップイン拡張データクラスマップの終了をマークします。

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>解説

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロを使用してスナップイン拡張機能マップを起動し、拡張スナップインの各データ型のエントリを[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロで追加し、END_EXTENSION_SNAPIN_NODEINFO_MAP マクロを使用してマップを完了します。

### <a name="example"></a>例

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)の例を参照してください。

## <a name="end_snapintoolbarid_map"></a><a name="end_snapintoolbarid_map"></a> END_SNAPINTOOLBARID_MAP

Snap-In オブジェクトのツールバー ID マップの終了を宣言します。

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>パラメーター

*_class*<br/>
からSnap-In オブジェクトクラスを指定します。

### <a name="example"></a>例

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)の例を参照してください。

## <a name="extension_snapin_dataclass"></a><a name="extension_snapin_dataclass"></a> EXTENSION_SNAPIN_DATACLASS

**ISnapInItemImpl** 派生クラスのスナップイン拡張データクラスにデータメンバーを追加します。

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>パラメーター

*Microsoft.visualstudio.ordesigner.dataclass.member*<br/>
からスナップイン拡張機能のデータクラス。

### <a name="remarks"></a>解説

このクラスは、スナップイン拡張データクラスマップにも入力する必要があります。 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロを使用してスナップイン拡張データクラスマップを開始し、各スナップイン拡張データ型のエントリを[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロで追加し、 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロを使用してマップを完了します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="extension_snapin_nodeinfo_entry"></a><a name="extension_snapin_nodeinfo_entry"></a> EXTENSION_SNAPIN_NODEINFO_ENTRY

スナップイン拡張機能のデータクラスマップにスナップイン拡張データクラスを追加します。

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>パラメーター

*Microsoft.visualstudio.ordesigner.dataclass.member*<br/>
からスナップイン拡張機能のデータクラス。

### <a name="remarks"></a>解説

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロを使用してスナップイン拡張データクラスマップを開始し、各スナップイン拡張データ型のエントリを EXTENSION_SNAPIN_NODEINFO_ENTRY マクロで追加し、 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロを使用してマップを完了します。

### <a name="example"></a>例

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)の例を参照してください。

## <a name="snapinmenuid"></a><a name="snapinmenuid"></a> SNAPINMENUID

このマクロを使用して、Snap-In オブジェクトのコンテキストメニューリソースを宣言します。

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
からSnap-In オブジェクトのコンテキストメニューを識別します。

## <a name="snapintoolbarid_entry"></a><a name="snapintoolbarid_entry"></a> SNAPINTOOLBARID_ENTRY

このマクロを使用して、Snap-In オブジェクトのツールバー ID マップにツールバー ID を入力します。

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
からツールバーコントロールを識別します。

### <a name="remarks"></a>解説

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)マクロは、ツールバー ID マップの先頭をマークします。[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)マクロは、終了をマークします。

### <a name="example"></a>例

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)の例を参照してください。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
