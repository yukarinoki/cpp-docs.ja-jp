---
description: '詳細情報: CComCompositeControl クラス'
title: CComCompositeControl クラス
ms.date: 11/04/2016
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
ms.openlocfilehash: 5c4d5b3e04855d570cab3a85bfe3a4c59482d990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146823"
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl クラス

このクラスは、複合コントロールを実装するために必要なメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラス、および複合コントロールに対してサポートするその他のインターフェイスから派生したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|コンストラクターです。|
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|このメソッドを呼び出して、複合コントロールによってホストされるすべてのコントロールをアドバイズまたはアドバイズを中止します。|
|[CComCompositeControl::CalcExtent](#calcextent)|複合コントロールをホストするために使用されるダイアログリソースの HIMETRIC 単位のサイズを計算するには、このメソッドを呼び出します。|
|[CComCompositeControl:: Create](#create)|このメソッドは、複合コントロールのコントロールウィンドウを作成するために呼び出されます。|
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|このメソッドを呼び出して、コントロールウィンドウを作成し、ホストされているコントロールをアドバイズします。|
|[CComCompositeControl:: SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|このメソッドを呼び出して、コンテナーの背景色を使用して、複合コントロールの背景色を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComCompositeControl:: m_hbrBackground](#m_hbrbackground)|背景ブラシ。|
|[CComCompositeControl:: m_hWndFocus](#m_hwndfocus)|現在フォーカスがあるウィンドウのハンドル。|

## <a name="remarks"></a>解説

クラスから派生したクラス `CComCompositeControl` は、ActiveX 複合コントロールの機能を継承します。 から派生 `CComCompositeControl` した ActiveX コントロールは、標準ダイアログボックスによってホストされます。 これらの種類のコントロールは、他のコントロール (ネイティブ Windows コントロールおよび ActiveX コントロール) をホストできるため、複合コントロールと呼ばれます。

`CComCompositeControl` 子クラスで列挙されたデータメンバーを検索することによって、複合コントロールの作成に使用するダイアログリソースを識別します。 この子クラスのメンバー IDD は、コントロールのウィンドウとして使用されるダイアログリソースのリソース ID に設定されます。 `CComCompositeControl`コントロールのウィンドウに使用するダイアログリソースを識別するために、から派生したクラスに含まれている必要があるデータメンバーの例を次に示します。

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
> 複合コントロールは常にウィンドウコントロールですが、ウィンドウなしのコントロールを含めることもできます。

派生クラスによって実装されるコントロールに `CComCompositeControl` は、既定のタブの動作が組み込まれています。 コントロールが、含まれているアプリケーション内のタブに移動してフォーカスを受け取ると、TAB キーを押すと、フォーカスが複合コントロールのすべてのコントロールに含まれています。その後、複合コントロールの外に移動し、コンテナーのタブオーダーの次の項目に移動します。 ホストされているコントロールのタブオーダーは、ダイアログリソースによって決定され、tab キーを使用する順序を決定します。

> [!NOTE]
> アクセラレータをで適切に動作させるには、コントロールの作成時にアクセラレータテーブルを読み込む必要があります。その後、アクセラレータ `CComCompositeControl` のハンドルと数を [IOleControlImpl:: Get linfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)に渡し、最後にコントロールが解放されたときにテーブルを破棄します。

## <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

[CComControl](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="ccomcompositecontroladvisesinkmap"></a><a name="advisesinkmap"></a> CComCompositeControl::AdviseSinkMap

このメソッドを呼び出して、複合コントロールによってホストされるすべてのコントロールをアドバイズまたはアドバイズを中止します。

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>パラメーター

*bAdvise*<br/>
すべてのコントロールを推奨する場合は True。それ以外の場合は false。

### <a name="return-value"></a>戻り値

| 値 | 説明 |
|--|--|
| `S_OK` | イベントシンクマップ内のすべてのコントロールが、イベントソースから正常に接続または切断されました。 |
| `E_FAIL` | イベントシンクマップ内のすべてのコントロールが、イベントソースから正常に接続または切断された可能性があります。 |
| `E_POINTER` | このエラーは、通常、コントロールのイベントシンクマップのエントリに問題があるか、または基底クラスで使用されるテンプレート引数に問題があることを示して `IDispEventImpl` `IDispEventSimpleImpl` います。 |
| `CONNECT_E_ADVISELIMIT` | コネクション ポイントは既に最大接続数に達していて、これ以上受け入れられません。 |
| `CONNECT_E_CANNOTCONNECT` | シンクは、このコネクションポイントで必要なインターフェイスをサポートしていません。 |
| `CONNECT_E_NOCONNECTION` | クッキーの値が有効な接続を表していません。 このエラーは、通常、コントロールのイベントシンクマップのエントリに問題があるか、または基底クラスで使用されるテンプレート引数に問題があることを示して `IDispEventImpl` `IDispEventSimpleImpl` います。 |

### <a name="remarks"></a>解説

このメソッドの基本実装は、イベントシンクマップ内のエントリを検索します。 次に、イベントシンクマップのシンクエントリによって記述された COM オブジェクトへの接続ポイントをアドバイズまたはアドバイズ解除します。 また、このメンバーメソッドは、 `IDispEventImpl` アドバイズまたはアドバイズを中止するシンクマップ内のすべてのコントロールに対して、派生クラスがの1つのインスタンスから継承することにも依存します。

## <a name="ccomcompositecontrolcalcextent"></a><a name="calcextent"></a> CComCompositeControl::CalcExtent

複合コントロールをホストするために使用されるダイアログリソースの HIMETRIC 単位のサイズを計算するには、このメソッドを呼び出します。

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
`SIZE`このメソッドで格納される構造体への参照。

### <a name="return-value"></a>戻り値

コントロールがダイアログボックスによってホストされている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

サイズは *size* パラメーターで返されます。

## <a name="ccomcompositecontrolcreate"></a><a name="create"></a> CComCompositeControl:: Create

このメソッドは、複合コントロールのコントロールウィンドウを作成するために呼び出されます。

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>パラメーター

*hWndParent*<br/>
コントロールの親ウィンドウへのハンドル。

*rcPos*<br/>
予約済み。

*dwInitParam*<br/>
コントロールの作成時にコントロールに渡されるデータ。 *Dwinitparam* として渡されるデータは、 [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog)メッセージの LPARAM パラメーターとして表示されます。これは、複合コントロールが作成されたときに送信されます。

### <a name="return-value"></a>戻り値

新しく作成された複合コントロールダイアログボックスへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、通常、コントロールのインプレースアクティベーション中に呼び出されます。

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="ccomcompositecontrol"></a> CComCompositeControl::CComCompositeControl

コンストラクターです。

```
CComCompositeControl();
```

### <a name="remarks"></a>解説

[CComCompositeControl:: m_hbrBackground](#m_hbrbackground)と[CComCompositeControl:: m_hWndFocus](#m_hwndfocus)データメンバーを NULL に初期化します。

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="dtor"></a> CComCompositeControl:: ~ CComCompositeControl

デストラクターです。

```
~CComCompositeControl();
```

### <a name="remarks"></a>解説

バックグラウンドオブジェクト (存在する場合) を削除します。

## <a name="ccomcompositecontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a> CComCompositeControl::CreateControlWindow

このメソッドを呼び出して、コントロールウィンドウを作成し、ホストされているコントロールをアドバイズします。

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>パラメーター

*hWndParent*<br/>
コントロールの親ウィンドウへのハンドル。

*rcPos*<br/>
*HWndParent* を基準とした、クライアント座標での複合コントロールの位置を示す四角形。

### <a name="return-value"></a>戻り値

新しく作成された複合コントロールダイアログボックスへのハンドルを返します。

### <a name="remarks"></a>解説

このメソッド [は、CComCompositeControl:: Create](#create) と [CComCompositeControl:: AdviseSinkMap](#advisesinkmap)を呼び出します。

## <a name="ccomcompositecontrolm_hbrbackground"></a><a name="m_hbrbackground"></a> CComCompositeControl:: m_hbrBackground

背景ブラシ。

```
HBRUSH m_hbrBackground;
```

## <a name="ccomcompositecontrolm_hwndfocus"></a><a name="m_hwndfocus"></a> CComCompositeControl:: m_hWndFocus

現在フォーカスがあるウィンドウのハンドル。

```
HWND m_hWndFocus;
```

## <a name="ccomcompositecontrolsetbackgroundcolorfromambient"></a><a name="setbackgroundcolorfromambient"></a> CComCompositeControl:: SetBackgroundColorFromAmbient

このメソッドを呼び出して、コンテナーの背景色を使用して、複合コントロールの背景色を設定します。

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[複合コントロールの基本](../../atl/atl-composite-control-fundamentals.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
