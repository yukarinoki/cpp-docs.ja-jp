---
title: 複合コントロール マクロ
ms.date: 05/06/2019
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
ms.openlocfilehash: 67ad18c07a92cfecca44667908a8488e8c2da234
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331518"
---
# <a name="composite-control-macros"></a>複合コントロール マクロ

これらのマクロは、イベント シンク マップとエントリを定義します。

|||
|-|-|
|[BEGIN_SINK_MAP](#begin_sink_map)|複合コントロールのイベント シンク マップの先頭をマークします。|
|[END_SINK_MAP](#end_sink_map)|複合コントロールのイベント シンク マップの終了をマークします。|
|[SINK_ENTRY](#sink_entry)|イベント シンク マップへのエントリ。|
|[SINK_ENTRY_EX](#sink_entry_ex)|追加のパラメーターを使用してイベント シンク マップへのエントリ。|
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (ビジュアルスタジオ2017)SINK_ENTRY_EX似ていますが、iid へのポインタを受け取る点が異なっています。|
|[SINK_ENTRY_INFO](#sink_entry_info)|イベント シンクへのエントリは、手動で指定された型情報を使用して[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)で使用するためのマップを作成します。|
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (ビジュアルスタジオ2017)iid へのポインターを受け取ることを除いて、SINK_ENTRY_INFOに似ています。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="begin_sink_map"></a><a name="begin_sink_map"></a>BEGIN_SINK_MAP

複合コントロールのイベント シンク マップの先頭を宣言します。

```
BEGIN_SINK_MAP(_class)
```

### <a name="parameters"></a>パラメーター

*_class*<br/>
[in]コントロールを指定します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>解説

ActiveX イベント シンクの CE ATL 実装では、イベント ハンドラー メソッドからの型 HRESULT または void の戻り値のみがサポートされます。その他の戻り値はサポートされず、その動作は未定義です。

## <a name="end_sink_map"></a><a name="end_sink_map"></a>END_SINK_MAP

複合コントロールのイベント シンク マップの終了を宣言します。

```
END_SINK_MAP()
```

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>解説

ActiveX イベント シンクの CE ATL 実装では、イベント ハンドラー メソッドからの型 HRESULT または void の戻り値のみがサポートされます。その他の戻り値はサポートされず、その動作は未定義です。

## <a name="sink_entry"></a><a name="sink_entry"></a>SINK_ENTRY

*id*で識別されるコントロールの指定されたイベント (*dispid*) のハンドラ関数 (*fn*) を宣言します。

```
SINK_ENTRY( id, dispid, fn )
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]コントロールを識別します。

*Dispid*<br/>
[in]指定したイベントを識別します。

*Fn*<br/>
[in]イベント ハンドラー関数の名前。 この関数は、呼`_stdcall`び出し規約を使用し、適切な dispinterface スタイルのシグネチャを持つ必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>解説

ActiveX イベント シンクの CE ATL 実装では、イベント ハンドラー メソッドからの型 HRESULT または void の戻り値のみがサポートされます。その他の戻り値はサポートされず、その動作は未定義です。

## <a name="sink_entry_ex-and-sink_entry_ex_p"></a><a name="sink_entry_ex"></a>SINK_ENTRY_EXとSINK_ENTRY_EX_P

*id*で識別されるコントロールのディスパッチ インターフェイス (*iid*) の指定されたイベント (*dispid*) のハンドラ関数 (*fn*) を宣言します。

```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]コントロールを識別します。

*Iid*<br/>
[in]ディスパッチ インターフェイスを識別します。

*ピッド*<br/>
[in]ディスパッチ インターフェイスへのポインター。

*Dispid*<br/>
[in]指定したイベントを識別します。

*Fn*<br/>
[in]イベント ハンドラー関数の名前。 この関数は、呼`_stdcall`び出し規約を使用し、適切な dispinterface スタイルのシグネチャを持つ必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]

### <a name="remarks"></a>解説

ActiveX イベント シンクの CE ATL 実装では、イベント ハンドラー メソッドからの型 HRESULT または void の戻り値のみがサポートされます。その他の戻り値はサポートされず、その動作は未定義です。

## <a name="sink_entry_info-and-sink_entry_info_p"></a><a name="sink_entry_info"></a>SINK_ENTRY_INFOとSINK_ENTRY_INFO_P

イベント シンク マップ内のSINK_ENTRY_INFO マクロを使用して、関連するハンドラー関数にイベントをルーティングするために[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)で必要な情報を提供します。

```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]イベント ソースを識別する符号なし整数。 この値は、関連する[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)基本クラスで使用される*nID*テンプレート パラメーターと一致する必要があります。

*Iid*<br/>
[in]ディスパッチ インターフェイスを識別する IID。

*ピッド*<br/>
[in]ディスパッチ インターフェイスを識別する IID へのポインター。

*Dispid*<br/>
[in]指定されたイベントを識別する DISPID。

*Fn*<br/>
[in]イベント ハンドラー関数の名前。 この関数は、呼`_stdcall`び出し規約を使用し、適切な dispinterface スタイルのシグネチャを持つ必要があります。

*info*<br/>
[in]イベント ハンドラー関数の型情報。 この型情報は、構造体へのポインターの形式で提供されます`_ATL_FUNC_INFO`。 CC_CDECLは、構造体の CALLCONV フィールドに対して Windows `_ATL_FUNC_INFO` CE でサポートされる唯一のオプションです。 その他の値はサポートされないため、その動作は未定義です。

### <a name="remarks"></a>解説

最初の 4 つのマクロ パラメーターは[、SINK_ENTRY_EX](#sink_entry_ex)マクロのパラメーターと同じです。 最後のパラメーターは、イベントの型情報を提供します。 ActiveX イベント シンクの CE ATL 実装では、イベント ハンドラー メソッドからの型 HRESULT または void の戻り値のみがサポートされます。その他の戻り値はサポートされず、その動作は未定義です。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)<br/>
[複合コントロールのグローバル関数](../../atl/reference/composite-control-global-functions.md)
