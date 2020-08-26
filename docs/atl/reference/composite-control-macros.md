---
title: 複合コントロールマクロ
ms.date: 05/06/2019
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
ms.openlocfilehash: 7ac13a11646faca53b38ec610dc0388bdd14d251
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833544"
---
# <a name="composite-control-macros"></a>複合コントロールマクロ

これらのマクロは、イベントシンクマップとエントリを定義します。

|マクロ|説明|
|-|-|
|[BEGIN_SINK_MAP](#begin_sink_map)|複合コントロールのイベントシンクマップの開始をマークします。|
|[END_SINK_MAP](#end_sink_map)|複合コントロールのイベントシンクマップの終了をマークします。|
|[SINK_ENTRY](#sink_entry)|イベントシンクマップへのエントリ。|
|[SINK_ENTRY_EX](#sink_entry_ex)|追加のパラメーターを持つイベントシンクマップへのエントリ。|
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017)SINK_ENTRY_EX に似ていますが、iid へのポインターを受け取る点が異なります。|
|[SINK_ENTRY_INFO](#sink_entry_info)|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)で使用するために手動で指定された型情報を持つイベントシンクマップへのエントリ。|
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017)SINK_ENTRY_INFO に似ていますが、iid へのポインターを受け取る点が異なります。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

## <a name="begin_sink_map"></a><a name="begin_sink_map"></a> BEGIN_SINK_MAP

複合コントロールのイベントシンクマップの開始を宣言します。

```
BEGIN_SINK_MAP(_class)
```

### <a name="parameters"></a>パラメーター

*_class*<br/>
からコントロールを指定します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>解説

CE ATL の ActiveX イベントシンクの実装では、イベントハンドラーメソッドから HRESULT 型または void 型の戻り値のみがサポートされます。その他の戻り値はサポートされておらず、その動作は未定義です。

## <a name="end_sink_map"></a><a name="end_sink_map"></a> END_SINK_MAP

複合コントロールのイベントシンクマップの終了を宣言します。

```
END_SINK_MAP()
```

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>解説

CE ATL の ActiveX イベントシンクの実装では、イベントハンドラーメソッドから HRESULT 型または void 型の戻り値のみがサポートされます。その他の戻り値はサポートされておらず、その動作は未定義です。

## <a name="sink_entry"></a><a name="sink_entry"></a> SINK_ENTRY

*Id*で識別されるコントロールの、指定されたイベント (*dispid*) のハンドラー関数 (*fn*) を宣言します。

```
SINK_ENTRY( id, dispid, fn )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
からコントロールを識別します。

*dispid*<br/>
から指定されたイベントを識別します。

*1億*<br/>
からイベントハンドラー関数の名前。 この関数は、 `_stdcall` 呼び出し規約を使用し、適切なディスパッチインターフェイススタイルのシグネチャを持つ必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>解説

CE ATL の ActiveX イベントシンクの実装では、イベントハンドラーメソッドから HRESULT 型または void 型の戻り値のみがサポートされます。その他の戻り値はサポートされておらず、その動作は未定義です。

## <a name="sink_entry_ex-and-sink_entry_ex_p"></a><a name="sink_entry_ex"></a> SINK_ENTRY_EX と SINK_ENTRY_EX_P

*Id*で識別されるコントロールのディスパッチインターフェイス (*iid*) の、指定されたイベント (*dispid*) のハンドラー関数 (*fn*) を宣言します。

```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*id*<br/>
からコントロールを識別します。

*iid*<br/>
からディスパッチインターフェイスを識別します。

*piid*<br/>
からディスパッチインターフェイスへのポインター。

*dispid*<br/>
から指定されたイベントを識別します。

*1億*<br/>
からイベントハンドラー関数の名前。 この関数は、 `_stdcall` 呼び出し規約を使用し、適切なディスパッチインターフェイススタイルのシグネチャを持つ必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]

### <a name="remarks"></a>解説

CE ATL の ActiveX イベントシンクの実装では、イベントハンドラーメソッドから HRESULT 型または void 型の戻り値のみがサポートされます。その他の戻り値はサポートされておらず、その動作は未定義です。

## <a name="sink_entry_info-and-sink_entry_info_p"></a><a name="sink_entry_info"></a> SINK_ENTRY_INFO と SINK_ENTRY_INFO_P

イベントシンクマップ内の SINK_ENTRY_INFO マクロを使用して、 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) が関連するハンドラー関数にイベントをルーティングするために必要な情報を提供します。

```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*id*<br/>
からイベントソースを識別する符号なし整数。 この値は、関連する[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)基本クラスで使用される*nID*テンプレートパラメーターと一致している必要があります。

*iid*<br/>
からディスパッチインターフェイスを識別する IID。

*piid*<br/>
からディスパッチインターフェイスを識別する IID へのポインター。

*dispid*<br/>
から指定されたイベントを識別する DISPID。

*1億*<br/>
からイベントハンドラー関数の名前。 この関数は、 `_stdcall` 呼び出し規約を使用し、適切なディスパッチインターフェイススタイルのシグネチャを持つ必要があります。

*info*<br/>
からイベントハンドラー関数の型情報。 この型情報は、構造体へのポインターの形式で提供され `_ATL_FUNC_INFO` ます。 CC_CDECL は、構造体の CALLCONV フィールドの Windows CE でサポートされている唯一のオプションです `_ATL_FUNC_INFO` 。 その他の値はサポートされていないため、動作は定義されていません。

### <a name="remarks"></a>解説

最初の4つのマクロパラメーターは、 [SINK_ENTRY_EX](#sink_entry_ex) マクロのパラメーターと同じです。 最後のパラメーターは、イベントの型情報を提供します。 CE ATL の ActiveX イベントシンクの実装では、イベントハンドラーメソッドから HRESULT 型または void 型の戻り値のみがサポートされます。その他の戻り値はサポートされておらず、その動作は未定義です。

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)<br/>
[複合コントロールのグローバル関数](../../atl/reference/composite-control-global-functions.md)
