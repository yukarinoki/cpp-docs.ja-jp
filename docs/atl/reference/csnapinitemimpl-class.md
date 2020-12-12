---
description: 詳細については、CSnapInItemImpl クラスに関するページを参照してください。
title: CSnapInItemImpl クラス
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
ms.openlocfilehash: c1c63f5b60d57743087bffde214d9b8addef5b8b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140557"
---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl クラス

このクラスには、スナップインノードオブジェクトを実装するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `CSnapInItemImpl` 。

*bIsExtension*<br/>
オブジェクトがスナップイン拡張である場合は TRUE。それ以外の場合は FALSE。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSnapInItemImpl:: CSnapInItemImpl](#csnapinitemimpl)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSnapInItemImpl:: AddMenuItems](#addmenuitems)|メニュー項目をコンテキストメニューに追加します。|
|[CSnapInItemImpl:: Command](#command)|カスタムメニュー項目が選択されたときにコンソールによって呼び出されます。|
|[CSnapInItemImpl:: CreatePropertyPages](#createpropertypages)|スナップインのプロパティシートにページを追加します。|
|[CSnapInItemImpl:: FillData](#filldata)|スナップインオブジェクトの情報を指定したストリームにコピーします。|
|[CSnapInItemImpl:: Getresultimpl Info](#getresultpaneinfo)|スナップイン `RESULTDATAITEM` の構造を取得します。|
|[CSnapInItemImpl:: GetResultViewType](#getresultviewtype)|結果ペインによって使用されるビューの種類を決定します。|
|[CSnapInItemImpl:: GetScopePaneInfo](#getscopepaneinfo)|スナップイン `SCOPEDATAITEM` の構造を取得します。|
|[CSnapInItemImpl:: Notify](#notify)|コンソールによって呼び出され、ユーザーによって実行されるアクションのスナップインを通知します。|
|[CSnapInItemImpl:: QueryPagesFor](#querypagesfor)|スナップインノードがプロパティページをサポートしているかどうかを確認するために呼び出されます。|
|[CSnapInItemImpl:: SetMenuInsertionFlags](#setmenuinsertionflags)|スナップインオブジェクトのメニュー挿入フラグを変更します。|
|[CSnapInItemImpl:: SetToolbarButtonInfo](#settoolbarbuttoninfo)|指定したツールバーボタンの情報を設定します。|
|[CSnapInItemImpl:: UpdateMenuState](#updatemenustate)|コンテキストメニュー項目の状態を更新します。|
|[CSnapInItemImpl:: UpdateToolbarButton](#updatetoolbarbutton)|指定したツールバーボタンの状態を更新します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CSnapInItemImpl:: m_bstrDisplayName](#m_bstrdisplayname)|スナップインオブジェクトの名前。|
|[CSnapInItemImpl:: m_resultDataItem](#m_resultdataitem)|`RESULTDATAITEM`オブジェクトによって使用される Windows 構造体 `CSnapInItemImpl` 。|
|[CSnapInItemImpl:: m_scopeDataItem](#m_scopedataitem)|`SCOPEDATAITEM`オブジェクトによって使用される Windows 構造体 `CSnapInItemImpl` 。|

## <a name="remarks"></a>解説

`CSnapInItemImpl` メニュー項目やツールバーの追加、スナップインノードのコマンドの転送など、スナップインノードオブジェクトの基本的な実装を提供します。 これらの機能は、いくつかの異なるインターフェイスとマップの種類を使用して実装されます。 既定の実装では、派生クラスの正しいインスタンスを決定し、適切なインスタンスにメッセージを転送することによって、node オブジェクトに送信される通知を処理します。

## <a name="inheritance-hierarchy"></a>継承階層

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlsnap. h

## <a name="csnapinitemimpladdmenuitems"></a><a name="addmenuitems"></a> CSnapInItemImpl:: AddMenuItems

このメソッドは、Win32 関数 [IExtendContextMenu:: AddMenuItems](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems)を実装します。

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>パラメーター

*piCallback*<br/>
から `IContextMenuCallback` コンテキストメニューに項目を追加できるへのポインター。

*許可された ppg tion*<br/>
[入力、出力]Microsoft 管理コンソール (MMC) で定義されている、使用可能なメニュー項目の挿入ポイントを識別します。 これは、次のフラグの組み合わせにすることができます。

- CCM_INSERTIONALLOWED_TOP の項目は、コンテキストメニューの上部に挿入できます。

- CCM_INSERTIONALLOWED_NEW の項目は、[新規作成] サブメニューに挿入できます。

- CCM_INSERTIONALLOWED_TASK の項目は、[タスク] サブメニューに挿入できます。

- CCM_INSERTIONALLOWED_VIEW の項目は、ツールバーの [表示] メニュー、または結果ペインのコンテキストメニューの [表示] サブメニューに挿入できます。

*type*<br/>
からオブジェクトの種類を指定します。 次のいずれかの値になります。

- スコープペインコンテキストのデータオブジェクトを CCT_SCOPE します。

- 結果ペインのコンテキストのデータオブジェクトを CCT_RESULT します。

- スナップインマネージャーコンテキストのデータオブジェクトを CCT_SNAPIN_MANAGER します。

- CCT_UNINITIALIZED データオブジェクトの型が無効です。

## <a name="csnapinitemimplcommand"></a><a name="command"></a> CSnapInItemImpl:: Command

このメソッドは、Win32 関数 [IExtendContextMenu:: Command](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-command)を実装します。

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>パラメーター

*lCommandID*<br/>
からメニュー項目のコマンド id を指定します。

*type*<br/>
からオブジェクトの種類を指定します。 次のいずれかの値になります。

- スコープペインコンテキストのデータオブジェクトを CCT_SCOPE します。

- 結果ペインのコンテキストのデータオブジェクトを CCT_RESULT します。

- スナップインマネージャーコンテキストのデータオブジェクトを CCT_SNAPIN_MANAGER します。

- CCT_UNINITIALIZED データオブジェクトの型が無効です。

## <a name="csnapinitemimplcreatepropertypages"></a><a name="createpropertypages"></a> CSnapInItemImpl:: CreatePropertyPages

このメソッドは、Win32 関数 [IExtendPropertySheet:: CreatePropertyPages](/windows/win32/api/mmc/nn-mmc-iextendpropertysheet2)を実装します。

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>パラメーター

*lpProvider*<br/>
からインターフェイスへのポインター `IPropertySheetCallback` 。

*扱え*<br/>
からMMCN_PROPERTY_CHANGE 通知メッセージを適切なデータクラスにルーティングするために使用するハンドルを指定します。

*パンク*<br/>
から `IExtendPropertySheet` ノードに関するコンテキスト情報を格納しているオブジェクト上のインターフェイスへのポインター。

*type*<br/>
からオブジェクトの種類を指定します。 次のいずれかの値になります。

- スコープペインコンテキストのデータオブジェクトを CCT_SCOPE します。

- 結果ペインのコンテキストのデータオブジェクトを CCT_RESULT します。

- スナップインマネージャーコンテキストのデータオブジェクトを CCT_SNAPIN_MANAGER します。

- CCT_UNINITIALIZED データオブジェクトの型が無効です。

## <a name="csnapinitemimplcsnapinitemimpl"></a><a name="csnapinitemimpl"></a> CSnapInItemImpl:: CSnapInItemImpl

`CSnapInItemImpl` オブジェクトを構築します。

```
CSnapInItemImpl();
```

## <a name="csnapinitemimplfilldata"></a><a name="filldata"></a> CSnapInItemImpl:: FillData

この関数は、項目に関する情報を取得するために呼び出されます。

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>パラメーター

*cf*<br/>
からクリップボードの形式 (テキスト、リッチテキスト、または OLE 項目を含むリッチテキスト)。

*pStream*<br/>
からオブジェクトデータを格納しているストリームへのポインター。

### <a name="remarks"></a>解説

この関数を適切に実装するには、 *cf* で示されたクリップボードの形式に応じて、正しい情報をストリーム (*pstream*) にコピーします。

## <a name="csnapinitemimplgetresultviewtype"></a><a name="getresultviewtype"></a> CSnapInItemImpl:: GetResultViewType

スナップインオブジェクトの結果ペインのビューの種類を取得するには、この関数を呼び出します。

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>パラメーター

*ppViewType*<br/>
入出力返されたビュー型のアドレスへのポインター。

*pViewOptions*<br/>
入出力MMC_VIEW_OPTIONS 列挙体へのポインター。コンソールには、所有しているスナップインによって指定されたオプションが用意されています。 この値は、次のいずれかです。

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0x00000001 は、[ **表示** ] メニューに標準のリストビューの選択肢を表示しないようにコンソールに指示します。 スナップインで、結果ビューペインにのみ独自のカスタムビューを表示できるようにします。 これは、現時点で定義されている唯一のオプションフラグです。

- MMC_VIEW_OPTIONS_NONE = 0 に設定すると、既定の表示オプションが使用できるようになります。

## <a name="csnapinitemimplgetscopepaneinfo"></a><a name="getscopepaneinfo"></a> CSnapInItemImpl:: GetScopePaneInfo

スナップインの構造を取得するには、この関数を呼び出し `SCOPEDATAITEM` ます。

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>パラメーター

*pScopeDataItem*<br/>
入出力 `SCOPEDATAITEM` オブジェクトの構造体へのポインター `CSnapInItemImpl` 。

## <a name="csnapinitemimplgetresultpaneinfo"></a><a name="getresultpaneinfo"></a> CSnapInItemImpl:: Getresultimpl Info

スナップインの構造を取得するには、この関数を呼び出し `RESULTDATAITEM` ます。

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>パラメーター

*pResultDataItem*<br/>
入出力 `RESULTDATAITEM` オブジェクトの構造体へのポインター `CSnapInItemImpl` 。

## <a name="csnapinitemimplm_bstrdisplayname"></a><a name="m_bstrdisplayname"></a> CSnapInItemImpl:: m_bstrDisplayName

ノード項目に対して表示される文字列を格納します。

```
CComBSTR m_bstrDisplayName;
```

## <a name="csnapinitemimplm_scopedataitem"></a><a name="m_scopedataitem"></a> CSnapInItemImpl:: m_scopeDataItem

`SCOPEDATAITEM`スナップインデータオブジェクトの構造。

```
SCOPEDATAITEM m_scopeDataItem;
```

## <a name="csnapinitemimplm_resultdataitem"></a><a name="m_resultdataitem"></a> CSnapInItemImpl:: m_resultDataItem

スナップインデータオブジェクトの [Resultdataitem](/windows/win32/api/mmc/ns-mmc-resultdataitem) 構造体。

```
RESULTDATAITEM m_resultDataItem;
```

## <a name="csnapinitemimplnotify"></a><a name="notify"></a> CSnapInItemImpl:: Notify

スナップインオブジェクトがユーザーによって操作されるときに呼び出されます。

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
からユーザーによって実行されるアクションを識別します。 次の通知が可能です。

- ウィンドウがアクティブ化され、非アクティブになったときに送信 MMCN_ACTIVATE ます。

- MMCN_ADD_IMAGES、結果ペインに画像を追加するために送信されます。

- MMCN_BTN_CLICK、ユーザーがツールバーのボタンのいずれかをクリックしたときに送信されます。

- ユーザーがリストビュー項目でマウスボタンをクリックしたときに送信される MMCN_CLICK ます。

- ユーザーがリストビューアイテムのマウスボタンをダブルクリックしたときに送信される MMCN_DBLCLICK ます。

- オブジェクトを削除する必要があることをスナップインに通知するために MMCN_DELETE 送信されます。

- フォルダーの展開または MMCN_EXPAND を行う必要がある場合に送信されます。

- ウィンドウが最小化または最大化されているときに送信 MMCN_MINIMIZED ます。

- スナップインオブジェクトのビューが変更されようとしていることをスナップインオブジェクトに通知するために MMCN_PROPERTY_CHANGE 送信されます。

- スナップインが、指定されたノードの下に追加されたサブツリー全体を削除する必要がある場合に送信 MMCN_REMOVE_CHILDREN ます。

- 名前変更をクエリするために最初に送信された MMCN_RENAME、2回目に名前の変更を行います。

- [スコープ] ウィンドウまたは結果ビューペイン内の項目が選択されたときに送信される MMCN_SELECT ます。

- スコープ項目が最初に選択または選択解除されたときに送信される MMCN_SHOW ます。

- 変更が発生したときにスナップインがすべてのビューを更新できる場合、MMCN_VIEW_CHANGE 送信されます。

*arg*<br/>
から通知の種類によって異なります。

*param*<br/>
から通知の種類によって異なります。

*pComponentData*<br/>
入出力を実装するオブジェクトへのポインター `IComponentData` 。 通知がから転送されていない場合、このパラメーターは NULL になり `IComponentData::Notify` ます。

*pComponent*<br/>
入出力を実装するオブジェクトへのポインター `IComponent` 。 通知がから転送されていない場合、このパラメーターは NULL になり `IComponent::Notify` ます。

*type*<br/>
からオブジェクトの種類を指定します。 次のいずれかの値になります。

- スコープペインコンテキストのデータオブジェクトを CCT_SCOPE します。

- 結果ペインのコンテキストのデータオブジェクトを CCT_RESULT します。

- スナップインマネージャーコンテキストのデータオブジェクトを CCT_SNAPIN_MANAGER します。

- CCT_UNINITIALIZED データオブジェクトの型が無効です。

## <a name="csnapinitemimplquerypagesfor"></a><a name="querypagesfor"></a> CSnapInItemImpl:: QueryPagesFor

スナップインノードがプロパティページをサポートしているかどうかを確認するために呼び出されます。

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

## <a name="csnapinitemimplsetmenuinsertionflags"></a><a name="setmenuinsertionflags"></a> CSnapInItemImpl:: SetMenuInsertionFlags

この関数を呼び出して、スナップインオブジェクトの *pインサーター Tionallowed* で指定されたメニュー挿入フラグを変更します。

```cpp
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>パラメーター

*bBeforeInsertion*<br/>
から項目をコンテキストメニューに追加する前に関数を呼び出す必要がある場合は0以外の場合は。それ以外の場合は0です。

*許可された ppg tion*<br/>
[入力、出力]Microsoft 管理コンソール (MMC) で定義されている、使用可能なメニュー項目の挿入ポイントを識別します。 これは、次のフラグの組み合わせにすることができます。

- CCM_INSERTIONALLOWED_TOP の項目は、コンテキストメニューの上部に挿入できます。

- CCM_INSERTIONALLOWED_NEW の項目は、[新規作成] サブメニューに挿入できます。

- CCM_INSERTIONALLOWED_TASK の項目は、[タスク] サブメニューに挿入できます。

- CCM_INSERTIONALLOWED_VIEW の項目は、ツールバーの [表示] メニュー、または結果ペインのコンテキストメニューの [表示] サブメニューに挿入できます。

### <a name="remarks"></a>解説

プライマリスナップインを開発している場合は、サードパーティの拡張機能によって追加できるメニュー項目の種類を制限する方法として、挿入フラグをリセットできます。 たとえば、プライマリスナップインは CCM_INSERTIONALLOWED_NEW フラグをクリアして、拡張機能によって独自の [新規作成] メニュー項目が追加されないようにすることができます。

最初はクリアされた *Ppg Tionallowed* にビットを設定しないようにしてください。 将来のバージョンの MMC では、現在定義されていないビットが使用される可能性があるため、現在定義されていないビットを変更することはできません。

## <a name="csnapinitemimplsettoolbarbuttoninfo"></a><a name="settoolbarbuttoninfo"></a> CSnapInItemImpl:: SetToolbarButtonInfo

ツールバーが作成される前に、スナップインオブジェクトのツールバーボタンのスタイルを変更するには、この関数を呼び出します。

```cpp
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>パラメーター

*id*<br/>
から設定するツールバーボタンの ID。

*fsState*<br/>
からボタンの状態フラグ。 次の1つまたは複数を指定できます。

- ボタンのスタイルが TBSTYLE_CHECKED TBSTATE_CHECKED、が押されています。

- TBSTATE_ENABLED ボタンはユーザー入力を受け入れます。 この状態を持たないボタンはユーザー入力を受け付けず、淡色表示になります。

- TBSTATE_HIDDEN ボタンが表示されず、ユーザー入力を受け取ることができません。

- TBSTATE_INDETERMINATE ボタンは淡色表示になっています。

- TBSTATE_PRESSED ボタンが押されていることを示します。

- ボタンの後に改行を TBSTATE_WRAP ます。 また、このボタンには TBSTATE_ENABLED が必要です。

*fsType*<br/>
からボタンの状態フラグ。 次の1つまたは複数を指定できます。

- TBSTYLE_BUTTON は、標準のプッシュボタンを作成します。

- TBSTYLE_CHECK は、ユーザーがクリックするたびに押された状態と押されていない状態を切り替えるボタンを作成します。 ボタンの背景色は、押された状態のときに異なります。

- TBSTYLE_CHECKGROUP によって、グループ内の別のボタンが押されるまで押された状態のチェックボタンが作成されます。

- TBSTYLE_GROUP によって、グループ内の別のボタンが押されるまで押されたままになるボタンが作成されます。

- TBSTYLE_SEP によって区切り文字が作成され、ボタングループ間のギャップが小さくなります。 このスタイルのボタンは、ユーザー入力を受け取りません。

## <a name="csnapinitemimplupdatemenustate"></a><a name="updatemenustate"></a> CSnapInItemImpl:: UpdateMenuState

スナップインオブジェクトのコンテキストメニューにメニュー項目を挿入する前に、この関数を呼び出してメニュー項目を変更します。

```cpp
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>パラメーター

*id*<br/>
から設定するメニュー項目の ID。

*pBuf*<br/>
から更新するメニュー項目の文字列へのポインター。

*flags*<br/>
から新しい状態フラグを指定します。 これは、次のフラグの組み合わせにすることができます。

- MF_POPUP は、これがショートカットメニュー内のサブメニューであることを指定します。 メニュー項目、挿入ポイント、およびその他のサブメニューは、をとして使用することで、このサブメニューに追加でき `lCommandID` `IInsertionPointID` ます。

- これらのフラグを MF_BITMAP および MF_OWNERDRAW することは許可されていません。 E_INVALIDARG の戻り値になります。

- MF_SEPARATOR は、水平方向の区切り線を描画します。 `IContextMenuProvider`MF_SEPARATOR セットを持つメニュー項目を追加できるのはのみです。

- MF_CHECKED メニュー項目の横にチェックマークを付けます。

- メニュー項目を選択できないように MF_DISABLED 無効にしますが、フラグは灰色になりません。

- メニュー項目を選択して灰色の状態から復元できるようにするには、MF_ENABLED します。

- メニュー項目を無効に MF_GRAYED、選択できないように graying します。

- MF_MENUBARBREAK 関数は、メニューバーの MF_MENUBREAK フラグと同じです。 ドロップダウンメニュー、サブメニュー、またはショートカットメニューの場合、新しい列は、前の列から縦線で区切られます。

- MF_MENUBREAK は、列を区切ることなく、新しい行 (メニューバーの場合) または新しい列 (ドロップダウンメニュー、サブメニュー、またはショートカットメニュー) に項目を配置します。

- MF_UNCHECKED は、項目の横にチェックマークを付けません (既定)。

次のフラグのグループを一緒に使用することはできません。

- MF_DISABLED、MF_ENABLED、および MF_GRAYED。

- MF_MENUBARBREAK と MF_MENUBREAK。

- MF_CHECKED と MF_UNCHECKED。

## <a name="csnapinitemimplupdatetoolbarbutton"></a><a name="updatetoolbarbutton"></a> CSnapInItemImpl:: UpdateToolbarButton

スナップインオブジェクトのツールバーボタンを表示する前に変更するには、この関数を呼び出します。

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>パラメーター

*id*<br/>
更新するツールバーボタンのボタン ID を指定します。

*fsState*<br/>
ツールバーボタンの状態を指定します。 この状態を設定する場合は、TRUE を返します。 これは、次のフラグの組み合わせにすることができます。

- [有効] に設定すると、ユーザー入力が受け入れられます。 この状態を持たないボタンはユーザー入力を受け付けず、淡色表示になります。

- チェックボックスがオンになっていることを確認します。

- [非表示] ボタンは表示されず、ユーザー入力を受け取ることはできません。

- [不確定] ボタンがグレーで表示されます。

- BUTTONPRESSED れたボタンが押されています。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
