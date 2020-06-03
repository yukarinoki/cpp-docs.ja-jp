---
title: コントロール クラス
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
ms.openlocfilehash: 700a8047ab1fa9df85c8e6530eb3eed5f29bd3d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320802"
---
# <a name="ccomcompositecontrol-class"></a>コントロール クラス

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
[クラスは、CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から派生したクラスだけでなく、複合コントロールをサポートする他のインターフェイスから派生します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComコンポジットコントロール::CComコンポジットコントロール](#ccomcompositecontrol)|コンストラクターです。|
|[CComコンポジットコントロール:~コムコンポジットコントロール](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ココムコンポジットコントロール::アドバイスシンクマップ](#advisesinkmap)|複合コントロールによってホストされているすべてのコントロールに通知または通知を解除するには、このメソッドを呼び出します。|
|[CComコンポジットコントロール::カルクエクステント](#calcextent)|複合コントロールのホストに使用されるダイアログ リソースの HIMETRIC 単位でサイズを計算します。|
|[CComコンポジットコントロール::作成](#create)|このメソッドは、複合コントロールのコントロール ウィンドウを作成するために呼び出されます。|
|[コントロールウィンドウを作成します。](#createcontrolwindow)|コントロール ウィンドウを作成し、ホストされたコントロールに通知します。|
|[コンコムコンポジットコントロール::アンビエントから背景色を設定します](#setbackgroundcolorfromambient)|コンテナーの背景色を使用して複合コントロールの背景色を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コムコンポジットコントロール::m_hbrBackground](#m_hbrbackground)|背景ブラシ。|
|[コムコンポジットコントロール::m_hWndFocus](#m_hwndfocus)|現在フォーカスがあるウィンドウのハンドル。|

## <a name="remarks"></a>解説

クラスから派生した`CComCompositeControl`クラスは、ActiveX 複合コントロールの機能を継承します。 派生`CComCompositeControl`した ActiveX コントロールは、標準のダイアログ ボックスでホストされます。 これらのコントロールは、他のコントロール (ネイティブ Windows コントロールと ActiveX コントロール) をホストできるため、複合コントロールと呼ばれます。

`CComCompositeControl`子クラスで列挙されたデータ メンバーを検索して、複合コントロールの作成に使用するダイアログ リソースを識別します。 この子クラスのメンバー IDD は、コントロールのウィンドウとして使用されるダイアログ リソースのリソース ID に設定されます。 次に、コントロールのウィンドウで使用するダイアログ リソースを識別`CComCompositeControl`するために、派生したクラスに含める必要があるデータ メンバーの例を示します。

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
> 複合コントロールは常にウィンドウ付きコントロールですが、ウィンドウなしのコントロールを含めることができます。

派生クラスによって`CComCompositeControl`実装されるコントロールには、既定のタブ処理動作が組み込まれています。 コントロールが、コンテナー アプリケーションでタブ付けされてフォーカスを受け取ると、Tab キーを連続的に押すと、複合コントロールに含まれるすべてのコントロールを順番にフォーカスが循環し、複合コントロールから次の項目に移動します。 ホストされたコントロールのタブオーダーはダイアログリソースによって決定され、タブが発生する順序を決定します。

> [!NOTE]
> アクセラレータが`CComCompositeControl`で正しく動作するためには、コントロールの作成時にアクセラレータ テーブルを読み込み、ハンドルと数のアクセラレータを[IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)に渡し、コントロールが解放されたときに最後にテーブルを破棄する必要があります。

## <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`WinBase`

[コムコントロールベース](../../atl/reference/ccomcontrolbase-class.md)

[コムコントロール](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="ccomcompositecontroladvisesinkmap"></a><a name="advisesinkmap"></a>ココムコンポジットコントロール::アドバイスシンクマップ

複合コントロールによってホストされているすべてのコントロールに通知または通知を解除するには、このメソッドを呼び出します。

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>パラメーター

*アドバイス*<br/>
すべてのコントロールに対して推奨される場合は true。それ以外の場合は false です。

### <a name="return-value"></a>戻り値

|||
|-|-|
|S_OK  |イベント シンク マップ内のすべてのコントロールが、イベント ソースに接続されているか、またはイベント ソースから切断されました。|
|E_FAIL  |イベント シンク マップ内のすべてのコントロールが、イベント ソースに接続または切断されたわけではありません。|
|E_POINTER  |このエラーは通常、コントロールのイベント シンク マップのエントリに問題がある、または基本`IDispEventImpl``IDispEventSimpleImpl`クラスで使用されるテンプレート引数に問題が発生していることを示します。|
|CONNECT_E_ADVISELIMIT  |コネクション ポイントは既に最大接続数に達していて、これ以上受け入れられません。|
|CONNECT_E_CANNOTCONNECT  |シンクは、このコネクション ポイントに必要なインターフェイスをサポートしていません。|
|CONNECT_E_NOCONNECTION  |Cookie 値は有効な接続を表していません。 このエラーは通常、コントロールのイベント シンク マップのエントリに問題がある、または基本`IDispEventImpl``IDispEventSimpleImpl`クラスで使用されるテンプレート引数に問題が発生していることを示します。|

### <a name="remarks"></a>解説

このメソッドの基本実装は、イベント シンク マップ内のエントリを検索します。 次に、イベント シンク マップのシンク エントリによって記述される COM オブジェクトへのコネクション ポイントをアドバイスまたはアンアドバイスします。 このメンバー メソッドは、シンク マップ内のコントロールのうち、推奨される、または推奨`IDispEventImpl`されないすべてのコントロールについて、派生クラスが 1 つのインスタンスから継承するという事実にも依存しています。

## <a name="ccomcompositecontrolcalcextent"></a><a name="calcextent"></a>CComコンポジットコントロール::カルクエクステント

複合コントロールのホストに使用されるダイアログ リソースの HIMETRIC 単位でサイズを計算します。

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
このメソッドによって埋`SIZE`め込まれる構造体への参照。

### <a name="return-value"></a>戻り値

コントロールがダイアログ ボックスによってホストされている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

サイズは *、サイズ*パラメーターで返されます。

## <a name="ccomcompositecontrolcreate"></a><a name="create"></a>CComコンポジットコントロール::作成

このメソッドは、複合コントロールのコントロール ウィンドウを作成するために呼び出されます。

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
コントロールの親ウィンドウへのハンドル。

*rcPos*<br/>
予約済み。

*ドウィニトパラム*<br/>
コントロールの作成時にコントロールに渡されるデータ。 *dwInitParam*として渡されたデータは[、WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog)メッセージの LPARAM パラメーターとして表示され、作成時に複合コントロールに送信されます。

### <a name="return-value"></a>戻り値

新しく作成された複合コントロール ダイアログ ボックスへのハンドル。

### <a name="remarks"></a>解説

このメソッドは通常、コントロールのインプレース アクティブ化時に呼び出されます。

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="ccomcompositecontrol"></a>CComコンポジットコントロール::CComコンポジットコントロール

コンストラクターです。

```
CComCompositeControl();
```

### <a name="remarks"></a>解説

[m_hbrBackground データ](#m_hbrbackground)メンバーを NULL に[m_hWndFocus](#m_hwndfocus)します。

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="dtor"></a>CComコンポジットコントロール:~コムコンポジットコントロール

デストラクターです。

```
~CComCompositeControl();
```

### <a name="remarks"></a>解説

背景オブジェクトが存在する場合は、そのオブジェクトを削除します。

## <a name="ccomcompositecontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a>コントロールウィンドウを作成します。

コントロール ウィンドウを作成し、ホストされているコントロールに通知します。

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
コントロールの親ウィンドウへのハンドル。

*rcPos*<br/>
クライアント座標での複合コントロールの位置の四角形を*hWndParent*に相対します。

### <a name="return-value"></a>戻り値

新しく作成された複合コントロール ダイアログ ボックスへのハンドルを返します。

### <a name="remarks"></a>解説

このメソッドは[、CCom コンポジット コントロールを](#create)呼び出します。:作成と[CCom コンポジット コントロール::AdviseSinkMap](#advisesinkmap).

## <a name="ccomcompositecontrolm_hbrbackground"></a><a name="m_hbrbackground"></a>コムコンポジットコントロール::m_hbrBackground

背景ブラシ。

```
HBRUSH m_hbrBackground;
```

## <a name="ccomcompositecontrolm_hwndfocus"></a><a name="m_hwndfocus"></a>コムコンポジットコントロール::m_hWndFocus

現在フォーカスがあるウィンドウのハンドル。

```
HWND m_hWndFocus;
```

## <a name="ccomcompositecontrolsetbackgroundcolorfromambient"></a><a name="setbackgroundcolorfromambient"></a>コンコムコンポジットコントロール::アンビエントから背景色を設定します

コンテナーの背景色を使用して複合コントロールの背景色を設定します。

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="see-also"></a>関連項目

[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[複合コントロールの基本](../../atl/atl-composite-control-fundamentals.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
