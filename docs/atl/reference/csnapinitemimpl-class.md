---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::AddMenuItems
- ATLSNAP/ATL::CSnapInItemImpl::Command
- ATLSNAP/ATL::CSnapInItemImpl::CreatePropertyPages
- ATLSNAP/ATL::CSnapInItemImpl::FillData
- ATLSNAP/ATL::CSnapInItemImpl::GetResultPaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::GetResultViewType
- ATLSNAP/ATL::CSnapInItemImpl::GetScopePaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::Notify
- ATLSNAP/ATL::CSnapInItemImpl::QueryPagesFor
- ATLSNAP/ATL::CSnapInItemImpl::SetMenuInsertionFlags
- ATLSNAP/ATL::CSnapInItemImpl::SetToolbarButtonInfo
- ATLSNAP/ATL::CSnapInItemImpl::UpdateMenuState
- ATLSNAP/ATL::CSnapInItemImpl::UpdateToolbarButton
- ATLSNAP/ATL::CSnapInItemImpl::m_bstrDisplayName
- ATLSNAP/ATL::CSnapInItemImpl::m_resultDataItem
- ATLSNAP/ATL::CSnapInItemImpl::m_scopeDataItem
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
ms.openlocfilehash: 04eeba0239789b9f3220b7bfece3eb41dc7f2826
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746417"
---
# <a name="csnapinitemimpl-class"></a>クラス

このクラスには、スナップイン ノード オブジェクトを実装するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`CSnapInItemImpl`。

*bIsExtension*<br/>
オブジェクトがスナップイン拡張の場合は TRUE。それ以外の場合は FALSE。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cスナップインアイテムインプル::Cスナップインアイテムインプル](#csnapinitemimpl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[メニュー項目の追加](#addmenuitems)|コンテキスト メニューにメニュー項目を追加します。|
|[Cスナップインアイテムインプル::コマンド](#command)|カスタム メニュー項目が選択されたときにコンソールによって呼び出されます。|
|[プロパティ ページを作成します。](#createpropertypages)|スナップインのプロパティ シートにページを追加します。|
|[クスナップインアイテムインプル::フィルデータ](#filldata)|スナップイン オブジェクトの情報を指定したストリームにコピーします。|
|[をクリックします。](#getresultpaneinfo)|スナップインの`RESULTDATAITEM`構造を取得します。|
|[を返します。](#getresultviewtype)|結果ペインで使用されるビューの種類を決定します。|
|[をクリックします。](#getscopepaneinfo)|スナップインの`SCOPEDATAITEM`構造を取得します。|
|[CSnapInItemImpl::通知](#notify)|ユーザーが実行した操作のスナップインに通知するために、コンソールによって呼び出されます。|
|[次のページを表示します。](#querypagesfor)|スナップイン ノードがプロパティ ページをサポートしているかどうかを確認するために呼び出されます。|
|[をクリックします。](#setmenuinsertionflags)|スナップイン オブジェクトのメニュー挿入フラグを変更します。|
|[をクリックします。](#settoolbarbuttoninfo)|指定したツール バー ボタンの情報を設定します。|
|[をクリックします。](#updatemenustate)|コンテキスト メニュー項目の状態を更新します。|
|[をクリックします。](#updatetoolbarbutton)|指定したツール バー ボタンの状態を更新します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[Cスナップインアイテムインプル::m_bstrDisplayName](#m_bstrdisplayname)|スナップイン オブジェクトの名前。|
|[Cスナップインアイテムインプル::m_resultDataItem](#m_resultdataitem)|オブジェクトによって`RESULTDATAITEM`使用される Windows`CSnapInItemImpl`構造体。|
|[Cスナップインアイテムインプル::m_scopeDataItem](#m_scopedataitem)|オブジェクトによって`SCOPEDATAITEM`使用される Windows`CSnapInItemImpl`構造体。|

## <a name="remarks"></a>解説

`CSnapInItemImpl`は、メニュー項目やツール バーの追加、スナップイン ノードのコマンドを適切なハンドラー関数に転送するなど、スナップイン ノード オブジェクトの基本的な実装を提供します。 これらの機能は、いくつかの異なるインターフェイスとマップの種類を使用して実装されます。 既定の実装では、派生クラスの正しいインスタンスを決定し、メッセージを正しいインスタンスに転送することによって、ノード オブジェクトに送信された通知を処理します。

## <a name="inheritance-hierarchy"></a>継承階層

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsnap.h

## <a name="csnapinitemimpladdmenuitems"></a><a name="addmenuitems"></a>メニュー項目の追加

このメソッドは、関数[IExtendContextMenu::AddMenuItems](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems)を実装します。

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>パラメーター

*パイコールバック*<br/>
[in]コンテキスト メニュー`IContextMenuCallback`に項目を追加できる を指すポインター。

*挿入可能*<br/>
[イン、アウト]使用できる Microsoft 管理コンソール (MMC) 定義されたメニュー項目挿入ポイントを識別します。 これは、次のフラグの組み合わせです。

- CCM_INSERTIONALLOWED_TOP項目は、コンテキストメニューの上部に挿入できます。

- CCM_INSERTIONALLOWED_NEW アイテムは、[新規作成] サブメニューに挿入できます。

- CCM_INSERTIONALLOWED_TASK項目は、[タスク] サブメニューに挿入できます。

- CCM_INSERTIONALLOWED_VIEW項目は、ツールバーの表示メニューまたは結果ペインのコンテキストメニューの表示サブメニューに挿入できます。

*type*<br/>
[in]オブジェクトの種類を指定します。 次のいずれかの値になります。

- CCT_SCOPE スコープ ペイン コンテキストのデータ オブジェクト。

- CCT_RESULT結果ペインコンテキストのデータオブジェクト。

- CCT_SNAPIN_MANAGER スナップイン マネージャー コンテキストのデータ オブジェクトです。

- CCT_UNINITIALIZED Data オブジェクトの型が無効です。

## <a name="csnapinitemimplcommand"></a><a name="command"></a>Cスナップインアイテムインプル::コマンド

このメソッドは、Win32 関数[を実装します](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-command)。

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]メニュー項目のコマンド ID を指定します。

*type*<br/>
[in]オブジェクトの種類を指定します。 次のいずれかの値になります。

- CCT_SCOPE スコープ ペイン コンテキストのデータ オブジェクト。

- CCT_RESULT結果ペインコンテキストのデータオブジェクト。

- CCT_SNAPIN_MANAGER スナップイン マネージャー コンテキストのデータ オブジェクトです。

- CCT_UNINITIALIZED Data オブジェクトの型が無効です。

## <a name="csnapinitemimplcreatepropertypages"></a><a name="createpropertypages"></a>プロパティ ページを作成します。

このメソッドは、Win32 関数[を実装します](/windows/win32/api/mmc/nn-mmc-iextendpropertysheet2)。

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>パラメーター

*プロバイダ*<br/>
[in]`IPropertySheetCallback`インターフェイスへのポインター。

*処理*<br/>
[in]MMCN_PROPERTY_CHANGE通知メッセージを適切なデータ クラスにルーティングするために使用するハンドルを指定します。

*パンク*<br/>
[in]ノードに`IExtendPropertySheet`関するコンテキスト情報を含むオブジェクトのインターフェイスへのポインター。

*type*<br/>
[in]オブジェクトの種類を指定します。 次のいずれかの値になります。

- CCT_SCOPE スコープ ペイン コンテキストのデータ オブジェクト。

- CCT_RESULT結果ペインコンテキストのデータオブジェクト。

- CCT_SNAPIN_MANAGER スナップイン マネージャー コンテキストのデータ オブジェクトです。

- CCT_UNINITIALIZED Data オブジェクトの型が無効です。

## <a name="csnapinitemimplcsnapinitemimpl"></a><a name="csnapinitemimpl"></a>Cスナップインアイテムインプル::Cスナップインアイテムインプル

`CSnapInItemImpl` オブジェクトを構築します。

```
CSnapInItemImpl();
```

## <a name="csnapinitemimplfilldata"></a><a name="filldata"></a>クスナップインアイテムインプル::フィルデータ

この関数は、項目に関する情報を取得するために呼び出されます。

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>パラメーター

*Cf*<br/>
[in]クリップボードの形式 (テキスト、リッチ テキスト、OLE アイテムを含むリッチ テキスト) を指定します。

*pストリーム*<br/>
[in]オブジェクト データを含むストリームへのポインター。

### <a name="remarks"></a>解説

この関数を正しく実装するには、 *cf*で示されたクリップボード形式に応じて、正しい情報をストリーム (*pStream*) にコピーします。

## <a name="csnapinitemimplgetresultviewtype"></a><a name="getresultviewtype"></a>を返します。

スナップイン オブジェクトの結果ペインのビューの種類を取得します。

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>パラメーター

*ビュータイプ*<br/>
[アウト]返されたビューの種類のアドレスへのポインター。

*オプション*<br/>
[アウト]MMC_VIEW_OPTIONS列挙体へのポインター。 この値は、次のいずれかです。

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0x0000001 [**表示**] メニューに標準のリスト ビューの選択肢を表示しないようにコンソールに指示します。 スナップインで、結果ビュー ペインに独自のカスタム ビューのみを表示できます。 これは、この時点で定義されている唯一のオプション・フラグです。

- MMC_VIEW_OPTIONS_NONE = 0 既定の表示オプションを使用できます。

## <a name="csnapinitemimplgetscopepaneinfo"></a><a name="getscopepaneinfo"></a>をクリックします。

スナップインの構造を`SCOPEDATAITEM`取得します。

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[アウト]`CSnapInItemImpl`オブジェクトの`SCOPEDATAITEM`構造体へのポインター。

## <a name="csnapinitemimplgetresultpaneinfo"></a><a name="getresultpaneinfo"></a>をクリックします。

スナップインの構造を`RESULTDATAITEM`取得します。

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>パラメーター

*を返します。*<br/>
[アウト]`CSnapInItemImpl`オブジェクトの`RESULTDATAITEM`構造体へのポインター。

## <a name="csnapinitemimplm_bstrdisplayname"></a><a name="m_bstrdisplayname"></a>Cスナップインアイテムインプル::m_bstrDisplayName

ノード項目に表示される文字列を格納します。

```
CComBSTR m_bstrDisplayName;
```

## <a name="csnapinitemimplm_scopedataitem"></a><a name="m_scopedataitem"></a>Cスナップインアイテムインプル::m_scopeDataItem

スナップイン`SCOPEDATAITEM`データ オブジェクトの構造。

```
SCOPEDATAITEM m_scopeDataItem;
```

## <a name="csnapinitemimplm_resultdataitem"></a><a name="m_resultdataitem"></a>Cスナップインアイテムインプル::m_resultDataItem

スナップイン データ オブジェクトの[RESULTDATAITEM](/windows/win32/api/mmc/ns-mmc-resultdataitem)構造体。

```
RESULTDATAITEM m_resultDataItem;
```

## <a name="csnapinitemimplnotify"></a><a name="notify"></a>CSnapInItemImpl::通知

スナップイン オブジェクトがユーザーによって処理されたときに呼び出されます。

```
STDMETHOD(Notify)(
    MMC_NOTIFY_TYPE event,
    long arg,
    long param,
    IComponentData* pComponentData,
    IComponent* pComponent,
    DATA_OBJECT_TYPES type) = 0;
```

### <a name="parameters"></a>パラメーター

*event*<br/>
[in]ユーザーが実行するアクションを識別します。 次の通知が可能です。

- MMCN_ACTIVATE ウィンドウがアクティブ化および非アクティブ化されているときに送信されます。

- MMCN_ADD_IMAGES 結果ウィンドウにイメージを追加するために送信されます。

- MMCN_BTN_CLICK ユーザーがツール バー ボタンのいずれかをクリックしたときに送信されます。

- MMCN_CLICK ユーザーがリスト ビュー アイテムのマウス ボタンをクリックしたときに送信されます。

- MMCN_DBLCLICK ユーザーがリスト ビュー アイテムのマウス ボタンをダブルクリックしたときに送信されます。

- MMCN_DELETE オブジェクトを削除する必要があることをスナップインに通知するために送信されます。

- MMCN_EXPAND フォルダを拡張または縮小する必要がある場合に送信されます。

- MMCN_MINIMIZED ウィンドウが最小化または最大化されているときに送信されます。

- MMCN_PROPERTY_CHANGE スナップイン オブジェクトのビューが変更されようとしていることを通知するために送信されます。

- MMCN_REMOVE_CHILDREN スナップインが指定されたノードの下に追加したサブツリー全体を削除する必要があるときに送信されます。

- MMCN_RENAME 名前の変更をクエリする最初の時間と、名前の変更を行う 2 回目の送信日時です。

- MMCN_SELECT スコープまたは結果ビュー ペイン内のアイテムが選択されたときに送信されます。

- MMCN_SHOW スコープアイテムが最初に選択または選択解除されたときに送信されます。

- MMCN_VIEW_CHANGE 変更が発生したときにスナップインがすべてのビューを更新できる場合に送信されます。

*Arg*<br/>
[in]通知の種類によって異なります。

*Param*<br/>
[in]通知の種類によって異なります。

*を使用します。*<br/>
[アウト]を実装`IComponentData`するオブジェクトへのポインター。 から`IComponentData::Notify`通知が転送されない場合、このパラメータは NULL です。

*コンポーネント*<br/>
[アウト]を実装するオブジェクトへのポインター `IComponent`。 から`IComponent::Notify`通知が転送されない場合、このパラメータは NULL です。

*type*<br/>
[in]オブジェクトの種類を指定します。 次のいずれかの値になります。

- CCT_SCOPE スコープ ペイン コンテキストのデータ オブジェクト。

- CCT_RESULT結果ペインコンテキストのデータオブジェクト。

- CCT_SNAPIN_MANAGER スナップイン マネージャー コンテキストのデータ オブジェクトです。

- CCT_UNINITIALIZED Data オブジェクトの型が無効です。

## <a name="csnapinitemimplquerypagesfor"></a><a name="querypagesfor"></a>次のページを表示します。

スナップイン ノードがプロパティ ページをサポートしているかどうかを確認するために呼び出されます。

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

## <a name="csnapinitemimplsetmenuinsertionflags"></a><a name="setmenuinsertionflags"></a>をクリックします。

スナップイン オブジェクトのメニュー挿入フラグを p*挿入許可*で指定した値を変更します。

```cpp
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>パラメーター

*前に挿入*<br/>
[in]項目がコンテキスト メニューに追加される前に関数を呼び出す必要がある場合は 0 以外の値を返します。それ以外の場合は 0。

*挿入可能*<br/>
[イン、アウト]使用できる Microsoft 管理コンソール (MMC) 定義されたメニュー項目挿入ポイントを識別します。 これは、次のフラグの組み合わせです。

- CCM_INSERTIONALLOWED_TOP項目は、コンテキストメニューの上部に挿入できます。

- CCM_INSERTIONALLOWED_NEW アイテムは、[新規作成] サブメニューに挿入できます。

- CCM_INSERTIONALLOWED_TASK項目は、[タスク] サブメニューに挿入できます。

- CCM_INSERTIONALLOWED_VIEW項目は、ツールバーの表示メニューまたは結果ペインのコンテキストメニューの表示サブメニューに挿入できます。

### <a name="remarks"></a>解説

プライマリ スナップインを開発している場合は、サードパーティの拡張機能が追加できるメニュー項目の種類を制限する方法として、挿入フラグをリセットできます。 たとえば、プライマリ スナップインでは、CCM_INSERTIONALLOWED_NEW フラグをクリアして、拡張機能が独自の [新規作成] メニュー項目を追加できないようにすることができます。

最初にクリアされた p*挿入許可*のビットを設定しないでください。 今後のバージョンの MMC では、現在定義されていないビットが使用される可能性があるため、現在定義されていないビットは変更しないでください。

## <a name="csnapinitemimplsettoolbarbuttoninfo"></a><a name="settoolbarbuttoninfo"></a>をクリックします。

この関数は、ツール バーを作成する前に、スナップイン オブジェクトのツール バー ボタン スタイルを変更します。

```cpp
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]設定するツール バー ボタンの ID。

*fsステート*<br/>
[in]ボタンの状態フラグ。 次の 1 つ以上の値を指定できます。

- TBSTATE_CHECKED ボタンはTBSTYLE_CHECKEDスタイルを持ち、押されています。

- TBSTATE_ENABLED ボタンはユーザー入力を受け入れます。 この状態ではないボタンは、ユーザー入力を受け付け、灰色表示になります。

- TBSTATE_HIDDEN ボタンは表示されず、ユーザー入力を受け取ることができません。

- TBSTATE_INDETERMINATE ボタンがグレー表示されます。

- TBSTATE_PRESSED ボタンが押されています。

- TBSTATE_WRAP ボタンの後に改行が表示されます。 ボタンにはTBSTATE_ENABLEDも必要です。

*fsType*<br/>
[in]ボタンの状態フラグ。 次の 1 つ以上の値を指定できます。

- TBSTYLE_BUTTON 標準のプッシュ ボタンを作成します。

- TBSTYLE_CHECK ユーザーがクリックするたびに押された状態と押されていない状態を切り替えるボタンを作成します。 ボタンが押された状態のとき、背景色が異なります。

- TBSTYLE_CHECKGROUP グループ内の別のボタンが押されるまで押されたままのチェック ボタンを作成します。

- TBSTYLE_GROUP グループ内の別のボタンが押されるまで押されたままのボタンを作成します。

- TBSTYLE_SEP ボタン グループ間に小さな間隔を設け、区切り記号を作成します。 このスタイルのボタンは、ユーザー入力を受け取りません。

## <a name="csnapinitemimplupdatemenustate"></a><a name="updatemenustate"></a>をクリックします。

スナップイン オブジェクトのコンテキスト メニューに挿入される前に、メニュー項目を変更します。

```cpp
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>パラメーター

*id*<br/>
[in]設定するメニュー項目の ID。

*pBuf*<br/>
[in]更新するメニュー項目の文字列へのポインター。

*フラグ*<br/>
[in]新しい状態フラグを指定します。 これは、次のフラグの組み合わせです。

- MF_POPUP コンテキスト メニュー内のサブメニューであることを指定します。 メニュー項目、挿入ポイント、および追加のサブメニューを、`lCommandID``IInsertionPointID`としてこのサブメニューに追加できます。

- MF_BITMAPおよびMF_OWNERDRAW これらのフラグは許可されず、戻り値が E_INVALIDARG になります。

- MF_SEPARATOR 水平分割線を描画します。 設定`IContextMenuProvider`されたメニュー項目のみを追加MF_SEPARATOR。

- MF_CHECKED メニュー項目の横にチェック マークを付けます。

- MF_DISABLED メニュー項目を無効にして選択できないようにしますが、フラグは淡色表示されません。

- MF_ENABLED メニュー項目を選択できるように有効にし、灰色の状態から復元します。

- MF_GRAYED メニュー項目を無効にし、選択できないように淡色表示します。

- MF_MENUBARBREAK メニュー バーのMF_MENUBREAK フラグと同じ機能を持ちます。 ドロップダウン メニュー、サブメニュー、またはショートカット メニューの場合、新しい列は、元の列と縦線で区切られます。

- MF_MENUBREAK 列を区切らずに、新しい行 (メニュー バーの場合) または新しい列 (ドロップダウン メニュー、サブメニュー、ショートカット メニューの場合) に項目を配置します。

- MF_UNCHECKED 項目の横にチェック マークを付けないことを示します (既定値)。

次のフラググループは、一緒に使用することはできません。

- MF_DISABLED、MF_ENABLED、MF_GRAYED。

- MF_MENUBARBREAKとMF_MENUBREAK。

- MF_CHECKEDとMF_UNCHECKED。

## <a name="csnapinitemimplupdatetoolbarbutton"></a><a name="updatetoolbarbutton"></a>をクリックします。

スナップイン オブジェクトのツール バー ボタンを、表示する前に変更します。

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>パラメーター

*id*<br/>
更新するツール バー ボタンのボタン ID を指定します。

*fsステート*<br/>
ツール バー ボタンの状態を指定します。 この状態を設定する場合は、TRUE を返します。 これは、次のフラグの組み合わせです。

- 有効ボタンは、ユーザー入力を受け入れます。 この状態ではないボタンは、ユーザー入力を受け付け、灰色表示になります。

- チェックボタンはCHECKEDスタイルを持ち、押されています。

- HIDDEN ボタンは表示されず、ユーザー入力を受け取ることができません。

- [不確定] ボタンは灰色表示されます。

- ボタン押下 ボタンが押されています。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
