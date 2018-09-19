---
title: CComControl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
dev_langs:
- C++
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb2d345e0bb8be8f5150d48237df9845acf451dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036177"
---
# <a name="ccomcontrol-class"></a>CComControl クラス

このクラスは、作成および ATL のコントロールを管理するためのメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, class WinBase = CWindowImpl<T>>
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コントロールを実装するクラスです。

*WinBase*<br/>
ウィンドウ関数を実装する基本クラス。 既定値は[CWindowImpl](../../atl/reference/cwindowimpl-class.md)します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComControl::CComControl](#ccomcontrol)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComControl::ControlQueryInterface](#controlqueryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[CComControl::CreateControlWindow](#createcontrolwindow)|コントロールのウィンドウを作成します。|
|[CComControl::FireOnChanged](#fireonchanged)|コントロールのプロパティが変更されたコンテナーのシンクに通知します。|
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|コントロールのプロパティを変更することと、オブジェクトが要求している、シンクの続行方法、コンテナーのシンクに通知します。|
|[CComControl::MessageBox](#messagebox)|作成、表示、およびメッセージ ボックスを操作するには、このメソッドを呼び出します。|

## <a name="remarks"></a>Remarks

`CComControl` 便利なコントロールのヘルパー関数と ATL のコントロールの重要なデータ メンバーのセットです。 標準のコントロールまたは ATL コントロール ウィザードを使用して、DHTML コントロールを作成するときにウィザードが自動的にからクラスを派生`CComControl`します。 `CComControl` メソッドのほとんどを派生[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)します。

コントロールの作成の詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)します。 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)です。

例については`CComControl`メソッドと、データ メンバーを参照してください、[円](../../visual-cpp-samples.md)サンプル。

## <a name="inheritance-hierarchy"></a>継承階層

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl.h

##  <a name="ccomcontrol"></a>  CComControl::CComControl

コンストラクターです。

```
CComControl();
```

### <a name="remarks"></a>Remarks

呼び出し、 [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase)コンス トラクターを渡して、`m_hWnd`を通じてデータ メンバーが継承[CWindowImpl](../../atl/reference/cwindowimpl-class.md)します。

##  <a name="controlqueryinterface"></a>  CComControl::ControlQueryInterface

要求されたインターフェイスへのポインターを取得します。

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
[in]要求されているインターフェイスの GUID です。

*ppv*<br/>
[out]によって識別されるインターフェイス ポインターへのポインター *iid*インターフェイスが見つからない場合は null です。

### <a name="remarks"></a>Remarks

COM マップ テーブル内のインターフェイスのみを処理します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

##  <a name="createcontrolwindow"></a>  CComControl::CreateControlWindow

既定では、呼び出すことによって、コントロールのウィンドウを作成します。`CWindowImpl::Create`します。

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>パラメーター

*hWndParent*<br/>
[in]親またはオーナー ウィンドウへのハンドルします。 有効なウィンドウ ハンドルを指定する必要があります。 コントロールのウィンドウは、親ウィンドウの領域に限定されます。

*rcPos*<br/>
[in]初期サイズと作成するウィンドウの位置。

### <a name="remarks"></a>Remarks

このメソッドをオーバーライドして、作業を行う場合以外の 1 つのウィンドウを作成、コントロールのツールバーになりますうちの 1 つを 2 つのウィンドウを作成するには、たとえば、します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

##  <a name="fireonchanged"></a>  CComControl::FireOnChanged

コントロールのプロパティが変更されたコンテナーのシンクに通知します。

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>パラメーター

*dispID*<br/>
[in]変更されたプロパティの識別子。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>Remarks

場合は、コントロール クラスから派生[IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)、このメソッドを呼び出す[CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged)すべてに通知するには接続`IPropertyNotifySink`インターフェイスを指定したコントロールプロパティが変更されました。 コントロール クラスがから派生していない場合`IPropertyNotifySink`、このメソッドは、S_OK を返します。

このメソッドは、安全に呼び出す場合でも、コントロールは、接続ポイントをサポートしません。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

##  <a name="fireonrequestedit"></a>  CComControl::FireOnRequestEdit

コントロールのプロパティを変更することと、オブジェクトが要求している、シンクの続行方法、コンテナーのシンクに通知します。

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>パラメーター

*dispID*<br/>
[in]変更するプロパティの識別子。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>Remarks

場合は、コントロール クラスから派生[IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)、このメソッドを呼び出す[CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit)すべてに通知するには接続`IPropertyNotifySink`インターフェイスを指定されました。コントロールのプロパティがこれから変更します。 コントロール クラスがから派生していない場合`IPropertyNotifySink`、このメソッドは、S_OK を返します。

このメソッドは、安全に呼び出す場合でも、コントロールは、接続ポイントをサポートしません。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

##  <a name="messagebox"></a>  CComControl::MessageBox

作成、表示、およびメッセージ ボックスを操作するには、このメソッドを呼び出します。

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
メッセージ ボックスに表示されるテキスト。

*lpszCaption*<br/>
ダイアログ ボックスのタイトル。 場合は NULL (既定)、「エラー」が使用されるタイトル。

*%n タイプ*<br/>
内容と、ダイアログ ボックスの動作を指定します。 参照してください、[メッセージ ボックス](/windows/desktop/api/winuser/nf-winuser-messagebox)使用可能なさまざまなメッセージ ボックスの一覧については、Windows SDK ドキュメント内のエントリ。 既定では、単純な**OK**ボタンをクリックします。

### <a name="return-value"></a>戻り値

下に表示 メニュー項目の値のいずれかを示す整数値を返します[メッセージ ボックス](/windows/desktop/api/winuser/nf-winuser-messagebox)Windows SDK のドキュメント。

### <a name="remarks"></a>Remarks

`MessageBox` 開発時とユーザーにエラーまたは警告メッセージを表示する簡単な方法としては役立ちます。

## <a name="see-also"></a>関連項目

[CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComControlBase クラス](../../atl/reference/ccomcontrolbase-class.md)<br/>
[CComCompositeControl クラス](../../atl/reference/ccomcompositecontrol-class.md)
