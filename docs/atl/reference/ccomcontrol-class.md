---
title: CCom コントロール クラス
ms.date: 11/04/2016
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
ms.openlocfilehash: 3518de3596748fa284c1f898b69d1576903e9510
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320764"
---
# <a name="ccomcontrol-class"></a>CCom コントロール クラス

このクラスには、ATL コントロールを作成および管理するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, class WinBase = CWindowImpl<T>>
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コントロールを実装するクラス。

*ウィンベース*<br/>
ウィンドウ関数を実装する基本クラス。 既定値は[CWindowImpl に設定されます](../../atl/reference/cwindowimpl-class.md)。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ココムコントロール::コムコントロール](#ccomcontrol)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロール::コントロールクエリインターフェイス](#controlqueryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[コントロール::コントロールウィンドウを作成します。](#createcontrolwindow)|コントロールのウィンドウを作成します。|
|[コムコントロール::ファイアオン変更](#fireonchanged)|コントロール プロパティが変更されたことをコンテナーのシンクに通知します。|
|[ココムコントロール::FireOnRequestEdit](#fireonrequestedit)|コントロール プロパティが変更されようとしていること、およびオブジェクトがシンクに処理の続行方法を要求していることをコンテナーのシンクに通知します。|
|[コントロール::メッセージボックス](#messagebox)|メッセージ ボックスを作成、表示、および操作します。|

## <a name="remarks"></a>解説

`CComControl`は、ATL コントロールの便利なコントロール ヘルパー関数と重要なデータ メンバーのセットです。 ATL コントロール ウィザードを使用して標準コントロールまたは DHTML コントロールを作成すると、ウィザードによってクラスが`CComControl`から自動的に派生します。 `CComControl`そのメソッドの大部分は[、CComControlBase](../../atl/reference/ccomcontrolbase-class.md)から派生します。

コントロールの作成の詳細については[、「ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)」を参照してください。 ATL プロジェクト ウィザードの詳細については、ATL[プロジェクトの作成に関する記事を](../../atl/reference/creating-an-atl-project.md)参照してください。

メソッドとデータ`CComControl`メンバーのデモンストレーションについては[、CIRC](../../overview/visual-cpp-samples.md)サンプルを参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`WinBase`

[コムコントロールベース](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="ccomcontrolccomcontrol"></a><a name="ccomcontrol"></a>ココムコントロール::コムコントロール

コンストラクターです。

```
CComControl();
```

### <a name="remarks"></a>解説

CWindowImpl を介して継承されたデータ`m_hWnd`メンバーを渡して[、CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase)コンストラクターを呼び出[します](../../atl/reference/cwindowimpl-class.md)。

## <a name="ccomcontrolcontrolqueryinterface"></a><a name="controlqueryinterface"></a>コントロール::コントロールクエリインターフェイス

要求されたインターフェイスへのポインターを取得します。

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]要求されているインターフェイスの GUID。

*Ppv*<br/>
[アウト]*iid*で識別されるインターフェイス ポインタへのポインタ、 またはインターフェイスが見つからない場合は NULL。

### <a name="remarks"></a>解説

COM マップ テーブル内のインターフェイスのみを処理します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

## <a name="ccomcontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a>コントロール::コントロールウィンドウを作成します。

既定では、 を呼び出`CWindowImpl::Create`してコントロールのウィンドウを作成します。

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
[in]親ウィンドウまたはオーナー ウィンドウへのハンドル。 有効なウィンドウ ハンドルを指定する必要があります。 コントロール ウィンドウは、親ウィンドウの領域に限定されます。

*rcPos*<br/>
[in]作成するウィンドウの初期サイズと位置。

### <a name="remarks"></a>解説

1 つのウィンドウを作成する以外の操作を行う場合(たとえば、2 つのウィンドウを作成する場合など)、このメソッドをオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

## <a name="ccomcontrolfireonchanged"></a><a name="fireonchanged"></a>コムコントロール::ファイアオン変更

コントロール プロパティが変更されたことをコンテナーのシンクに通知します。

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
[in]変更されたプロパティの識別子。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

コントロール クラスが[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)から派生している場合、このメソッドは[CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged)を呼び出して、指定されたコントロール プロパティが変更されたことをすべての接続された`IPropertyNotifySink`インターフェイスに通知します。 コントロール クラスが から`IPropertyNotifySink`派生していない場合、このメソッドはS_OK返します。

このメソッドは、コントロールがコネクション ポイントをサポートしていない場合でも、安全に呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

## <a name="ccomcontrolfireonrequestedit"></a><a name="fireonrequestedit"></a>ココムコントロール::FireOnRequestEdit

コントロール プロパティが変更されようとしていること、およびオブジェクトがシンクに処理の続行方法を要求していることをコンテナーのシンクに通知します。

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
[in]変更しようとしているプロパティの識別子。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

コントロール クラスが[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)から派生している場合、このメソッドは[CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit)を呼び出して、指定されたコントロール プロパティが変更されようとしているすべての接続された`IPropertyNotifySink`インターフェイスに通知します。 コントロール クラスが から`IPropertyNotifySink`派生していない場合、このメソッドはS_OK返します。

このメソッドは、コントロールがコネクション ポイントをサポートしていない場合でも、安全に呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

## <a name="ccomcontrolmessagebox"></a><a name="messagebox"></a>コントロール::メッセージボックス

メッセージ ボックスを作成、表示、および操作します。

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
メッセージ ボックスに表示するテキスト。

*一方、一時おくもみ*<br/>
ダイアログ ボックスのタイトル。 NULL (既定値) の場合は、タイトル "エラー" が使用されます。

*nType*<br/>
ダイアログ ボックスの内容と動作を指定します。 使用可能なさまざまな[メッセージ ボックス](/windows/win32/api/winuser/nf-winuser-messagebox)の一覧については、Windows SDK のドキュメントのメッセージ ボックスエントリを参照してください。 デフォルトでは、単純な **[OK]** ボタンが用意されています。

### <a name="return-value"></a>戻り値

Windows SDK ドキュメントの[メッセージ ボックス](/windows/win32/api/winuser/nf-winuser-messagebox)に表示されているメニュー項目の値のいずれかを指定する整数値を返します。

### <a name="remarks"></a>解説

`MessageBox`は、開発中に、エラーメッセージや警告メッセージをユーザーに表示する簡単な方法として、両方とも役立ちます。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/cwindowimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラス](../../atl/reference/ccomcontrolbase-class.md)<br/>
[コントロール クラス](../../atl/reference/ccomcompositecontrol-class.md)
