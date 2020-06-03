---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
ms.openlocfilehash: d8e60a817d197f67c14318a7d50ddf796e570142
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318742"
---
# <a name="caxdialogimpl-class"></a>クラス

このクラスは、ActiveX コントロールをホストするダイアログ ボックス (モーダルまたはモードレス) を実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, class TBase = CWindow>
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`CAxDialogImpl`。

*Tベース*<br/>
の基本ウィンドウ クラス`CDialogImplBaseT`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[アアドバイスシンクマップ](#advisesinkmap)|オブジェクトのシンク マップ イベント マップ内のすべてのエントリに対してアドバイスを行ったり、通知を解除したりするには、このメソッドを呼び出します。|
|[CAxDialogImpl::作成](#create)|モードレス ダイアログ ボックスを作成します。|
|[アックスダイアログインプル::Dエストロイウィンドウ](#destroywindow)|モードレス ダイアログ ボックスを破棄します。|
|[CAxDialogImpl::Doモーダル](#domodal)|モーダル ダイアログ ボックスを作成します。|
|[アックスダイアログインプル::エンドダイアログ](#enddialog)|モーダル ダイアログ ボックスを破棄します。|
|[をクリックします。](#getdialogproc)|`DialogProc`コールバック関数へのポインターを取得します。|
|[アックスダイアログインプル::ゲットイド](#getidd)|ダイアログ テンプレート リソース ID を取得します。|
|[をクリックします。](#isdialogmessage)|メッセージがこのダイアログ ボックスを対象としているかどうかを調べ、メッセージを処理する場合は、このメソッドを呼び出します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[アクスダイアログインプル::m_bModal](#m_bmodal)|デバッグ ビルドにのみ存在し、ダイアログ ボックスがモーダルの場合は true に設定される変数。|

## <a name="remarks"></a>解説

`CAxDialogImpl`では、モーダルまたはモードレス ダイアログ ボックスを作成できます。 `CAxDialogImpl`には、既定のメッセージ マップを使用してメッセージを適切なハンドラーに送信するダイアログ ボックス プロシージャが用意されています。

`CAxDialogImpl`は から`CDialogImplBaseT`派生し、TBase (*TBase*既定では`CWindow`) および`CMessageMap`から派生します。

クラスは、ダイアログ テンプレート リソース ID を指定する IDD メンバーを定義する必要があります。 たとえば、[**クラスの追加**] ダイアログ ボックスを使用して ATL Dialog オブジェクトを追加すると、次の行が自動的にクラスに追加されます。

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]

ATL ダイアログ ウィザードに入力された`MyDialog`**短い名前**を指定します。

詳細については、「[ダイアログ ボックスの実装](../../atl/implementing-a-dialog-box.md)」を参照してください。

モーダル ダイアログ ボックスで作成された ActiveX`CAxDialogImpl`コントロールは、アクセラレータ キーをサポートしません。 で`CAxDialogImpl`作成したダイアログ ボックスでアクセラレータ キーをサポートするには、モードレス ダイアログ ボックスを作成し、独自のメッセージ ループを使用して、キューからメッセージを取得した後[、CAxDialogImpl::IsDialogMessage](#isdialogmessage)を使用してアクセラレータ キーを処理します。

`CAxDialogImpl`の詳細については、「 [ATL コントロールの包含に関する FAQ](../../atl/atl-control-containment-faq.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CDialogImplBaseT`

`CAxDialogImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="caxdialogimpladvisesinkmap"></a><a name="advisesinkmap"></a>アアドバイスシンクマップ

オブジェクトのシンク マップ イベント マップ内のすべてのエントリに対してアドバイスを行ったり、通知を解除したりするには、このメソッドを呼び出します。

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>パラメーター

*アドバイス*<br/>
すべてのシンク エントリに対して推奨される場合は true に設定します。すべてのシンク エントリがアトレスになる場合は false。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="caxdialogimplcreate"></a><a name="create"></a>CAxDialogImpl::作成

モードレス ダイアログ ボックスを作成します。

```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
[in]所有者ウィンドウへのハンドル。

*ドウィニトパラム*<br/>
[in]WM_INITDIALOG メッセージの*lParam*パラメータでダイアログ ボックスに渡す値を指定します。

*レック&*<br/>
このパラメーターは使用されません。 このパラメータは`CComControl`.

### <a name="return-value"></a>戻り値

新しく作成されたダイアログ ボックスへのハンドル。

### <a name="remarks"></a>解説

このダイアログ ボックスは、オブジェクトに`CAxDialogImpl`自動的にアタッチされます。 モーダル ダイアログ ボックスを作成するには[、DoModal](#domodal)を呼び出します。

2 番目のオーバーライドは、ダイアログ ボックスを[CComControl](../../atl/reference/ccomcontrol-class.md)で使用できるようにのみ提供されます。

## <a name="caxdialogimpldestroywindow"></a><a name="destroywindow"></a>アックスダイアログインプル::Dエストロイウィンドウ

モードレス ダイアログ ボックスを破棄します。

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>戻り値

ウィンドウが正常に破棄された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

モーダル`DestroyWindow`ダイアログ ボックスを破棄するために呼び出す必要はありません。 代わりに[EndDialog を](#enddialog)呼び出します。

## <a name="caxdialogimpldomodal"></a><a name="domodal"></a>CAxDialogImpl::Doモーダル

モーダル ダイアログ ボックスを作成します。

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>パラメーター

*スーンドペアレント*<br/>
[in]所有者ウィンドウへのハンドル。 既定値は、[関数](/windows/win32/api/winuser/nf-winuser-getactivewindow)の戻り値です。

*ドウィニトパラム*<br/>
[in]WM_INITDIALOG メッセージの*lParam*パラメータでダイアログ ボックスに渡す値を指定します。

### <a name="return-value"></a>戻り値

成功した場合は[、EndDialog](#enddialog)の呼び出しで指定された*nRetCode*パラメーターの値。それ以外の場合は -1。

### <a name="remarks"></a>解説

このダイアログ ボックスは、オブジェクトに`CAxDialogImpl`自動的にアタッチされます。

モードレス ダイアログ ボックスを作成するには、 [Create](#create)を呼び出します。

## <a name="caxdialogimplenddialog"></a><a name="enddialog"></a>アックスダイアログインプル::エンドダイアログ

モーダル ダイアログ ボックスを破棄します。

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>パラメーター

*nレットコード*<br/>
[in]によって返される値[です](#domodal)。

### <a name="return-value"></a>戻り値

ダイアログ ボックスが破棄された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

`EndDialog`ダイアログ ボックス プロシージャを使用して呼び出す必要があります。 ダイアログ ボックスが破棄されると、ダイアログ ボックスを作成した`DoModal`戻り値として*nRetCode*の値が使用されます。

> [!NOTE]
> モードレス`EndDialog`ダイアログ ボックスを破棄するために呼び出しません。 代わりに[デストロイウィンドウを](#destroywindow)呼び出します。

## <a name="caxdialogimplgetdialogproc"></a><a name="getdialogproc"></a>をクリックします。

`DialogProc`コールバック関数へのポインターを取得します。

```
virtual DLGPROC GetDialogProc();
```

### <a name="return-value"></a>戻り値

コールバック関数へのポインターを`DialogProc`返します。

### <a name="remarks"></a>解説

この`DialogProc`関数は、アプリケーション定義のコールバック関数です。

## <a name="caxdialogimplgetidd"></a><a name="getidd"></a>アックスダイアログインプル::ゲットイド

ダイアログ テンプレート リソース ID を取得します。

```
int GetIDD();
```

### <a name="return-value"></a>戻り値

ダイアログ テンプレートリソース ID を返します。

## <a name="caxdialogimplisdialogmessage"></a><a name="isdialogmessage"></a>をクリックします。

メッセージがこのダイアログ ボックスを対象としているかどうかを調べ、メッセージを処理する場合は、このメソッドを呼び出します。

```
BOOL IsDialogMessage(LPMSG pMsg);
```

### <a name="parameters"></a>パラメーター

*Pmsg*<br/>
検査対象のメッセージを含む[MSG](/windows/win32/api/winuser/ns-winuser-msg)構造体へのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理された場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドは、メッセージ ループ内から呼び出すことを意図しています。

## <a name="caxdialogimplm_bmodal"></a><a name="m_bmodal"></a>アクスダイアログインプル::m_bModal

デバッグ ビルドにのみ存在し、ダイアログ ボックスがモーダルの場合は true に設定される変数。

```
bool m_bModal;
```

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/cdialogimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
