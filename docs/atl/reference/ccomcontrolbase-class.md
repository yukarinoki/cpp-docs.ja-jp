---
title: CComControlBase クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
dev_langs:
- C++
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b72157db26d4cb7d576e32ca704a32b62b4c2da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366355"
---
# <a name="ccomcontrolbase-class"></a>CComControlBase クラス
このクラスは、作成して、ATL コントロールを管理するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class ATL_NO_VTABLE CComControlBase
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComControlBase::AppearanceType](#appearancetype)|場合は、オーバーライド、`m_nAppearance`ストック プロパティは、型の`short`します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComControlBase::CComControlBase](#ccomcontrolbase)|コンストラクターです。|  
|[CComControlBase:: ~ CComControlBase](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|確認、`iVerb`で使用されるパラメーター`IOleObjectImpl::DoVerb`コントロールのユーザー インターフェイスをアクティブにするか ( `iVerb` equals `OLEIVERB_UIACTIVATE`)、ユーザーがコントロールをダブルクリックしたときに実行されるアクションを定義します ( `iVerb` に等しい`OLEIVERB_PRIMARY`)、コントロールが表示されます ( `iVerb` equals `OLEIVERB_SHOW`)、またはコントロールをアクティブ化 ( `iVerb` equals **OLEIVERB_INPLACEACTIVATE**)。|  
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|確認、`iVerb`で使用されるパラメーター`IOleObjectImpl::DoVerb`コントロールのユーザー インターフェイスをアクティブ化してを返します**TRUE**です。|  
|[CComControlBase::DoVerbProperties](#doverbproperties)|コントロールのプロパティ ページを表示します。|  
|[CComControlBase::FireViewChange](#fireviewchange)|コントロールを再描画するコンテナーを確認するには、このメソッドを呼び出すか、コントロールのビューが変更された登録済みアドバイズ シンクに通知します。|  
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|取得**を示す**、現在の外観をコントロールの設定: フラットと 3d 1 0 を指定します。|  
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|取得**DISPID_AMBIENT_AUTOCLIP**コンテナーがコントロールの表示領域の自動クリップをサポートしているかどうかを示しますフラグ。|  
|[用意されています](#getambientbackcolor)|取得**DISPID_AMBIENT_BACKCOLOR**、コンテナーによって定義されている、すべてのコントロールのアンビエント背景色。|  
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|取得**DISPID_AMBIENT_CHARSET**、アンビエント文字セットのコンテナーで定義されているすべてのコントロールです。|  
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|取得**ことにあります**、アンビエント文字セットのコンテナーで定義されているすべてのコントロールです。|  
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|取得**DISPID_AMBIENT_DISPLAYASDEFAULT**、あるフラグ**TRUE**場合は、コンテナーが既定のボタンにするには、このサイト内のコントロールをマークし、したがってボタン コントロールが描画するのには、自ら、太くフレームです。|  
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|取得**DISPID_AMBIENT_DISPLAYNAME**コンテナーがコントロールに指定した名前です。|  
|[CComControlBase::GetAmbientFont](#getambientfont)|取得、コンテナーへのポインターのアンビエント`IFont`インターフェイスです。|  
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|取得、コンテナーへのポインターのアンビエント**この**ディスパッチ インターフェイスです。|  
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|取得**DISPID_AMBIENT_FORECOLOR**、コンテナーによって定義されている、すべてのコントロールのアンビエント前景色。|  
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|取得**DISPID_AMBIENT_LOCALEID**、コンテナーによって使用される言語の識別子。|  
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|取得**DISPID_AMBIENT_MESSAGEREFLECT**、コンテナーがウィンドウのメッセージを受信するかどうかを示すフラグ (など`WM_DRAWITEM`) イベントとして。|  
|[CComControlBase::GetAmbientPalette](#getambientpalette)|取得**DISPID_AMBIENT_PALETTE**コンテナーのアクセスに使用される、`HPALETTE`です。|  
|[CComControlBase::GetAmbientProperty](#getambientproperty)|指定されたコンテナーのプロパティを取得`id`です。|  
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|取得**DISPID_AMBIENT_RIGHTTOLEFT**方向、コンテナーによってコンテンツが表示されます。|  
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|取得**DISPID_AMBIENT_SCALEUNITS**コンテナーのアンビエント単位数 (インチやセンチメートル) などのラベル付けが表示されます。|  
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|取得**DISPID_AMBIENT_SHOWGRABHANDLES**コンテナーがアクティブなときにハンドルを表示するコントロールを許可するかどうかを示すフラグ。|  
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|取得**DISPID_AMBIENT_SHOWHATCHING**コンテナーがときに表示される自体ハッチ パターンで UI がアクティブなコントロールを許可するかどうかを示すフラグ。|  
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|取得**DISPID_AMBIENT_SUPPORTSMNEMONICS**コンテナーがキーボードのニーモニックをサポートしているかどうかを示しますフラグ。|  
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|取得**DISPID_AMBIENT_TEXTALIGN**コンテナーで優先されるテキストの配置: 一般的な配置 (数値、テキストを左) の場合は 0、左揃えの場合は 1、2 を中央揃え、および右揃えの 3 です。|  
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|取得**DISPID_AMBIENT_TOPTOBOTTOM**方向、コンテナーによってコンテンツが表示されます。|  
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|取得**DISPID_AMBIENT_UIDEAD**コンテナーに、コントロール ユーザー インターフェイスの動作に応答するかどうかを示すフラグ。|  
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|取得**DISPID_AMBIENT_USERMODE**、コンテナーが実行モードであるかどうかを示すフラグ ( **TRUE**) デザイン モードまたは ( **FALSE**)。|  
|[CComControlBase::GetDirty](#getdirty)|データ メンバーの値を返します`m_bRequiresSave`です。|  
|[CComControlBase::GetZoomInfo](#getzoominfo)|取得、x と y の分子とズームの倍率の分母の値の有効なコントロールの埋め込み先編集します。|  
|[CComControlBase::InPlaceActivate](#inplaceactivate)|動詞には、状態を非アクティブ状態から移行するコントロールをさせます`iVerb`を示します。|  
|[CComControlBase::InternalGetSite](#internalgetsite)|識別されたインターフェイスへのポインターのコントロール サイトを照会するには、このメソッドを呼び出します。|  
|[CComControlBase::OnDraw](#ondraw)|コントロールを描画するには、このメソッドをオーバーライドします。|  
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|既定値**OnDrawAdvanced**描画、正規化されたデバイス コンテキストを準備し、コントロール クラスの`OnDraw`メソッドです。|  
|[CComControlBase::OnKillFocus](#onkillfocus)|コントロール、インプレース アクティブと有効なコントロール サイトを持つそのがコンテナーに通知コントロールがフォーカスを失ったことを確認します。|  
|[CComControlBase::OnMouseActivate](#onmouseactivate)|UI がユーザー モードでは、し、コントロールをアクティブにすることを確認します。|  
|[CComControlBase::OnPaint](#onpaint)|描画するため、コンテナーを準備し、コントロールのクライアント領域の取得、コントロール クラスの`OnDraw`メソッドです。|  
|[CComControlBase::OnSetFocus](#onsetfocus)|コントロール、インプレース アクティブと有効なコントロール サイトを持つそのがコンテナー コントロールに通知の確認は、フォーカスを得てきました。|  
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|独自のキーボード アクセラレータのハンドラーを提供するには、このメソッドをオーバーライドします。|  
|[CComControlBase::SendOnClose](#sendonclose)|コントロールが閉じられたことアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。|  
|[CComControlBase::SendOnDataChange](#sendondatachange)|コントロールのデータが変更されたアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。|  
|[CComControlBase::SendOnRename](#sendonrename)|コントロールに新しいモニカーがあること、アドバイズ保有者に登録されているすべてのアドバイズ シンクに通知します。|  
|[CComControlBase::SendOnSave](#sendonsave)|コントロールが保存されているアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。|  
|[CComControlBase::SendOnViewChange](#sendonviewchange)|登録されているすべてのコントロールのビューが変更されたアドバイズ シンクに通知します。|  
|[CComControlBase::SetControlFocus](#setcontrolfocus)|設定またはコントロールの間にキーボード フォーカスを削除します。|  
|[CComControlBase::SetDirty](#setdirty)|データ メンバーを設定`m_bRequiresSave`の値に`bDirty`です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComControlBase::m_bAutoSize](#m_bautosize)|コントロールが他の任意のサイズを変更できないことを示すフラグです。|  
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|示すフラグ`IDataObjectImpl::GetData`と`CComControlBase::GetZoomInfo`からコントロールのサイズを設定する必要があります`m_sizeNatural`からではなく`m_sizeExtent`です。|  
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|示すフラグ`IDataObjectImpl::GetData`描画するときに HIMETRIC 単位と単位を使用する必要があります。|  
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|コントロールが、インプレース アクティブであることを示すフラグです。|  
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|コンテナーのサポートを示すフラグ、**処理**インターフェイスと OCX96 およびちらつきなしのコントロールなどの機能を制御します。|  
|[各](#m_bnegotiatedwnd)|(ちらつきなしでウィンドウ コントロールなど)、OCX96 コントロールの機能のサポートのコンテナーとコントロールがネゴシエートされるかどうか、およびコントロールでのウィンドウまたはウィンドウなしがかどうかを示すフラグです。|  
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|コントロールがコンテナーには、コントロールの表示サイズが変更されたときに、プレゼンテーションを再構成することを示すフラグです。|  
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|最後に保存された後、コントロールが変更を示すフラグします。|  
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|コントロールが本来のエクステント (スケールなし物理サイズ) のサイズを変更することを示すフラグ、コンテナーにコントロールの表示サイズが変更されたとき。|  
|[CComControlBase::m_bUIActive](#m_buiactive)|メニューやツールバーなどのコントロールのユーザー インターフェイスを示すフラグがアクティブです。|  
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|コントロールは、コンテナーが指定したウィンドウ領域の使用を示すフラグします。|  
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|コントロール ウィンドウなし、されましたが、可能性がありますでなくてもかまいませんウィンドウなし今すぐを示すフラグします。|  
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|コンテナーは、ウィンドウなしのコントロールをサポートしている場合でも、コントロールはウィンドウを持つできるかを示すフラグです。|  
|[CComControlBase::m_bWndLess](#m_bwndless)|コントロールはウィンドウなしを示すフラグします。|  
|[CComControlBase::m_hWndCD](#m_hwndcd)|コントロールに関連付けられているウィンドウ ハンドルへの参照が含まれています。|  
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|回数のカウント コンテナー イベントを固定した (イベントを承諾することを拒否) イベント (イベントの受け入れ) の中間の凍結解除なし。|  
|[CComControlBase::m_rcPos](#m_rcpos)|コンテナーの座標で表される、コントロールの位置をピクセル単位で。|  
|[この](#m_sizeextent)|HIMETRIC 単位 (各単位は 0.01 ミリメートル) 特定のディスプレイのコントロールの範囲。|  
|[CComControlBase::m_sizeNatural](#m_sizenatural)|HIMETRIC 単位 (各単位は 0.01 ミリメートル) 内のコントロールの物理サイズ。|  
|[アドバイズ](#m_spadvisesink)|コンテナー上のアドバイザリ コネクションを直接のポインター (コンテナーの[IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513))。|  
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|A`CComDispatchDriver`オブジェクトを取得し、コンテナーのプロパティを設定することができます、`IDispatch`ポインター。|  
|[CComControlBase::m_spClientSite](#m_spclientsite)|コンテナー内のコントロールのクライアントのサイトへのポインター。|  
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|データ オブジェクト間のアドバイザリ コネクションをアドバイズ シンクすることを意味標準を提供します。|  
|[は](#m_spinplacesite)|コンテナーへのポインター[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461)、または[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)インターフェイス ポインター。|  
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|アドバイザリ コネクションを保持するための標準的な実装を提供します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、作成して、ATL コントロールを管理するためのメソッドを提供します。 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)から派生した`CComControlBase`です。 ATL コントロール ウィザードを使用して、標準のコントロールまたは DHTML コントロールを作成するときに、ウィザードは自動的に派生クラスから`CComControlBase`です。  
  
 コントロールの作成の詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)です。 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトを作成する](../../atl/reference/creating-an-atl-project.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="appearancetype"></a>  CComControlBase::AppearanceType  
 場合は、オーバーライド、 **m_nAppearance**ストック プロパティは、型の**短い**です。  
  
```
typedef short AppearanceType;
```  
  
### <a name="remarks"></a>コメント  
 ATL コントロール ウィザードの追加**m_nAppearance**ストック short 型のプロパティです。 オーバーライド`AppearanceType`別のデータ型を使用する場合。  
  
##  <a name="ccomcontrolbase"></a>  CComControlBase::CComControlBase  
 コンストラクターです。  
  
```
CComControlBase(HWND& h);
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 コントロールに関連付けられているウィンドウ ハンドルです。  
  
### <a name="remarks"></a>コメント  
 コントロールのサイズを HIMETRIC 単位の 5080 × 5080 初期化 (2 2"X") を初期化し、`CComControlBase`データ メンバーの値を**NULL**または**FALSE**です。  
  
##  <a name="dtor"></a>  CComControlBase:: ~ CComControlBase  
 デストラクターです。  
  
```
~CComControlBase();
```  
  
### <a name="remarks"></a>コメント  
 コントロールのウィンドウを持つ場合`~CComControlBase`を呼び出して破棄[DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682)です。  
  
##  <a name="controlqueryinterface"></a>  CComControlBase::ControlQueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 要求されているインターフェイスの GUID です。  
  
 `ppv`  
 によって識別されるインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 COM マップ テーブル内のインターフェイスを処理のみです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]  
  
##  <a name="doesverbactivate"></a>  CComControlBase::DoesVerbActivate  
 確認、`iVerb`で使用されるパラメーター`IOleObjectImpl::DoVerb`コントロールのユーザー インターフェイスをアクティブにするか ( `iVerb` equals `OLEIVERB_UIACTIVATE`)、ユーザーがコントロールをダブルクリックしたときに実行されるアクションを定義します ( `iVerb` に等しい`OLEIVERB_PRIMARY`)、コントロールが表示されます ( `iVerb` equals `OLEIVERB_SHOW`)、またはコントロールをアクティブ化 ( `iVerb` equals **OLEIVERB_INPLACEACTIVATE**)。  
  
```
BOOL DoesVerbActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 によって実行されるアクションを示す値`DoVerb`です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**場合`iVerb`equals `OLEIVERB_UIACTIVATE`、 `OLEIVERB_PRIMARY`、 `OLEIVERB_SHOW`、または**OLEIVERB_INPLACEACTIVATE**、それ以外を返します**FALSE**.  
  
### <a name="remarks"></a>コメント  
 独自のライセンス認証の動詞を定義するには、このメソッドをオーバーライドすることができます。  
  
##  <a name="doesverbuiactivate"></a>  CComControlBase::DoesVerbUIActivate  
 確認、`iVerb`で使用されるパラメーター`IOleObjectImpl::DoVerb`コントロールのユーザー インターフェイスをアクティブ化してを返します**TRUE**です。  
  
```
BOOL DoesVerbUIActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 によって実行されるアクションを示す値`DoVerb`です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**場合`iVerb`equals `OLEIVERB_UIACTIVATE`、 `OLEIVERB_PRIMARY`、 `OLEIVERB_SHOW`、または**OLEIVERB_INPLACEACTIVATE**です。 メソッドを返しますそれ以外の場合、 **FALSE**です。  
  
##  <a name="doverbproperties"></a>  CComControlBase::DoVerbProperties  
 コントロールのプロパティ ページを表示します。  
  
```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 予約済み。  
  
 *hwndParent*  
 コントロールを含むウィンドウのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]  
  
 [!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]  
  
##  <a name="fireviewchange"></a>  CComControlBase::FireViewChange  
 コントロールを再描画するコンテナーを確認するには、このメソッドを呼び出すか、コントロールのビューが変更された登録済みアドバイズ シンクに通知します。  
  
```
HRESULT FireViewChange();
```  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 コントロールがアクティブな場合 (コントロール クラスのデータ メンバー [CComControlBase::m_bInPlaceActive](#m_binplaceactive)は**TRUE**)、コントロール全体を再描画するコンテナーに通知します。 コントロールがアクティブでない場合は、コントロールの登録に通知アドバイズ シンク (コントロール クラスのデータ メンバーを介して[アドバイズ](#m_spadvisesink)) コントロールのビューが変更されたことです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]  
  
##  <a name="getambientappearance"></a>  CComControlBase::GetAmbientAppearance  
 取得**を示す**、現在の外観をコントロールの設定: フラットと 3d 1 0 を指定します。  
  
```
HRESULT GetAmbientAppearance(short& nAppearance);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAppearance`  
 プロパティ**を示す**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]  
  
##  <a name="getambientautoclip"></a>  CComControlBase::GetAmbientAutoClip  
 取得**DISPID_AMBIENT_AUTOCLIP**コンテナーがコントロールの表示領域の自動クリップをサポートしているかどうかを示しますフラグ。  
  
```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAutoClip*  
 プロパティ**DISPID_AMBIENT_AUTOCLIP**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientbackcolor"></a>  用意されています  
 取得**DISPID_AMBIENT_BACKCOLOR**、コンテナーによって定義されている、すべてのコントロールのアンビエント背景色。  
  
```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *背景色*  
 プロパティ**DISPID_AMBIENT_BACKCOLOR**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientcharset"></a>  CComControlBase::GetAmbientCharSet  
 取得**DISPID_AMBIENT_CHARSET**、アンビエント文字セットのコンテナーで定義されているすべてのコントロールです。  
  
```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrCharSet*  
 プロパティ**DISPID_AMBIENT_CHARSET**です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="getambientcodepage"></a>  CComControlBase::GetAmbientCodePage  
 取得**ことにあります**、コンテナーによって定義されている、すべてのコントロールのアンビエント コード ページです。  
  
```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```  
  
### <a name="parameters"></a>パラメーター  
 *ulCodePage*  
 プロパティ**ことにあります**です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="getambientdisplayasdefault"></a>  CComControlBase::GetAmbientDisplayAsDefault  
 取得**DISPID_AMBIENT_DISPLAYASDEFAULT**、あるフラグ**TRUE**場合は、コンテナーが既定のボタンにするには、このサイト内のコントロールをマークし、したがってボタン コントロールが描画するのには、自ら、太くフレームです。  
  
```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDisplayAsDefault`  
 プロパティ**DISPID_AMBIENT_DISPLAYASDEFAULT**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientdisplayname"></a>  CComControlBase::GetAmbientDisplayName  
 取得**DISPID_AMBIENT_DISPLAYNAME**コンテナーがコントロールに指定した名前です。  
  
```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrDisplayName*  
 プロパティ**DISPID_AMBIENT_DISPLAYNAME**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientfont"></a>  CComControlBase::GetAmbientFont  
 取得、コンテナーへのポインターのアンビエント`IFont`インターフェイスです。  
  
```
HRESULT GetAmbientFont(IFont** ppFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFont`  
 コンテナーへのポインターのアンビエント[IFont](http://msdn.microsoft.com/library/windows/desktop/ms680673)インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 プロパティが場合**NULL**、ポインターが**NULL**です。 ポインターがない場合**NULL**、呼び出し元は、ポインターを解放する必要があります。  
  
##  <a name="getambientfontdisp"></a>  CComControlBase::GetAmbientFontDisp  
 取得、コンテナーへのポインターのアンビエント**この**ディスパッチ インターフェイスです。  
  
```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFont`  
 コンテナーへのポインターのアンビエント[この](http://msdn.microsoft.com/library/windows/desktop/ms692695)ディスパッチ インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティが場合**NULL**、ポインターが**NULL**です。 ポインターがない場合**NULL**、呼び出し元は、ポインターを解放する必要があります。  
  
##  <a name="getambientforecolor"></a>  CComControlBase::GetAmbientForeColor  
 取得**DISPID_AMBIENT_FORECOLOR**、コンテナーによって定義されている、すべてのコントロールのアンビエント前景色。  
  
```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *前景色*  
 プロパティ**DISPID_AMBIENT_FORECOLOR**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientlocaleid"></a>  CComControlBase::GetAmbientLocaleID  
 取得**DISPID_AMBIENT_LOCALEID**、コンテナーによって使用される言語の識別子。  
  
```
HRESULT GetAmbientLocaleID(LCID& lcid);
```  
  
### <a name="parameters"></a>パラメーター  
 `lcid`  
 プロパティ**DISPID_AMBIENT_LOCALEID**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 コントロールは、この識別子を使用して、さまざまな言語には、そのユーザー インターフェイスを調整することができます。  
  
##  <a name="getambientmessagereflect"></a>  CComControlBase::GetAmbientMessageReflect  
 取得**DISPID_AMBIENT_MESSAGEREFLECT**、コンテナーがウィンドウのメッセージを受信するかどうかを示すフラグ (など`WM_DRAWITEM`) イベントとして。  
  
```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```  
  
### <a name="parameters"></a>パラメーター  
 `bMessageReflect`  
 プロパティ**DISPID_AMBIENT_MESSAGEREFLECT**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientpalette"></a>  CComControlBase::GetAmbientPalette  
 取得**DISPID_AMBIENT_PALETTE**コンテナーのアクセスに使用される、`HPALETTE`です。  
  
```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 `hPalette`  
 プロパティ**DISPID_AMBIENT_PALETTE**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientproperty"></a>  CComControlBase::GetAmbientProperty  
 指定されたコンテナーのプロパティを取得`dispid`です。  
  
```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 取得するコンテナーのプロパティの識別子。  
  
 `var`  
 プロパティを受け取る変数です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 ATL には、一連の特定のプロパティを取得するヘルパー関数が提供されている[用意されています](#getambientbackcolor)です。 適切なメソッドがないの場合を使用して`GetAmbientProperty`です。  
  
##  <a name="getambientrighttoleft"></a>  CComControlBase::GetAmbientRightToLeft  
 取得**DISPID_AMBIENT_RIGHTTOLEFT**方向、コンテナーによってコンテンツが表示されます。  
  
```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```  
  
### <a name="parameters"></a>パラメーター  
 *bRightToLeft*  
 プロパティ**DISPID_AMBIENT_RIGHTTOLEFT**です。 設定**TRUE**コンテンツが右から左へ表示される場合**FALSE**左右側に表示される場合。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="getambientscaleunits"></a>  CComControlBase::GetAmbientScaleUnits  
 取得**DISPID_AMBIENT_SCALEUNITS**コンテナーのアンビエント単位数 (インチやセンチメートル) などのラベル付けが表示されます。  
  
```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrScaleUnits*  
 プロパティ**DISPID_AMBIENT_SCALEUNITS**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientshowgrabhandles"></a>  CComControlBase::GetAmbientShowGrabHandles  
 取得**DISPID_AMBIENT_SHOWGRABHANDLES**コンテナーがアクティブなときにハンドルを表示するコントロールを許可するかどうかを示すフラグ。  
  
```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShowGrabHandles*  
 プロパティ**DISPID_AMBIENT_SHOWGRABHANDLES**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientshowhatching"></a>  CComControlBase::GetAmbientShowHatching  
 取得**DISPID_AMBIENT_SHOWHATCHING**コンテナーがコントロールのユーザー インターフェイスがアクティブなとき、ハッチ パターンを持つ自体を表示するコントロールを許可するかどうかを示すフラグ。  
  
```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShowHatching*  
 プロパティ**DISPID_AMBIENT_SHOWHATCHING**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambientsupportsmnemonics"></a>  CComControlBase::GetAmbientSupportsMnemonics  
 取得**DISPID_AMBIENT_SUPPORTSMNEMONICS**コンテナーがキーボードのニーモニックをサポートしているかどうかを示しますフラグ。  
  
```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```  
  
### <a name="parameters"></a>パラメーター  
 *bSupportsMnemonics*  
 プロパティ**DISPID_AMBIENT_SUPPORTSMNEMONICS**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambienttextalign"></a>  CComControlBase::GetAmbientTextAlign  
 取得**DISPID_AMBIENT_TEXTALIGN**コンテナーで優先されるテキストの配置: 一般的な配置 (数値、テキストを左) の場合は 0、左揃えの場合は 1、2 を中央揃え、および右揃えの 3 です。  
  
```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 *nTextAlign*  
 プロパティ**DISPID_AMBIENT_TEXTALIGN**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getambienttoptobottom"></a>  CComControlBase::GetAmbientTopToBottom  
 取得**DISPID_AMBIENT_TOPTOBOTTOM**方向、コンテナーによってコンテンツが表示されます。  
  
```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```  
  
### <a name="parameters"></a>パラメーター  
 *bTopToBottom*  
 プロパティ**DISPID_AMBIENT_TOPTOBOTTOM**です。 設定**TRUE**テキストが表示されている場合上から下に向かって、 **FALSE**表示されている場合下から上 です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="getambientuidead"></a>  CComControlBase::GetAmbientUIDead  
 取得**DISPID_AMBIENT_UIDEAD**コンテナーに、コントロール ユーザー インターフェイスの動作に応答するかどうかを示すフラグ。  
  
```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```  
  
### <a name="parameters"></a>パラメーター  
 *bUIDead*  
 プロパティ**DISPID_AMBIENT_UIDEAD**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 場合**TRUE**コントロールは応答しません。 このフラグに関係なく適用されます、 **DISPID_AMBIENT_USERMODE**フラグ。 参照してください[CComControlBase::GetAmbientUserMode](#getambientusermode)です。  
  
##  <a name="getambientusermode"></a>  CComControlBase::GetAmbientUserMode  
 取得**DISPID_AMBIENT_USERMODE**、コンテナーが実行モードであるかどうかを示すフラグ ( **TRUE**) デザイン モードまたは ( **FALSE**)。  
  
```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `bUserMode`  
 プロパティ**DISPID_AMBIENT_USERMODE**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
##  <a name="getdirty"></a>  CComControlBase::GetDirty  
 データ メンバーの値を返します`m_bRequiresSave`です。  
  
```
BOOL GetDirty();
```  
  
### <a name="return-value"></a>戻り値  
 データ メンバーの値を返します[m_bRequiresSave](#m_brequiressave)です。  
  
### <a name="remarks"></a>コメント  
 使用してこの値を設定[CComControlBase::SetDirty](#setdirty)です。  
  
##  <a name="getzoominfo"></a>  CComControlBase::GetZoomInfo  
 取得、x と y の分子とズームの倍率の分母の値の有効なコントロールの埋め込み先編集します。  
  
```
void GetZoomInfo(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>パラメーター  
 `di`  
 倍率の分子と分母を保持する構造体。 詳細については、次を参照してください。 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)です。  
  
### <a name="remarks"></a>コメント  
 ズームの倍率は、現在の大きさにコントロールの自然なサイズの比率です。  
  
##  <a name="inplaceactivate"></a>  CComControlBase::InPlaceActivate  
 動詞には、状態を非アクティブ状態から移行するコントロールをさせます`iVerb`を示します。  
  
```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 によって実行されるアクションを示す値[IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb)です。  
  
 *prcPosRect*  
 インプレースでコントロールの位置を指すポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 アクティブ化する前にこのメソッドを確認コントロール クライアント サイト、チェック コントロールの量が表示されて、親ウィンドウのコントロールの位置を取得します。 コントロールをアクティブにした後、このメソッドはコントロールのユーザー インターフェイスをアクティブにし、コントロールを表示するコンテナーに通知。  
  
 このメソッドも取得、 `IOleInPlaceSite`、**処理**、または**IOleInPlaceSiteWindowless**コントロールのインターフェイス ポインターコントロールクラスのデータメンバー内に格納および[は](#m_spinplacesite)します。 コントロール クラスのデータ メンバー [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)、 [CComControlBase::m_bWndLess](#m_bwndless)、 [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)、および[各](#m_bnegotiatedwnd)必要に応じて、true に設定されます。  
  
##  <a name="internalgetsite"></a>  CComControlBase::InternalGetSite  
 識別されたインターフェイスへのポインターのコントロール サイトを照会するには、このメソッドを呼び出します。  
  
```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```  
  
### <a name="parameters"></a>パラメーター  
 `riid`  
 返す必要があるインターフェイス ポインターの IID`ppUnkSite`です。  
  
 `ppUnkSite`  
 要求されたインターフェイス ポインターを受け取るポインター変数のアドレス`riid`です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 サイトで要求されたインターフェイスをサポートする場合は`riid`、により、ポインターが返される`ppUnkSite`です。 それ以外の場合、`ppUnkSite`は NULL に設定します。  
  
##  <a name="m_bautosize"></a>  CComControlBase::m_bAutoSize  
 コントロールが他の任意のサイズを変更できないことを示すフラグです。  
  
```
unsigned m_bAutoSize:1;
```  
  
### <a name="remarks"></a>コメント  
 このフラグがオンになって`IOleObjectImpl::SetExtent`し、 **TRUE**、関数が返すと、 **E_FAIL**です。  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 追加する場合、**自動サイズ** オプションを選択、[ストック プロパティ](../../atl/reference/stock-properties-atl-control-wizard.md)ATL コントロール ウィザード、ウィザードのタブに自動的にコントロール クラスのこのデータ メンバーを作成、配置を作成およびプロパティのメソッドを取得、し、サポート[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)にプロパティが変更されたときに、コンテナーを自動的に通知します。  
  
##  <a name="m_bdrawfromnatural"></a>  CComControlBase::m_bDrawFromNatural  
 示すフラグ`IDataObjectImpl::GetData`と`CComControlBase::GetZoomInfo`からコントロールのサイズを設定する必要があります`m_sizeNatural`からではなく`m_sizeExtent`です。  
  
```
unsigned m_bDrawFromNatural:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bdrawgetdatainhimetric"></a>  CComControlBase::m_bDrawGetDataInHimetric  
 示すフラグ`IDataObjectImpl::GetData`描画するときに HIMETRIC 単位と単位を使用する必要があります。  
  
```
unsigned m_bDrawGetDataInHimetric:1;
```  
  
### <a name="remarks"></a>コメント  
 それぞれの論理 HIMETRIC 単位は 0.01 ミリメートルです。  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_binplaceactive"></a>  CComControlBase::m_bInPlaceActive  
 コントロールが、インプレース アクティブであることを示すフラグです。  
  
```
unsigned m_bInPlaceActive:1;
```  
  
### <a name="remarks"></a>コメント  
 つまり、コントロールが表示されると、そのウィンドウ、表示が、メニューおよびツールバーをアクティブなできない可能性があります。 `m_bUIActive`フラグは、メニューなどのコントロールのユーザー インターフェイスがアクティブでもことを示します。  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_binplacesiteex"></a>  CComControlBase::m_bInPlaceSiteEx  
 コンテナーのサポートを示すフラグ、**処理**インターフェイスと OCX96 およびちらつきなしのコントロールなどの機能を制御します。  
  
```
unsigned m_bInPlaceSiteEx:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 データ メンバー`m_spInPlaceSite`を指す、[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461)、または[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)の値に応じて、インターフェイス、`m_bWndLess`と`m_bInPlaceSiteEx`フラグ。 (データ メンバー`m_bNegotiatedWnd`する必要があります**TRUE**の`m_spInPlaceSite`を有効にするポインター)。  
  
 場合`m_bWndLess`は**FALSE**と`m_bInPlaceSiteEx`は**TRUE**、`m_spInPlaceSite`は、**処理**インターフェイス ポインター。 参照してください[は、「](#m_spinplacesite)これら 3 つのデータ メンバーの間でリレーションシップを示すテーブルにします。  
  
##  <a name="m_bnegotiatedwnd"></a>  各  
 (ちらつきなしでウィンドウ コントロールなど)、OCX96 コントロールの機能のサポートのコンテナーとコントロールがネゴシエートされるかどうか、およびコントロールでのウィンドウまたはウィンドウなしがかどうかを示すフラグです。  
  
```
unsigned m_bNegotiatedWnd:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 `m_bNegotiatedWnd`フラグである必要があります**TRUE**の`m_spInPlaceSite`を有効にするポインター。  
  
##  <a name="m_brecomposeonresize"></a>  CComControlBase::m_bRecomposeOnResize  
 コントロールがコンテナーには、コントロールの表示サイズが変更されたときに、プレゼンテーションを再構成することを示すフラグです。  
  
```
unsigned m_bRecomposeOnResize:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 このフラグがオンになって[IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent)し、 **TRUE**、`SetExtent`の変更の表示のコンテナーに通知します。 このフラグが設定されている場合、 **OLEMISC_RECOMPOSEONRESIZE**ビット、[入ります](http://msdn.microsoft.com/library/windows/desktop/ms678497)列挙型を設定することも必要があります。  
  
##  <a name="m_brequiressave"></a>  CComControlBase::m_bRequiresSave  
 最後に保存された後、コントロールが変更を示すフラグします。  
  
```
unsigned m_bRequiresSave:1;
```  
  
### <a name="remarks"></a>コメント  
 値`m_bRequiresSave`で設定できる[CComControlBase::SetDirty](#setdirty)されで取得された[CComControlBase::GetDirty](#getdirty)です。  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bresizenatural"></a>  CComControlBase::m_bResizeNatural  
 コントロールが本来のエクステント (スケールなし物理サイズ) のサイズを変更することを示すフラグ、コンテナーにコントロールの表示サイズが変更されたとき。  
  
```
unsigned m_bResizeNatural:1;
```  
  
### <a name="remarks"></a>コメント  
 このフラグがオンになって`IOleObjectImpl::SetExtent`し、 **TRUE**に渡されたサイズ`SetExtent`に割り当てられている`m_sizeNatural`です。  
  
 渡されたサイズ`SetExtent`に常に割り当てられた`m_sizeExtent`の値に関係なく、`m_bResizeNatural`です。  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_buiactive"></a>  CComControlBase::m_bUIActive  
 メニューやツールバーなどのコントロールのユーザー インターフェイスを示すフラグがアクティブです。  
  
```
unsigned m_bUIActive:1;
```  
  
### <a name="remarks"></a>コメント  
 `m_bInPlaceActive`フラグは、コントロールがアクティブにできたら、それがあることを示しますがアクティブで、ユーザー インターフェイス。  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_busingwindowrgn"></a>  CComControlBase::m_bUsingWindowRgn  
 コントロールは、コンテナーが指定したウィンドウ領域の使用を示すフラグします。  
  
```
unsigned m_bUsingWindowRgn:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bwasoncewindowless"></a>  CComControlBase::m_bWasOnceWindowless  
 コントロール ウィンドウなし、されましたが、可能性がありますでなくてもかまいませんウィンドウなし今すぐを示すフラグします。  
  
```
unsigned m_bWasOnceWindowless:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bwindowonly"></a>  CComControlBase::m_bWindowOnly  
 コンテナーは、ウィンドウなしのコントロールをサポートしている場合でも、コントロールはウィンドウを持つできるかを示すフラグです。  
  
```
unsigned m_bWindowOnly:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bwndless"></a>  CComControlBase::m_bWndLess  
 コントロールはウィンドウなしを示すフラグします。  
  
```
unsigned m_bWndLess:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 データ メンバー`m_spInPlaceSite`を指す、[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461)、または[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)の値に応じて、インターフェイス、`m_bWndLess`と[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)フラグ。 (データ メンバー[各](#m_bnegotiatedwnd)する必要があります**TRUE**の[は](#m_spinplacesite)を有効にするポインター)。  
  
 場合`m_bWndLess`は**TRUE**、`m_spInPlaceSite`は、 **IOleInPlaceSiteWindowless**インターフェイス ポインター。 参照してください[は](#m_spinplacesite)のこれらのデータ メンバーの完全な関係を示す表。  
  
##  <a name="m_hwndcd"></a>  CComControlBase::m_hWndCD  
 コントロールに関連付けられているウィンドウ ハンドルへの参照が含まれています。  
  
```
HWND& m_hWndCD;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_nfreezeevents"></a>  CComControlBase::m_nFreezeEvents  
 回数のカウント コンテナー イベントを固定した (イベントを承諾することを拒否) イベント (イベントの受け入れ) の中間の凍結解除なし。  
  
```
short m_nFreezeEvents;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_rcpos"></a>  CComControlBase::m_rcPos  
 コンテナーの座標で表される、コントロールの位置をピクセル単位で。  
  
```
RECT m_rcPos;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_sizeextent"></a>  この  
 HIMETRIC 単位 (各単位は 0.01 ミリメートル) 特定のディスプレイのコントロールの範囲。  
  
```
SIZE m_sizeExtent;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 このサイズは、表示してスケーリングされます。 コントロールの物理サイズで指定する、`m_sizeNatural`データ メンバーは固定されているとします。  
  
 サイズを変換するには、グローバル関数でピクセルに[AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)です。  
  
##  <a name="m_sizenatural"></a>  CComControlBase::m_sizeNatural  
 HIMETRIC 単位 (各単位は 0.01 ミリメートル) 内のコントロールの物理サイズ。  
  
```
SIZE m_sizeNatural;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 サイズの中に、このサイズは固定されて`m_sizeExtent`ディスプレイでのスケールが設定されます。  
  
 サイズを変換するには、グローバル関数でピクセルに[AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)です。  
  
##  <a name="m_spadvisesink"></a>  アドバイズ  
 コンテナー上のアドバイザリ コネクションを直接のポインター (コンテナーの[IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513))。  
  
```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_spambientdispatch"></a>  CComControlBase::m_spAmbientDispatch  
 A`CComDispatchDriver`オブジェクトを取得し、オブジェクトのプロパティを設定することができます、`IDispatch`ポインター。  
  
```
CComDispatchDriver m_spAmbientDispatch;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_spclientsite"></a>  CComControlBase::m_spClientSite  
 コンテナー内のコントロールのクライアントのサイトへのポインター。  
  
```
CComPtr<IOleClientSite>
    m_spClientSite;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_spdataadviseholder"></a>  CComControlBase::m_spDataAdviseHolder  
 データ オブジェクト間のアドバイザリ コネクションをアドバイズ シンクすることを意味標準を提供します。  
  
```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 データ オブジェクトはデータを転送することができを実装するコントロール[IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)、そのメソッドがデータの形式と転送メディアを指定します。  
  
 インターフェイス`m_spDataAdviseHolder`を実装する、 [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579)と[IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448)メソッドを設定し、コンテナーにアドバイザリ コネクションを削除します。 コントロールのコンテナーがサポートすることによりアドバイズ シンクを実装する必要があります、 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)インターフェイスです。  
  
##  <a name="m_spinplacesite"></a>  は  
 コンテナーへのポインター[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461)、または[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)インターフェイス ポインター。  
  
```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 `m_spInPlaceSite`ポインターが有効な場合にのみ、 [m_bNegotiatedWnd](#m_bnegotiatedwnd)フラグは**TRUE**です。  
  
 次の表に、どのように`m_spInPlaceSite`ポインターの種類によって異なります、 [m_bWndLess](#m_bwndless)と[m_bInPlaceSiteEx](#m_binplacesiteex)データ メンバーのフラグ。  
  
|型は、「|m_bWndLess 値|m_bInPlaceSiteEx 値|  
|---------------------------|-----------------------|-----------------------------|  
|**IOleInPlaceSiteWindowless**|**場合は TRUE。**|**TRUE**または**FALSE**|  
|**この処理**|**FALSE**|**場合は TRUE。**|  
|`IOleInPlaceSite`|**FALSE**|**FALSE**|  
  
##  <a name="m_spoleadviseholder"></a>  CComControlBase::m_spOleAdviseHolder  
 アドバイザリ コネクションを保持するための標準的な実装を提供します。  
  
```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロール クラス内のこのデータ メンバーを使用するには、必要がありますとして宣言するデータ メンバーをコントロール クラスでします。 基本クラスの共用体で宣言されているために、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 インターフェイス`m_spOleAdviseHolder`を実装する、 [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573)と[IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749)メソッドを設定し、コンテナーにアドバイザリ コネクションを削除します。 コントロールのコンテナーがサポートすることによりアドバイズ シンクを実装する必要があります、 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)インターフェイスです。  
  
##  <a name="ondraw"></a>  CComControlBase::OnDraw  
 コントロールを描画するには、このメソッドをオーバーライドします。  
  
```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>パラメーター  
 `di`  
 参照、 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)描画縦横比、コントロールの境界などの描画の情報を格納する構造体かの描画の最適化するかどうかとします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 既定値`OnDraw`を削除、デバイス コンテキストを復元または何も行われません設定されているフラグによって[CComControlBase::OnDrawAdvanced](#ondrawadvanced)です。  
  
 `OnDraw`メソッドは ATL コントロール ウィザードを使用して、コントロールを作成するときに、自動的に、コントロール クラスに追加します。 ウィザードの既定`OnDraw`"ATL 8.0"というラベルを持つ四角形を描画します。  
  
### <a name="example"></a>例  
 例を参照して[CComControlBase::GetAmbientAppearance](#getambientappearance)です。  
  
##  <a name="ondrawadvanced"></a>  CComControlBase::OnDrawAdvanced  
 既定値`OnDrawAdvanced`描画、正規化されたデバイス コンテキストを準備し、コントロール クラスの`OnDraw`メソッドです。  
  
```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>パラメーター  
 `di`  
 参照、 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)描画縦横比、コントロールの境界などの描画の情報を格納する構造体かの描画の最適化するかどうかとします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 標準化なしコンテナーによって渡されたデバイス コンテキストをそのまま使用する場合は、このメソッドをオーバーライドします。  
  
 参照してください[CComControlBase::OnDraw](#ondraw)詳細についてはします。  
  
##  <a name="onkillfocus"></a>  CComControlBase::OnKillFocus  
 コントロール、インプレース アクティブと有効なコントロール サイトを持つそのがコンテナーに通知コントロールがフォーカスを失ったことを確認します。  
  
```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMsg`  
 予約済み。  
  
 `wParam`  
 予約済み。  
  
 `lParam`  
 予約済み。  
  
 `bHandled`  
 ウィンドウ メッセージが正常に処理されたかどうかを示すフラグです。 既定値は、`FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
##  <a name="onmouseactivate"></a>  CComControlBase::OnMouseActivate  
 UI がユーザー モードでは、し、コントロールをアクティブにすることを確認します。  
  
```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMsg`  
 予約済み。  
  
 `wParam`  
 予約済み。  
  
 `lParam`  
 予約済み。  
  
 `bHandled`  
 ウィンドウ メッセージが正常に処理されたかどうかを示すフラグです。 既定値は、`FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
##  <a name="onpaint"></a>  CComControlBase::OnPaint  
 描画するため、コンテナーを準備し、コントロールのクライアント領域の取得、コントロール クラスの`OnDrawAdvanced`メソッドです。  
  
```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMsg`  
 予約済み。  
  
 `wParam`  
 既存の HDC です。  
  
 `lParam`  
 予約済み。  
  
 `lResult`  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`wParam`が NULL でない`OnPaint`有効 HDC を含みの代わりに使用を前提としています[CComControlBase::m_hWndCD](#m_hwndcd)です。  
  
##  <a name="onsetfocus"></a>  CComControlBase::OnSetFocus  
 コントロール、インプレース アクティブと有効なコントロール サイトを持つそのがコンテナー コントロールに通知の確認は、フォーカスを得てきました。  
  
```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMsg`  
 予約済み。  
  
 `wParam`  
 予約済み。  
  
 `lParam`  
 予約済み。  
  
 `bHandled`  
 ウィンドウ メッセージが正常に処理されたかどうかを示すフラグです。 既定値は、`FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがフォーカスを受け取ったことをコンテナーに通知を送信します。  
  
##  <a name="pretranslateaccelerator"></a>  CComControlBase::PreTranslateAccelerator  
 独自のキーボード アクセラレータのハンドラーを提供するには、このメソッドをオーバーライドします。  
  
```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 予約済み。  
  
 *hRet*  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 既定では返します**FALSE**です。  
  
##  <a name="sendonclose"></a>  CComControlBase::SendOnClose  
 コントロールが閉じられたことアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。  
  
```
HRESULT SendOnClose();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがそのアドバイズ シンクを閉じている通知を送信します。  
  
##  <a name="sendondatachange"></a>  CComControlBase::SendOnDataChange  
 コントロールのデータが変更されたアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。  
  
```
HRESULT SendOnDataChange(DWORD advf = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *advf*  
 アドバイス フラグを指定する方法への呼び出し[IAdviseSink::OnDataChange](http://msdn.microsoft.com/library/windows/desktop/ms687283)が行われます。 値は、 [ADVF](http://msdn.microsoft.com/library/windows/desktop/ms693742)列挙します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="sendonrename"></a>  CComControlBase::SendOnRename  
 コントロールに新しいモニカーがあること、アドバイズ保有者に登録されているすべてのアドバイズ シンクに通知します。  
  
```
HRESULT SendOnRename(IMoniker* pmk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pmk*  
 コントロールの新しいモニカーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールのモニカーが変更されたことを示す通知を送信します。  
  
##  <a name="sendonsave"></a>  CComControlBase::SendOnSave  
 コントロールが保存されているアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。  
  
```
HRESULT SendOnSave();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがデータを保存したことの通知を送信します。  
  
##  <a name="sendonviewchange"></a>  CComControlBase::SendOnViewChange  
 登録されているすべてのコントロールのビューが変更されたアドバイズ シンクに通知します。  
  
```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwAspect`  
 縦横またはコントロールのビューです。  
  
 *lindex*  
 変更されたビューの一部です。 -1 だけは有効です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 `SendOnViewChange` 呼び出し[IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337)です。 値だけ*lindex*ビュー全体が関心のあることを示す-1 は、現在サポートされています。  
  
##  <a name="setcontrolfocus"></a>  CComControlBase::SetControlFocus  
 設定またはコントロールの間にキーボード フォーカスを削除します。  
  
```
BOOL SetControlFocus(BOOL bGrab);
```  
  
### <a name="parameters"></a>パラメーター  
 *bGrab*  
 場合**TRUE**、呼び出し元のコントロールにキーボード フォーカスを設定します。 場合**FALSE**、フォーカスがあるものであれば、呼び出し元の管理からキーボード フォーカスを削除します。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**コントロールが正常にフォーカスを受け取る場合は、それ以外の場合、 **FALSE**です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ コントロール、Windows API 関数の[SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms646312)と呼びます。 ウィンドウなしのコントロールの[IOleInPlaceSiteWindowless::SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms679745)と呼びます。 この呼び出しでは、ウィンドウなしのコントロールがキーボード フォーカスを取得し、ウィンドウのメッセージに応答できます。  
  
##  <a name="setdirty"></a>  CComControlBase::SetDirty  
 データ メンバーを設定`m_bRequiresSave`の値に`bDirty`です。  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDirty`  
 データ メンバーの値[CComControlBase::m_bRequiresSave](#m_brequiressave)です。  
  
### <a name="remarks"></a>コメント  
 **Setdirty (true)** フラグを最後に保存してから、コントロールが変更されたことを呼び出す必要があります。 値`m_bRequiresSave`で取得[CComControlBase::GetDirty](#getdirty)です。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
