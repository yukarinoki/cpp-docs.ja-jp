---
title: クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
ms.openlocfilehash: 15cfa205337248181f02e6a1218d49e75bda58e6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748109"
---
# <a name="ccomcontrolbase-class"></a>クラス

このクラスには、ATL コントロールを作成および管理するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[コムコントロールベース::外観タイプ](#appearancetype)|`m_nAppearance`ストック プロパティの種類が**short**でない場合はオーバーライドします。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コントロールベース::ココムコントロールベース](#ccomcontrolbase)|コンストラクターです。|
|[コントロールベース::~CComコントロールベース](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロールインターフェイス::コントロールクエリインターフェイス](#controlqueryinterface)|要求されたインターフェイスへのポインターを取得します。|
|[:Dオーズバーブアクティブ](#doesverbactivate)|コントロール*のユーザー*`IOleObjectImpl::DoVerb`インターフェイスがアクティブになる (iVerb がOLEIVERB_UIACTIVATEに等しい)、ユーザーがコントロールをダブルクリックしたときのアクションを定義する *(iVerb*がOLEIVERB_PRIMARY*iVerb*に等しい) コントロールを表示するか *(iVerb*がOLEIVERB_SHOWに等しい)、コントロールをアクティブにする *(iVerb*がOLEIVERB_INPLACEACTIVATE)。|
|[:DオースブバーブUIアクティベート](#doesverbuiactivate)|で`IOleObjectImpl::DoVerb`使用される*iVerb*パラメーターによってコントロールのユーザー インターフェイスがアクティブ化され、TRUE が返されることを確認します。|
|[:Dプロパティ](#doverbproperties)|コントロールのプロパティ ページを表示します。|
|[コントロールベース::FireViewチェンジ](#fireviewchange)|コントロールを再描画するようにコンテナーに通知するか、コントロールのビューが変更されたことを登録されたアドバイス シンクに通知します。|
|[コムコントロールベース::ゲットアンビエントアピアランス](#getambientappearance)|コントロールの現在の外観設定であるDISPID_AMBIENT_APPEARANCEを取得します。|
|[コムコントロールベース::ゲットアンビエントオートクリップ](#getambientautoclip)|DISPID_AMBIENT_AUTOCLIPを取得します。|
|[コムコントロールベース::アンビエントバックカラー](#getambientbackcolor)|コンテナーで定義されたすべてのコントロールのアンビエント背景色であるDISPID_AMBIENT_BACKCOLORを取得します。|
|[コムコントロールベース::ゲットアンビエントチャルセット](#getambientcharset)|コンテナーによって定義されたすべてのコントロールのアンビエント文字セットであるDISPID_AMBIENT_CHARSETを取得します。|
|[をクリックします。](#getambientcodepage)|コンテナーによって定義されたすべてのコントロールのアンビエント文字セットであるDISPID_AMBIENT_CODEPAGEを取得します。|
|[デフォルトでアンビエントディスプレイを表示します。](#getambientdisplayasdefault)|コンテナーが既定のボタンとしてこのサイトのコントロールをマークしている場合はtrueDISPID_AMBIENT_DISPLAYASDEFAULTを取得し、したがって、ボタン コントロールは、より太いフレームで自分自身を描画する必要があります。|
|[を使用します。](#getambientdisplayname)|コンテナーがコントロールに指定した名前DISPID_AMBIENT_DISPLAYNAMEを取得します。|
|[クコムコントロールベース::ゲットアンビエントフォント](#getambientfont)|コンテナーのアンビエント`IFont`インターフェイスへのポインターを取得します。|
|[::アンビエントフォントディス](#getambientfontdisp)|コンテナーのアンビエント`IFontDisp`ディスパッチ インターフェイスへのポインターを取得します。|
|[コムコントロールベース::ゲットアンビエントフォーレカラー](#getambientforecolor)|コンテナーで定義された、すべてのコントロールのアンビエント前景色であるDISPID_AMBIENT_FORECOLORを取得します。|
|[を設定します。](#getambientlocaleid)|コンテナーで使用される言語の識別子であるDISPID_AMBIENT_LOCALEIDを取得します。|
|[を返します。](#getambientmessagereflect)|WM_DRAWITEM DISPID_AMBIENT_MESSAGEREFLECTを取得します。|
|[コントロールベース::ゲットアンビエントパレット](#getambientpalette)|コンテナの HPALETTE にアクセスするために使用されるDISPID_AMBIENT_PALETTEを取得します。|
|[プロパティを取得します。](#getambientproperty)|*id*で指定されたコンテナ プロパティを取得します。|
|[コムコントロールベース::ゲットアンビエントライトを左に](#getambientrighttoleft)|コンテナーによって表示されるコンテンツの方向であるDISPID_AMBIENT_RIGHTTOLEFTを取得します。|
|[クコムコントロールベース::アンビエントスケールユニット](#getambientscaleunits)|DISPID_AMBIENT_SCALEUNITS、ラベル表示用のコンテナーのアンビエント単位 (インチやセンチメートルなど) を取得します。|
|[コムコントロールベース::アンビエントショーグラブハンドル](#getambientshowgrabhandles)|DISPID_AMBIENT_SHOWGRABHANDLESを取得します。|
|[コムコントロールベース::ゲットアンビエントショーハッチング](#getambientshowhatching)|ui がアクティブな場合、コンテナーがハッチ パターンでコントロール自体を表示できるかどうかを示すフラグDISPID_AMBIENT_SHOWHATCHINGを取得します。|
|[コムコントロールベース::Getアンビエントサポートムネモニック](#getambientsupportsmnemonics)|DISPID_AMBIENT_SUPPORTSMNEMONICSを取得します。|
|[コントロールベース::アンビエントテキスト整列](#getambienttextalign)|DISPID_AMBIENT_TEXTALIGN、コンテナが推奨するテキストの配置を取得します: 0 (右の数字、左のテキスト)、左揃えの場合は 1、中央揃えの場合は 2、右揃えの場合は 3。|
|[コムコントロールベース::ゲットアンビエントトップトボトム](#getambienttoptobottom)|DISPID_AMBIENT_TOPTOBOTTOM、コンテンツがコンテナーによって表示される方向を取得します。|
|[コムコントロールベース::ゲットアンビエントUIデッド](#getambientuidead)|DISPID_AMBIENT_UIDEADを取得します。|
|[を使用します。](#getambientusermode)|DISPID_AMBIENT_USERMODE、コンテナーが実行モード (TRUE) またはデザイン モード (FALSE) かどうかを示すフラグを取得します。|
|[ココムコントロールベース::ゲットダーティ](#getdirty)|データ メンバ`m_bRequiresSave`の値を返します。|
|[コントロールベース::ゲットズームインフォ](#getzoominfo)|インプレイス編集用にアクティブ化されたコントロールのズーム係数の分子と分母の x および y 値を取得します。|
|[ココムコントロールベース::インプレースアクティベート](#inplaceactivate)|コントロールが非アクティブ状態から*iVerb*の動詞が示す状態に遷移します。|
|[コントロールベース::内部ゲットサイト](#internalgetsite)|指定したインターフェイスへのポインターをコントロール サイトに照会します。|
|[ココムコントロールベース::オンドロー](#ondraw)|コントロールを描画するには、このメソッドをオーバーライドします。|
|[ココムコントロールベース::オンドローアドバンスド](#ondrawadvanced)|既定`OnDrawAdvanced`では、描画用に正規化されたデバイス コンテキストを準備し、コントロール クラスの`OnDraw`メソッドを呼び出します。|
|[ココムコントロールベース::オンキルフォーカス](#onkillfocus)|コントロールがインプレース アクティブで、有効なコントロール サイトを持っていることを確認し、コントロールがフォーカスを失ったことをコンテナーに通知します。|
|[ココムコントロールベース::マウス活性化](#onmouseactivate)|UI がユーザー モードであることを確認し、コントロールをアクティブにします。|
|[コムコントロールベース::オンペイント](#onpaint)|描画用のコンテナーを準備し、コントロールのクライアント領域を取得してから、コントロール クラスの`OnDraw`メソッドを呼び出します。|
|[コントロールベース::オンセットフォーカス](#onsetfocus)|コントロールがインプレース アクティブで、有効なコントロール サイトを持っていることを確認し、コントロールがフォーカスを得たことをコンテナーに通知します。|
|[コントロールベース::P再翻訳アクセラレータ](#pretranslateaccelerator)|独自のキーボード アクセラレータ ハンドラーを提供するには、このメソッドをオーバーライドします。|
|[コントロールベース::センドオンクローズ](#sendonclose)|コントロールが閉じられたことをアドバイス ホルダーに登録されているすべてのアドバイザリ シンクに通知します。|
|[コントロールベース::センドオンデータチェンジ](#sendondatachange)|コントロール データが変更されたことをアドバイスホルダーに登録されているすべてのアドバイザリ シンクに通知します。|
|[コントロールベース::センドオンリネーム](#sendonrename)|コントロールに新しいモニカーがあることを通知ホルダーに登録されているすべてのアドバイザリ シンクに通知します。|
|[コントロールベース::センドオンセーブ](#sendonsave)|コントロールが保存されたことを通知ホルダーに登録されているすべてのアドバイザリ シンクに通知します。|
|[コントロールベース::センドオンビューチェンジ](#sendonviewchange)|コントロールのビューが変更されたことを、登録されているすべてのアドバイザリ シンクに通知します。|
|[コントロールベース::セットコントロールフォーカス](#setcontrolfocus)|コントロールに対するキーボード フォーカスの設定または削除を行います。|
|[ココムコントロールベース::セットダーティ](#setdirty)|データ メンバ`m_bRequiresSave`を*bDirty*の値に設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コムコントロールベース::m_bAutoSize](#m_bautosize)|コントロールを他のサイズにできないことを示すフラグ。|
|[コムコントロールベース::m_bDrawFromNatural](#m_bdrawfromnatural)|を`IDataObjectImpl::GetData`示すフラグ`CComControlBase::GetZoomInfo`を指定し、コントロール`m_sizeNatural`のサイズを`m_sizeExtent`からではなくから設定する必要があります。|
|[コムコントロールベース::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|描画時に`IDataObjectImpl::GetData`、ピクセルではなく HIMETRIC 単位を使用することを示すフラグです。|
|[コムコントロールベース::m_bInPlaceActive](#m_binplaceactive)|コントロールがインプレース アクティブであることを示すフラグ。|
|[コムコントロールベース::m_bInPlaceSiteEx](#m_binplacesiteex)|コンテナーがインターフェイスと OCX96 コントロール機能 (`IOleInPlaceSiteEx`ウィンドウなしコントロールやちらつきのないコントロールなど) をサポートするフラグ。|
|[コムコントロールベース::m_bNegotiatedWnd](#m_bnegotiatedwnd)|コントロールが OCX96 コントロール機能 (ちらつきのないコントロールやウィンドウなしのコントロールなど) のサポートについてコンテナーとネゴシエートしたかどうか、およびコントロールがウィンドウ表示またはウィンドウなしかどうかを示すフラグです。|
|[コムコントロールベース::m_bRecomposeOnResize](#m_brecomposeonresize)|コンテナーがコントロールの表示サイズを変更したときに、コントロールがプレゼンテーションを再構成することを示すフラグ。|
|[コムコントロールベース::m_bRequiresSave](#m_brequiressave)|コントロールが最後に保存されてから変更されたことを示すフラグ。|
|[コムコントロールベース::m_bResizeNatural](#m_bresizenatural)|コンテナーがコントロールの表示サイズを変更したときに、コントロールの自然な範囲 (スケーリングされていない物理サイズ) のサイズを変更することを示すフラグ。|
|[コムコントロールベース::m_bUIActive](#m_buiactive)|メニューやツールバーなどのコントロールのユーザー インターフェイスがアクティブであることを示すフラグ。|
|[コムコントロールベース::m_bUsingWindowRgn](#m_busingwindowrgn)|コントロールがコンテナー指定のウィンドウ領域を使用しているフラグ。|
|[コムコントロールベース::m_bWasOnceWindowless](#m_bwasoncewindowless)|コントロールがウィンドウなしであることを示すフラグが、現在ウィンドウなしである場合とない場合があります。|
|[コムコントロールベース::m_bWindowOnly](#m_bwindowonly)|コンテナーがウィンドウなしのコントロールをサポートしている場合でも、コントロールをウィンドウ化する必要があることを示すフラグ。|
|[コムコントロールベース::m_bWndLess](#m_bwndless)|コントロールがウィンドウなしであることを示すフラグ。|
|[コムコントロールベース::m_hWndCD](#m_hwndcd)|コントロールに関連付けられているウィンドウ ハンドルへの参照を格納します。|
|[コムコントロールベース::m_nFreezeEvents](#m_nfreezeevents)|イベントの間に発生する雪解け (イベントの受け入れ) せずに、コンテナーがイベントを凍結した回数のカウントです (イベントの受け入れ)。|
|[コムコントロールベース::m_rcPos](#m_rcpos)|コントロールの位置をピクセル単位で、コンテナーの座標で表します。|
|[コムコントロールベース::m_sizeExtent](#m_sizeextent)|特定のディスプレイの HIMETRIC 単位 (各単位は 0.01 ミリメートル) 単位のコントロールの範囲。|
|[コムコントロールベース::m_sizeNatural](#m_sizenatural)|HIMETRIC 単位でのコントロールの物理サイズ (各単位は 0.01 ミリメートル)。|
|[コムコントロールベース::m_spAdviseSink](#m_spadvisesink)|コンテナー (コンテナーの[IAdviseSink)](/windows/win32/api/objidl/nn-objidl-iadvisesink)に対するアドバイザリ接続への直接ポインター。|
|[コムコントロールベース::m_spAmbientDispatch](#m_spambientdispatch)|ポインターを介してコンテナーのプロパティを取得および設定できる`CComDispatchDriver`オブジェクト。 `IDispatch`|
|[コムコントロールベース::m_spClientSite](#m_spclientsite)|コンテナー内のコントロールのクライアント サイトへのポインター。|
|[コムコントロールベース::m_spDataAdviseHolder](#m_spdataadviseholder)|データ オブジェクトとアドバイズ シンク間のアドバイザリ接続を保持するための標準的な手段を提供します。|
|[コムコントロールベース::m_spInPlaceSite](#m_spinplacesite)|コンテナーの[IOleInPlace サイト](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)、または[IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)へのポインター[ウィンドウレス](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)インターフェイス ポインター。|
|[コムコントロールベース::m_spOleAdviseHolder](#m_spoleadviseholder)|アドバイザリコネクションを保持する方法の標準的な実装を提供します。|

## <a name="remarks"></a>解説

このクラスには、ATL コントロールを作成および管理するためのメソッドが用意されています。 [から](../../atl/reference/ccomcontrol-class.md)派生するクラスです`CComControlBase`。 ATL コントロール ウィザードを使用して標準コントロールまたは DHTML コントロールを作成すると、ウィザードによってクラスが`CComControlBase`から自動的に派生します。

コントロールの作成の詳細については[、「ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)」を参照してください。 ATL プロジェクト ウィザードの詳細については、ATL[プロジェクトの作成に関する記事を](../../atl/reference/creating-an-atl-project.md)参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="ccomcontrolbaseappearancetype"></a><a name="appearancetype"></a>コムコントロールベース::外観タイプ

`m_nAppearance`ストック プロパティの種類が**short**でない場合はオーバーライドします。

```
typedef short AppearanceType;
```

### <a name="remarks"></a>解説

ATL コントロール ウィザード`m_nAppearance`は、short 型のストック プロパティを追加します。 別`AppearanceType`のデータ型を使用する場合はオーバーライドします。

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="ccomcontrolbase"></a>コントロールベース::ココムコントロールベース

コンストラクターです。

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
コントロールに関連付けられているウィンドウへのハンドル。

### <a name="remarks"></a>解説

コントロール サイズを 5080X5080 HIMETRIC 単位 (2"X2") に`CComControlBase`初期化し、データ メンバー値を NULL または FALSE に初期化します。

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="dtor"></a>コントロールベース::~CComコントロールベース

デストラクターです。

```
~CComControlBase();
```

### <a name="remarks"></a>解説

コントロールがウィンドウに表示されている場合`~CComControlBase`は[、DestroyWindow](/windows/win32/api/winuser/nf-winuser-destroywindow)を呼び出してコントロールを破棄します。

## <a name="ccomcontrolbasecontrolqueryinterface"></a><a name="controlqueryinterface"></a>コントロールインターフェイス::コントロールクエリインターフェイス

要求されたインターフェイスへのポインターを取得します。

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
要求されているインターフェイスの GUID。

*Ppv*<br/>
*iid*で識別されるインターフェイス ポインタへのポインタ、 またはインターフェイスが見つからない場合は NULL。

### <a name="remarks"></a>解説

COM マップ テーブル内のインターフェイスのみを処理します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

## <a name="ccomcontrolbasedoesverbactivate"></a><a name="doesverbactivate"></a>:Dオーズバーブアクティブ

コントロール*のユーザー*`IOleObjectImpl::DoVerb`インターフェイスがアクティブになる (iVerb がOLEIVERB_UIACTIVATEに等しい)、ユーザーがコントロールをダブルクリックしたときのアクションを定義する *(iVerb*がOLEIVERB_PRIMARY*iVerb*に等しい) コントロールを表示するか *(iVerb*がOLEIVERB_SHOWに等しい)、コントロールをアクティブにする *(iVerb*がOLEIVERB_INPLACEACTIVATE)。

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>パラメーター

*i動詞*<br/>
によって`DoVerb`実行されるアクションを示す値。

### <a name="return-value"></a>戻り値

*iVerb*がOLEIVERB_UIACTIVATE、OLEIVERB_PRIMARY、OLEIVERB_SHOW、またはOLEIVERB_INPLACEACTIVATEに等しい場合は TRUE を返します。それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドをオーバーライドして、独自のアクティブ化動詞を定義できます。

## <a name="ccomcontrolbasedoesverbuiactivate"></a><a name="doesverbuiactivate"></a>:DオースブバーブUIアクティベート

で`IOleObjectImpl::DoVerb`使用される*iVerb*パラメーターによってコントロールのユーザー インターフェイスがアクティブ化され、TRUE が返されることを確認します。

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>パラメーター

*i動詞*<br/>
によって`DoVerb`実行されるアクションを示す値。

### <a name="return-value"></a>戻り値

*iVerb*がOLEIVERB_UIACTIVATE、OLEIVERB_PRIMARY、OLEIVERB_SHOW、またはOLEIVERB_INPLACEACTIVATEに等しい場合は TRUE を返します。 それ以外の場合、メソッドは FALSE を返します。

## <a name="ccomcontrolbasedoverbproperties"></a><a name="doverbproperties"></a>:Dプロパティ

コントロールのプロパティ ページを表示します。

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>パラメーター

*プルポスレック*<br/>
予約済み。

*hwndParent*<br/>
コントロールを含むウィンドウのハンドル。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

## <a name="ccomcontrolbasefireviewchange"></a><a name="fireviewchange"></a>コントロールベース::FireViewチェンジ

コントロールを再描画するようにコンテナーに通知するか、コントロールのビューが変更されたことを登録されたアドバイス シンクに通知します。

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

コントロールがアクティブな場合 (コントロール クラス のデータ メンバー [CComControlBase::m_bInPlaceActive](#m_binplaceactive)が TRUE)、コントロール全体を再描画するコンテナーに通知します。 コントロールが非アクティブの場合は、コントロールのビューが変更されたことをコントロールの登録されたアドバイス シンク (コントロール クラスのデータ メンバー [CComControlBase::m_spAdviseSink](#m_spadvisesink)を通じて) に通知します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

## <a name="ccomcontrolbasegetambientappearance"></a><a name="getambientappearance"></a>コムコントロールベース::ゲットアンビエントアピアランス

コントロールの現在の外観設定であるDISPID_AMBIENT_APPEARANCEを取得します。

```
HRESULT GetAmbientAppearance(short& nAppearance);
```

### <a name="parameters"></a>パラメーター

*n外観*<br/>
プロパティDISPID_AMBIENT_APPEARANCE。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]

## <a name="ccomcontrolbasegetambientautoclip"></a><a name="getambientautoclip"></a>コムコントロールベース::ゲットアンビエントオートクリップ

DISPID_AMBIENT_AUTOCLIPを取得します。

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>パラメーター

*b自動クリップ*<br/>
プロパティはDISPID_AMBIENT_AUTOCLIP。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientbackcolor"></a><a name="getambientbackcolor"></a>コムコントロールベース::アンビエントバックカラー

コンテナーで定義されたすべてのコントロールのアンビエント背景色であるDISPID_AMBIENT_BACKCOLORを取得します。

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>パラメーター

*Backcolor*<br/>
プロパティDISPID_AMBIENT_BACKCOLOR。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientcharset"></a><a name="getambientcharset"></a>コムコントロールベース::ゲットアンビエントチャルセット

コンテナーによって定義されたすべてのコントロールのアンビエント文字セットであるDISPID_AMBIENT_CHARSETを取得します。

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>パラメーター

*を設定します。*<br/>
プロパティはDISPID_AMBIENT_CHARSET。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="ccomcontrolbasegetambientcodepage"></a><a name="getambientcodepage"></a>をクリックします。

コンテナーによって定義されるすべてのコントロールのアンビエント コード ページDISPID_AMBIENT_CODEPAGEを取得します。

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>パラメーター

*ウルコードページ*<br/>
プロパティDISPID_AMBIENT_CODEPAGE。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="ccomcontrolbasegetambientdisplayasdefault"></a><a name="getambientdisplayasdefault"></a>デフォルトでアンビエントディスプレイを表示します。

コンテナーが既定のボタンとしてこのサイトのコントロールをマークしている場合はtrueDISPID_AMBIENT_DISPLAYASDEFAULTを取得し、したがって、ボタン コントロールは、より太いフレームで自分自身を描画する必要があります。

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>パラメーター

*既定の表示*<br/>
プロパティはDISPID_AMBIENT_DISPLAYASDEFAULT。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientdisplayname"></a><a name="getambientdisplayname"></a>を使用します。

コンテナーがコントロールに指定した名前DISPID_AMBIENT_DISPLAYNAMEを取得します。

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>パラメーター

*表示名*<br/>
プロパティはDISPID_AMBIENT_DISPLAYNAME。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientfont"></a><a name="getambientfont"></a>クコムコントロールベース::ゲットアンビエントフォント

コンテナーのアンビエント`IFont`インターフェイスへのポインターを取得します。

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
コンテナーのアンビエント[IFont](/windows/win32/api/ocidl/nn-ocidl-ifont)インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

プロパティが NULL の場合、ポインターは NULL です。 ポインターが NULL でない場合、呼び出し元はポインターを解放する必要があります。

## <a name="ccomcontrolbasegetambientfontdisp"></a><a name="getambientfontdisp"></a>::アンビエントフォントディス

コンテナーのアンビエント`IFontDisp`ディスパッチ インターフェイスへのポインターを取得します。

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
コンテナーのアンビエント[IFontDisp](/windows/win32/api/ocidl/nn-ocidl-ifontdisp)ディスパッチ インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

プロパティが NULL の場合、ポインターは NULL です。 ポインターが NULL でない場合、呼び出し元はポインターを解放する必要があります。

## <a name="ccomcontrolbasegetambientforecolor"></a><a name="getambientforecolor"></a>コムコントロールベース::ゲットアンビエントフォーレカラー

コンテナーで定義された、すべてのコントロールのアンビエント前景色であるDISPID_AMBIENT_FORECOLORを取得します。

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>パラメーター

*前景色*<br/>
プロパティはDISPID_AMBIENT_FORECOLOR。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientlocaleid"></a><a name="getambientlocaleid"></a>を設定します。

コンテナーで使用される言語の識別子であるDISPID_AMBIENT_LOCALEIDを取得します。

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>パラメーター

*Lcid*<br/>
プロパティDISPID_AMBIENT_LOCALEID。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

コントロールは、この識別子を使用して、ユーザー インターフェイスを異なる言語に適応させることができます。

## <a name="ccomcontrolbasegetambientmessagereflect"></a><a name="getambientmessagereflect"></a>を返します。

DISPID_AMBIENT_MESSAGEREFLECT、コンテナがイベントとしてウィンドウ メッセージを受信するかどうかを示すフラグ`WM_DRAWITEM`を取得します。

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>パラメーター

*メッセージを反映する*<br/>
プロパティはDISPID_AMBIENT_MESSAGEREFLECT。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientpalette"></a><a name="getambientpalette"></a>コントロールベース::ゲットアンビエントパレット

コンテナの HPALETTE にアクセスするために使用されるDISPID_AMBIENT_PALETTEを取得します。

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>パラメーター

*hパレット*<br/>
プロパティはDISPID_AMBIENT_PALETTE。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientproperty"></a><a name="getambientproperty"></a>プロパティを取得します。

で指定されたコンテナ プロパティ*を取得します*。

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
取得するコンテナー プロパティの識別子。

*var*<br/>
プロパティを受け取る変数。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

ATL は、特定のプロパティを取得するためのヘルパー関数のセットを提供[しています](#getambientbackcolor)。 適切な方法がない場合は、 を`GetAmbientProperty`使用します。

## <a name="ccomcontrolbasegetambientrighttoleft"></a><a name="getambientrighttoleft"></a>コムコントロールベース::ゲットアンビエントライトを左に

コンテナーによって表示されるコンテンツの方向であるDISPID_AMBIENT_RIGHTTOLEFTを取得します。

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>パラメーター

*左に右へ*<br/>
プロパティはDISPID_AMBIENT_RIGHTTOLEFT。 コンテンツが右から左に表示される場合は TRUE に設定し、左から右に表示される場合は FALSE に設定します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="ccomcontrolbasegetambientscaleunits"></a><a name="getambientscaleunits"></a>クコムコントロールベース::アンビエントスケールユニット

DISPID_AMBIENT_SCALEUNITS、ラベル表示用のコンテナーのアンビエント単位 (インチやセンチメートルなど) を取得します。

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>パラメーター

*スケール単位*<br/>
プロパティはDISPID_AMBIENT_SCALEUNITS。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientshowgrabhandles"></a><a name="getambientshowgrabhandles"></a>コムコントロールベース::アンビエントショーグラブハンドル

DISPID_AMBIENT_SHOWGRABHANDLESを取得します。

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>パラメーター

*グラブハンドルを表示する*<br/>
プロパティはDISPID_AMBIENT_SHOWGRABHANDLES。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientshowhatching"></a><a name="getambientshowhatching"></a>コムコントロールベース::ゲットアンビエントショーハッチング

DISPID_AMBIENT_SHOWHATCHINGを取得します。コントロールのユーザー インターフェイスがアクティブなときに、コンテナーがハッチ パターンでコントロール自体を表示できるかどうかを示すフラグ。

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>パラメーター

*bショーハッチング*<br/>
プロパティはDISPID_AMBIENT_SHOWHATCHING。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambientsupportsmnemonics"></a><a name="getambientsupportsmnemonics"></a>コムコントロールベース::Getアンビエントサポートムネモニック

DISPID_AMBIENT_SUPPORTSMNEMONICSを取得します。

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>パラメーター

*bサポートムネモニック*<br/>
プロパティはDISPID_AMBIENT_SUPPORTSMNEMONICS。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambienttextalign"></a><a name="getambienttextalign"></a>コントロールベース::アンビエントテキスト整列

DISPID_AMBIENT_TEXTALIGN、コンテナが推奨するテキストの配置を取得します: 0 (右の数字、左のテキスト)、左揃えの場合は 1、中央揃えの場合は 2、右揃えの場合は 3。

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>パラメーター

*テキストの配置*<br/>
プロパティがDISPID_AMBIENT_TEXTALIGN。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetambienttoptobottom"></a><a name="getambienttoptobottom"></a>コムコントロールベース::ゲットアンビエントトップトボトム

DISPID_AMBIENT_TOPTOBOTTOM、コンテンツがコンテナーによって表示される方向を取得します。

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>パラメーター

*ボトムス*<br/>
プロパティDISPID_AMBIENT_TOPTOBOTTOM。 テキストが上から下に表示される場合は TRUE に設定し、下から上に表示されている場合は FALSE に設定します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="ccomcontrolbasegetambientuidead"></a><a name="getambientuidead"></a>コムコントロールベース::ゲットアンビエントUIデッド

DISPID_AMBIENT_UIDEADを取得します。

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>パラメーター

*bUIデッド*<br/>
プロパティはDISPID_AMBIENT_UIDEAD。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

TRUE の場合、コントロールは応答しません。 このフラグは、DISPID_AMBIENT_USERMODE フラグに関係なく適用されます。 を参照してください[。](#getambientusermode)

## <a name="ccomcontrolbasegetambientusermode"></a><a name="getambientusermode"></a>を使用します。

DISPID_AMBIENT_USERMODE、コンテナーが実行モード (TRUE) またはデザイン モード (FALSE) かどうかを示すフラグを取得します。

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>パラメーター

*モード*<br/>
プロパティDISPID_AMBIENT_USERMODE。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

## <a name="ccomcontrolbasegetdirty"></a><a name="getdirty"></a>ココムコントロールベース::ゲットダーティ

データ メンバ`m_bRequiresSave`の値を返します。

```
BOOL GetDirty();
```

### <a name="return-value"></a>戻り値

データ メンバ[の値を返m_bRequiresSave。](#m_brequiressave)

### <a name="remarks"></a>解説

この値は[、CCom コントロールベース::セットダーティ](#setdirty)を使用して設定されます。

## <a name="ccomcontrolbasegetzoominfo"></a><a name="getzoominfo"></a>コントロールベース::ゲットズームインフォ

インプレイス編集用にアクティブ化されたコントロールのズーム係数の分子と分母の x および y 値を取得します。

```cpp
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>パラメーター

*ディ*<br/>
ズーム係数の分子と分母を保持する構造。 詳細については[、「ATL_DRAWINFO」](../../atl/reference/atl-drawinfo-structure.md)を参照してください。

### <a name="remarks"></a>解説

ズーム係数は、コントロールの現在の範囲に対する自然なサイズの比率です。

## <a name="ccomcontrolbaseinplaceactivate"></a><a name="inplaceactivate"></a>ココムコントロールベース::インプレースアクティベート

コントロールが非アクティブ状態から*iVerb*の動詞が示す状態に遷移します。

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>パラメーター

*i動詞*<br/>
によって実行されるアクションを示す値[: :DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb).

*プルポスレック*<br/>
埋め込みコントロールの位置へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

アクティブ化の前に、このメソッドは、コントロールにクライアント サイトが含まれているかどうかを確認し、コントロールの表示領域を確認して、親ウィンドウ内のコントロールの位置を取得します。 コントロールがアクティブ化されると、このメソッドはコントロールのユーザー インターフェイスをアクティブにし、コントロールを表示するようにコンテナーに通知します。

この`IOleInPlaceSite`メソッドは、コントロールの`IOleInPlaceSiteEx`、、`IOleInPlaceSiteWindowless`またはインターフェイス ポインターを取得し、コントロール クラスのデータ メンバー [CComControlBase::m_spInPlaceSite](#m_spinplacesite)に格納します。 コントロール クラス データ メンバー [CComControlBase::m_bInPlaceSiteEx、CCom](#m_binplacesiteex)[コントロールベース::m_bWndLess、CCom](#m_bwndless)[コントロールベース::m_bWasOnceWindowless](#m_bwasoncewindowless)、および[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)は、必要に応じて true に設定されます。

## <a name="ccomcontrolbaseinternalgetsite"></a><a name="internalgetsite"></a>コントロールベース::内部ゲットサイト

指定したインターフェイスへのポインターをコントロール サイトに照会します。

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
*ppUnkSite*で返されるインターフェイス ポインタの IID。

*ppUnkSite*<br/>
*riid*で要求されたインターフェイス ポインターを受け取るポインター変数のアドレス。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

サイトが*riid*で要求されたインターフェイスをサポートしている場合、ポインターは*ppUnkSite*を使用して返されます。 それ以外の場合 *、ppUnkSite*は NULL に設定されます。

## <a name="ccomcontrolbasem_bautosize"></a><a name="m_bautosize"></a>コムコントロールベース::m_bAutoSize

コントロールを他のサイズにできないことを示すフラグ。

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>解説

このフラグは、チェック`IOleObjectImpl::SetExtent`され、TRUE の場合は、関数がE_FAIL返します。

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

ATL コントロール ウィザードの[[ストック プロパティ]](../../atl/reference/stock-properties-atl-control-wizard.md)タブで **[自動サイズ]** オプションを追加すると、ウィザードはコントロール クラスにこのデータ メンバを自動的に作成し[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)、プロパティの put メソッドと get メソッドを作成します。

## <a name="ccomcontrolbasem_bdrawfromnatural"></a><a name="m_bdrawfromnatural"></a>コムコントロールベース::m_bDrawFromNatural

を`IDataObjectImpl::GetData`示すフラグ`CComControlBase::GetZoomInfo`を指定し、コントロール`m_sizeNatural`のサイズを`m_sizeExtent`からではなくから設定する必要があります。

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_bdrawgetdatainhimetric"></a><a name="m_bdrawgetdatainhimetric"></a>コムコントロールベース::m_bDrawGetDataInHimetric

描画時に`IDataObjectImpl::GetData`、ピクセルではなく HIMETRIC 単位を使用することを示すフラグです。

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>解説

各論理 HIMETRIC 単位は 0.01 ミリメートルです。

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_binplaceactive"></a><a name="m_binplaceactive"></a>コムコントロールベース::m_bInPlaceActive

コントロールがインプレース アクティブであることを示すフラグ。

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>解説

つまり、コントロールが表示され、ウィンドウがある場合は、そのウィンドウが表示されますが、そのメニューとツールバーはアクティブでない可能性があります。 この`m_bUIActive`フラグは、メニューなどのコントロールのユーザー インターフェイスもアクティブであることを示します。

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_binplacesiteex"></a><a name="m_binplacesiteex"></a>コムコントロールベース::m_bInPlaceSiteEx

コンテナーがインターフェイスと OCX96 コントロール機能 (`IOleInPlaceSiteEx`ウィンドウなしコントロールやちらつきのないコントロールなど) をサポートするフラグ。

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

データ メンバー`m_spInPlaceSite`は、フラグの`m_bWndLess``m_bInPlaceSiteEx`値に応じて[、IOleInPlaceSite、](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)または[IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)、または[IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)インターフェイスを指します。 ポインタが有効な`m_bNegotiatedWnd`場合は、データ`m_spInPlaceSite`メンバが TRUE である必要があります。

FALSE`m_bWndLess`の場合`m_bInPlaceSiteEx`、TRUE`m_spInPlaceSite`はインターフェイス`IOleInPlaceSiteEx`ポインターです。 これらの3つのデータメンバー間の関係を示す表については[、m_spInPlaceSite](#m_spinplacesite)を参照してください。

## <a name="ccomcontrolbasem_bnegotiatedwnd"></a><a name="m_bnegotiatedwnd"></a>コムコントロールベース::m_bNegotiatedWnd

コントロールが OCX96 コントロール機能 (ちらつきのないコントロールやウィンドウなしのコントロールなど) のサポートについてコンテナーとネゴシエートしたかどうか、およびコントロールがウィンドウ表示またはウィンドウなしかどうかを示すフラグです。

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

ポインター`m_bNegotiatedWnd`を有効にするには、フラグを`m_spInPlaceSite`TRUE にする必要があります。

## <a name="ccomcontrolbasem_brecomposeonresize"></a><a name="m_brecomposeonresize"></a>コムコントロールベース::m_bRecomposeOnResize

コンテナーがコントロールの表示サイズを変更したときに、コントロールがプレゼンテーションを再構成することを示すフラグ。

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

このフラグは[、IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent)によってチェックされ、TRUE`SetExtent`の場合は、ビューの変更をコンテナーに通知します。 このフラグを設定する場合は[、OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc)列挙体のOLEMISC_RECOMPOSEONRESIZEビットも設定する必要があります。

## <a name="ccomcontrolbasem_brequiressave"></a><a name="m_brequiressave"></a>コムコントロールベース::m_bRequiresSave

コントロールが最後に保存されてから変更されたことを示すフラグ。

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>解説

の`m_bRequiresSave`値は[、CComコントロールベースで設定することができます::セットダーティと](#setdirty)[取得CComコントロールベース::GetDirty](#getdirty).

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_bresizenatural"></a><a name="m_bresizenatural"></a>コムコントロールベース::m_bResizeNatural

コンテナーがコントロールの表示サイズを変更したときに、コントロールの自然な範囲 (スケーリングされていない物理サイズ) のサイズを変更することを示すフラグ。

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>解説

このフラグはによって`IOleObjectImpl::SetExtent`チェックされ、TRUE の場合、渡される`SetExtent`サイズは`m_sizeNatural`に割り当てられます。

渡されるサイズ`SetExtent`は、 の値`m_sizeExtent`に関係なく常に`m_bResizeNatural`に に割り当てられます。

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_buiactive"></a><a name="m_buiactive"></a>コムコントロールベース::m_bUIActive

メニューやツールバーなどのコントロールのユーザー インターフェイスがアクティブであることを示すフラグ。

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>解説

この`m_bInPlaceActive`フラグは、コントロールがアクティブであり、ユーザー インターフェイスがアクティブであることを示しません。

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_busingwindowrgn"></a><a name="m_busingwindowrgn"></a>コムコントロールベース::m_bUsingWindowRgn

コントロールがコンテナー指定のウィンドウ領域を使用しているフラグ。

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_bwasoncewindowless"></a><a name="m_bwasoncewindowless"></a>コムコントロールベース::m_bWasOnceWindowless

コントロールがウィンドウなしであることを示すフラグが、現在ウィンドウなしである場合とない場合があります。

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_bwindowonly"></a><a name="m_bwindowonly"></a>コムコントロールベース::m_bWindowOnly

コンテナーがウィンドウなしのコントロールをサポートしている場合でも、コントロールをウィンドウ化する必要があることを示すフラグ。

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_bwndless"></a><a name="m_bwndless"></a>コムコントロールベース::m_bWndLess

コントロールがウィンドウなしであることを示すフラグ。

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

データ メンバー`m_spInPlaceSite`は、および[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)フラグ`m_bWndLess`の値に応じて[、IOleInPlaceSite、](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)または[IOleInPlaceSiteEx 、または IOleInPlaceSiteEx 、または IOleInPlaceSite](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)を指します。 [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex) (データ メンバー [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)は[、m_spInPlaceSite 有効](#m_spinplacesite)なポインターを有効にする必要があります。

TRUE`m_bWndLess`の場合`m_spInPlaceSite`は、`IOleInPlaceSiteWindowless`インターフェイス ポインターです。 これらのデータ メンバー間の完全なリレーションシップを示す表については[、CComControlBase::m_spInPlaceSite](#m_spinplacesite)を参照してください。

## <a name="ccomcontrolbasem_hwndcd"></a><a name="m_hwndcd"></a>コムコントロールベース::m_hWndCD

コントロールに関連付けられているウィンドウ ハンドルへの参照を格納します。

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_nfreezeevents"></a><a name="m_nfreezeevents"></a>コムコントロールベース::m_nFreezeEvents

イベントの間に発生する雪解け (イベントの受け入れ) せずに、コンテナーがイベントを凍結した回数のカウントです (イベントの受け入れ)。

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_rcpos"></a><a name="m_rcpos"></a>コムコントロールベース::m_rcPos

コントロールの位置をピクセル単位で、コンテナーの座標で表します。

```
RECT m_rcPos;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_sizeextent"></a><a name="m_sizeextent"></a>コムコントロールベース::m_sizeExtent

特定のディスプレイの HIMETRIC 単位 (各単位は 0.01 ミリメートル) 単位のコントロールの範囲。

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

このサイズは、ディスプレイによって拡大縮小されます。 コントロールの物理サイズは、データ メンバーで`m_sizeNatural`指定され、固定されます。

グローバル関数[AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)を使用してサイズをピクセルに変換できます。

## <a name="ccomcontrolbasem_sizenatural"></a><a name="m_sizenatural"></a>コムコントロールベース::m_sizeNatural

HIMETRIC 単位でのコントロールの物理サイズ (各単位は 0.01 ミリメートル)。

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

このサイズは固定で、サイズ`m_sizeExtent`はディスプレイによって拡大縮小されます。

グローバル関数[AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)を使用してサイズをピクセルに変換できます。

## <a name="ccomcontrolbasem_spadvisesink"></a><a name="m_spadvisesink"></a>コムコントロールベース::m_spAdviseSink

コンテナー (コンテナーの[IAdviseSink)](/windows/win32/api/objidl/nn-objidl-iadvisesink)に対するアドバイザリ接続への直接ポインター。

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_spambientdispatch"></a><a name="m_spambientdispatch"></a>コムコントロールベース::m_spAmbientDispatch

`IDispatch`ポインターを介して`CComDispatchDriver`オブジェクトのプロパティを取得および設定できるオブジェクト。

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_spclientsite"></a><a name="m_spclientsite"></a>コムコントロールベース::m_spClientSite

コンテナー内のコントロールのクライアント サイトへのポインター。

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

## <a name="ccomcontrolbasem_spdataadviseholder"></a><a name="m_spdataadviseholder"></a>コムコントロールベース::m_spDataAdviseHolder

データ オブジェクトとアドバイズ シンク間のアドバイザリ接続を保持するための標準的な手段を提供します。

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

データ オブジェクトは、データを転送できるコントロールで、 [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)を実装します。

このインターフェイス`m_spDataAdviseHolder`は、コンテナーへのアドバイザリ接続を確立および削除するための[IDataObject::DAdvise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise)メソッドと[IDataObject::DUnadvise](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise)メソッドを実装します。 コントロールのコンテナーは[、IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink)インターフェイスをサポートして、アドバイス シンクを実装する必要があります。

## <a name="ccomcontrolbasem_spinplacesite"></a><a name="m_spinplacesite"></a>コムコントロールベース::m_spInPlaceSite

コンテナーの[IOleInPlace サイト](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)、または[IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)へのポインター[ウィンドウレス](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)インターフェイス ポインター。

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

ポインター`m_spInPlaceSite`は[、m_bNegotiatedWnd](#m_bnegotiatedwnd)フラグが TRUE の場合にのみ有効です。

次の表は、ポインター`m_spInPlaceSite`型が[m_bWndLess](#m_bwndless)と[m_bInPlaceSiteEx](#m_binplacesiteex)データ メンバー フラグに依存する方法を示しています。

|m_spInPlaceSiteタイプ|m_bWndLess値|m_bInPlaceSiteEx値|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|TRUE|TRUE または FALSE|
|`IOleInPlaceSiteEx`|FALSE|TRUE|
|`IOleInPlaceSite`|FALSE|FALSE|

## <a name="ccomcontrolbasem_spoleadviseholder"></a><a name="m_spoleadviseholder"></a>コムコントロールベース::m_spOleAdviseHolder

アドバイザリコネクションを保持する方法の標準的な実装を提供します。

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>解説

> [!NOTE]
> コントロール クラス内でこのデータ メンバーを使用するには、コントロール クラスでデータ メンバーとして宣言する必要があります。 コントロール クラスは、基本クラスの共用体内で宣言されているため、このデータ メンバーを基本クラスから継承しません。

インターフェイス`m_spOleAdviseHolder`は、コンテナーへのアドバイザリ[接続を](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise)確立[および削除](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise)するためのメソッドを実装します。 コントロールのコンテナーは[、IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink)インターフェイスをサポートして、アドバイス シンクを実装する必要があります。

## <a name="ccomcontrolbaseondraw"></a><a name="ondraw"></a>ココムコントロールベース::オンドロー

コントロールを描画するには、このメソッドをオーバーライドします。

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>パラメーター

*ディ*<br/>
描画の側面、コントロールの境界、図面が最適化されているかどうかなどの図面情報を含む[ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)構造への参照。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

既定`OnDraw`では[、CComControlBase::OnDrawAdvanced](#ondrawadvanced)で設定されたフラグに応じて、デバイス コンテキストを削除または復元するか、何もしません。

ATL コントロール ウィザードを使用してコントロールを作成すると、`OnDraw`メソッドがコントロール クラスに自動的に追加されます。 ウィザードの既定`OnDraw`では、ラベル "ATL 8.0" の四角形が描画されます。

### <a name="example"></a>例

[の例を](#getambientappearance)参照してください。

## <a name="ccomcontrolbaseondrawadvanced"></a><a name="ondrawadvanced"></a>ココムコントロールベース::オンドローアドバンスド

既定`OnDrawAdvanced`では、描画用に正規化されたデバイス コンテキストを準備し、コントロール クラスの`OnDraw`メソッドを呼び出します。

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>パラメーター

*ディ*<br/>
描画の側面、コントロールの境界、図面が最適化されているかどうかなどの図面情報を含む[ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)構造への参照。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

コンテナーによって渡されたデバイス コンテキストを正規化せずに受け入れる場合は、このメソッドをオーバーライドします。

詳細については[、CCom コントロールベース::OnDraw](#ondraw)を参照してください。

## <a name="ccomcontrolbaseonkillfocus"></a><a name="onkillfocus"></a>ココムコントロールベース::オンキルフォーカス

コントロールがインプレース アクティブで、有効なコントロール サイトを持っていることを確認し、コントロールがフォーカスを失ったことをコンテナーに通知します。

```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>パラメーター

*nMsg*<br/>
予約済み。

*wParam*<br/>
予約済み。

*lParam*<br/>
予約済み。

*処理済み*<br/>
ウィンドウ メッセージが正常に処理されたかどうかを示すフラグ。 デフォルトは FALSE です。

### <a name="return-value"></a>戻り値

常に 1 を返します。

## <a name="ccomcontrolbaseonmouseactivate"></a><a name="onmouseactivate"></a>ココムコントロールベース::マウス活性化

UI がユーザー モードであることを確認し、コントロールをアクティブにします。

```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>パラメーター

*nMsg*<br/>
予約済み。

*wParam*<br/>
予約済み。

*lParam*<br/>
予約済み。

*処理済み*<br/>
ウィンドウ メッセージが正常に処理されたかどうかを示すフラグ。 デフォルトは FALSE です。

### <a name="return-value"></a>戻り値

常に 1 を返します。

## <a name="ccomcontrolbaseonpaint"></a><a name="onpaint"></a>コムコントロールベース::オンペイント

描画用のコンテナーを準備し、コントロールのクライアント領域を取得してから、コントロール クラスの`OnDrawAdvanced`メソッドを呼び出します。

```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```

### <a name="parameters"></a>パラメーター

*nMsg*<br/>
予約済み。

*wParam*<br/>
既存の HDC。

*lParam*<br/>
予約済み。

*lResult*<br/>
予約済み。

### <a name="return-value"></a>戻り値

常にゼロが返されます。

### <a name="remarks"></a>解説

*wParam*が NULL`OnPaint`でない場合は、有効な HDC が含まれていると仮定し[、CComControlBase::m_hWndCD](#m_hwndcd)の代わりにそれを使用します。

## <a name="ccomcontrolbaseonsetfocus"></a><a name="onsetfocus"></a>コントロールベース::オンセットフォーカス

コントロールがインプレース アクティブで、有効なコントロール サイトを持っていることを確認し、コントロールがフォーカスを得たことをコンテナーに通知します。

```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>パラメーター

*nMsg*<br/>
予約済み。

*wParam*<br/>
予約済み。

*lParam*<br/>
予約済み。

*処理済み*<br/>
ウィンドウ メッセージが正常に処理されたかどうかを示すフラグ。 デフォルトは FALSE です。

### <a name="return-value"></a>戻り値

常に 1 を返します。

### <a name="remarks"></a>解説

コントロールがフォーカスを受け取った旨の通知をコンテナーに送信します。

## <a name="ccomcontrolbasepretranslateaccelerator"></a><a name="pretranslateaccelerator"></a>コントロールベース::P再翻訳アクセラレータ

独自のキーボード アクセラレータ ハンドラーを提供するには、このメソッドをオーバーライドします。

```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```

### <a name="parameters"></a>パラメーター

*Pmsg*<br/>
予約済み。

*hレット*<br/>
予約済み。

### <a name="return-value"></a>戻り値

デフォルトでは FALSE が返されます。

## <a name="ccomcontrolbasesendonclose"></a><a name="sendonclose"></a>コントロールベース::センドオンクローズ

コントロールが閉じられたことをアドバイス ホルダーに登録されているすべてのアドバイザリ シンクに通知します。

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

コントロールがアドバイザリ シンクを閉じたという通知を送信します。

## <a name="ccomcontrolbasesendondatachange"></a><a name="sendondatachange"></a>コントロールベース::センドオンデータチェンジ

コントロール データが変更されたことをアドバイスホルダーに登録されているすべてのアドバイザリ シンクに通知します。

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>パラメーター

*Advf*<br/>
[IAdviseSink::OnDataChange](/windows/win32/api/objidl/nf-objidl-iadvisesink-ondatachange)の呼び出しの方法を指定するフラグをアドバイスします。 値は[ADVF](/windows/win32/api/objidl/ne-objidl-advf)列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="ccomcontrolbasesendonrename"></a><a name="sendonrename"></a>コントロールベース::センドオンリネーム

コントロールに新しいモニカーがあることを通知ホルダーに登録されているすべてのアドバイザリ シンクに通知します。

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>パラメーター

*Pmk*<br/>
コントロールの新しいモニカーへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

コントロールのモニカーが変更されたことを示す通知を送信します。

## <a name="ccomcontrolbasesendonsave"></a><a name="sendonsave"></a>コントロールベース::センドオンセーブ

コントロールが保存されたことを通知ホルダーに登録されているすべてのアドバイザリ シンクに通知します。

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

コントロールがデータを保存したことを通知します。

## <a name="ccomcontrolbasesendonviewchange"></a><a name="sendonviewchange"></a>コントロールベース::センドオンビューチェンジ

コントロールのビューが変更されたことを、登録されているすべてのアドバイザリ シンクに通知します。

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>パラメーター

*dwアスペクト*<br/>
コントロールのアスペクトまたはビュー。

*Lindex*<br/>
ビューの変更部分。 1 だけが有効です。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

`SendOnViewChange`を呼び出します[。](/windows/win32/api/objidl/nf-objidl-iadvisesink-onviewchange) 現在サポートされている*lindex*の値は -1 のみで、ビュー全体が対象であることを示します。

## <a name="ccomcontrolbasesetcontrolfocus"></a><a name="setcontrolfocus"></a>コントロールベース::セットコントロールフォーカス

コントロールに対するキーボード フォーカスの設定または削除を行います。

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>パラメーター

*bグラブ*<br/>
TRUE の場合、キーボード フォーカスを呼び出し元コントロールに設定します。 FALSE の場合、フォーカスがある場合は、呼び出し元のコントロールからキーボード フォーカスを削除します。

### <a name="return-value"></a>戻り値

コントロールがフォーカスを受け取った場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ウィンドウコントロールの場合は、Windows API 関数[SetFocus](/windows/win32/api/winuser/nf-winuser-setfocus)が呼び出されます。 ウィンドウなしのコントロールの場合は、[ウィンドウレス::セットフォーカス](/windows/win32/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus)が呼び出されます。 この呼び出しを通じて、ウィンドウなしのコントロールはキーボード フォーカスを取得し、ウィンドウ メッセージに応答できます。

## <a name="ccomcontrolbasesetdirty"></a><a name="setdirty"></a>ココムコントロールベース::セットダーティ

データ メンバ`m_bRequiresSave`を*bDirty*の値に設定します。

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>パラメーター

*bダーティ*<br/>
データ メンバーの値[CComControlBase::m_bRequiresSave](#m_brequiressave)。

### <a name="remarks"></a>解説

`SetDirty(TRUE)`最後に保存されてからコントロールが変更されたことを示すフラグを付けるために呼び出す必要があります。 の`m_bRequiresSave`値は[、CCom コントロールベース::GetDirty](#getdirty)で取得されます。

## <a name="see-also"></a>関連項目

[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
