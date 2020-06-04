---
title: スナップイン オブジェクト マクロ
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
ms.openlocfilehash: 6a57cdb3c9b6a4448bc954ff754ac9b18fa0b393
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325855"
---
# <a name="snap-in-object-macros"></a>スナップイン オブジェクト マクロ

これらのマクロは、スナップイン拡張機能をサポートします。

|||
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|スナップイン オブジェクトのスナップイン拡張データ クラス マップの先頭を示します。|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|スナップイン オブジェクトのツール バー マップの先頭をマークします。|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|スナップイン オブジェクトのスナップイン拡張データ クラス マップの末尾をマークします。|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|スナップイン オブジェクトのツール バー マップの終わりを示します。|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|スナップイン拡張機能のデータ クラスのデータ メンバーを作成します。|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|スナップイン拡張データ クラスをスナップイン オブジェクトのスナップイン拡張データ クラス マップに入力します。|
|[スナップインメニュー ID](#snapinmenuid)|スナップイン オブジェクトで使用されるコンテキスト メニューの ID を宣言します。|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|スナップイン オブジェクトのツール バー マップにツールバーを入力します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsnap.h

## <a name="begin_extension_snapin_nodeinfo_map"></a><a name="begin_extension_snapin_nodeinfo_map"></a>BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

スナップイン拡張データ クラス マップの先頭を示します。

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
[in]スナップイン拡張データ クラスの名前。

### <a name="remarks"></a>解説

BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP マクロを使用してスナップイン拡張マップを開始し[、EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロを使用してスナップイン拡張データ型ごとにエントリを追加し[、END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロを使用してマップを完成させます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="begin_snapintoolbarid_map"></a><a name="begin_snapintoolbarid_map"></a>BEGIN_SNAPINTOOLBARID_MAP

スナップイン オブジェクトのツール バー ID マップの先頭を宣言します。

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>パラメーター

*_class*<br/>
[in]スナップイン オブジェクト クラスを指定します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

## <a name="end_extension_snapin_nodeinfo_map"></a><a name="end_extension_snapin_nodeinfo_map"></a>END_EXTENSION_SNAPIN_NODEINFO_MAP

スナップイン拡張データ クラス マップの終了をマークします。

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>解説

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロを使用してスナップイン拡張マップを開始し[、EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロを使用して各拡張スナップイン データ型のエントリを追加し、END_EXTENSION_SNAPIN_NODEINFO_MAP マクロを使用してマップを完成させます。

### <a name="example"></a>例

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)の例を参照してください。

## <a name="end_snapintoolbarid_map"></a><a name="end_snapintoolbarid_map"></a>END_SNAPINTOOLBARID_MAP

スナップイン オブジェクトのツール バー ID マップの末尾を宣言します。

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>パラメーター

*_class*<br/>
[in]スナップイン オブジェクト クラスを指定します。

### <a name="example"></a>例

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)の例を参照してください。

## <a name="extension_snapin_dataclass"></a><a name="extension_snapin_dataclass"></a>EXTENSION_SNAPIN_DATACLASS

**ISnapInItemImpl**派生クラスのスナップイン拡張データ クラスにデータ メンバーを追加します。

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>パラメーター

*データクラス*<br/>
[in]スナップイン拡張機能のデータ クラス。

### <a name="remarks"></a>解説

このクラスは、スナップイン拡張データ クラス マップにも入力する必要があります。 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロを使用してスナップイン拡張データ クラス マップを起動し[、EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)マクロを使用してスナップイン拡張データ型ごとにエントリを追加し[、END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロを使用してマップを完成させます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="extension_snapin_nodeinfo_entry"></a><a name="extension_snapin_nodeinfo_entry"></a>EXTENSION_SNAPIN_NODEINFO_ENTRY

スナップイン拡張データ クラス をスナップイン拡張データ クラス マップに追加します。

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>パラメーター

*データクラス*<br/>
[in]スナップイン拡張機能のデータ クラス。

### <a name="remarks"></a>解説

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)マクロを使用してスナップイン拡張データ クラス マップを起動し、EXTENSION_SNAPIN_NODEINFO_ENTRY マクロを使用してスナップイン拡張データ型ごとにエントリを追加し[、END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)マクロを使用してマップを完成させます。

### <a name="example"></a>例

[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)の例を参照してください。

## <a name="snapinmenuid"></a><a name="snapinmenuid"></a>スナップインメニュー ID

このマクロを使用して、Snap-In オブジェクトのコンテキスト メニュー リソースを宣言します。

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]スナップイン オブジェクトのコンテキスト メニューを識別します。

## <a name="snapintoolbarid_entry"></a><a name="snapintoolbarid_entry"></a>SNAPINTOOLBARID_ENTRY

このマクロを使用して、スナップイン オブジェクトのツール バー ID マップにツールバー ID を入力します。

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]ツール バー コントロールを識別します。

### <a name="remarks"></a>解説

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)マクロは、ツールバー ID マップの先頭を示します。[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)マクロは終了をマークします。

### <a name="example"></a>例

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)の例を参照してください。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
