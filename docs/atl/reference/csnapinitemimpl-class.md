---
title: CSnapInItemImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 759917497f06f80cde97f4e1bba9f3711add94a8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366459"
---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl クラス
このクラスは、スナップイン ノード オブジェクトを実装するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, BOOL bIsExtension = FALSE>  
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`CSnapInItemImpl`です。  
  
 *bIsExtension*  
 **TRUE**オブジェクトがスナップイン拡張機能の場合それ以外の場合**FALSE**です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|コンテキスト メニューにメニュー項目を追加します。|  
|[CSnapInItemImpl::Command](#command)|カスタム メニュー項目が選択されているときに、コンソールによって呼び出されます。|  
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|スナップインのプロパティ シートにページを追加します。|  
|[CSnapInItemImpl::FillData](#filldata)|指定したストリームに、スナップイン オブジェクト上の情報をコピーします。|  
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|取得、 **RESULTDATAITEM**スナップインの構造。|  
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|結果ウィンドウで使用されたビューの種類を決定します。|  
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|取得、 **SCOPEDATAITEM**スナップインの構造。|  
|[CSnapInItemImpl::Notify](#notify)|ユーザーによって実行されたアクションのスナップインに通知するコンソールによって呼び出されます。|  
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|スナップインでノードにプロパティ ページでサポートされているかどうかに呼び出されます。|  
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|スナップインでオブジェクトのメニュー挿入フラグを変更します。|  
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|指定されたツール バー ボタンの情報を設定します。|  
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|コンテキスト メニュー項目の状態を更新します。|  
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|指定されたツール バー ボタンの状態を更新します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|スナップインでオブジェクトの名前。|  
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Windows **RESULTDATAITEM**構造で使用される、`CSnapInItemImpl`オブジェクト。|  
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Windows **SCOPEDATAITEM**構造で使用される、`CSnapInItemImpl`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CSnapInItemImpl` メニュー項目やツールバーを追加して、適切なハンドラー関数にスナップイン ノード用のコマンドの転送などのスナップインでノード オブジェクトの基本的な実装を提供します。 これらの機能は、複数のインターフェイスを使用して実装し、型をマップします。 既定の実装では、派生クラスの適切なインスタンスを特定し、適切なインスタンスにメッセージを転送して、ノード オブジェクトに送信する通知を処理します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsnap.h  
  
##  <a name="addmenuitems"></a>  CSnapInItemImpl::AddMenuItems  
 このメソッドは、Win32 関数を実装します。 [IExtendContextMenu::AddMenuItems](http://msdn.microsoft.com/library/aa814841)です。  
  
```
AddMenuItems(  
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>パラメーター  
 *piCallback*  
 [in]ポインター、 **IContextMenuCallback**コンテキスト メニューに項目を追加することができます。  
  
 `pInsertionAllowed`  
 [入力、出力].識別 Microsoft 管理コンソール MMC 定義メニュー項目挿入ポイントを使用することができます。 これにより、次のフラグの組み合わせが可能します。  
  
- **CCM_INSERTIONALLOWED_TOP**コンテキスト メニューの上部にある項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_NEW**新規作成 サブメニューで項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_TASK**タスク サブメニューに項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_VIEW**や結果ウィンドウのコンテキスト メニューのサブメニューの表示 ツールバーの表示 メニューで、項目を挿入することができます。  
  
 `type`  
 [in]オブジェクトの種類を指定します。 次の値のいずれかを取ります。  
  
- **CCT_SCOPE**スコープ ウィンドウのコンテキストのデータ オブジェクト。  
  
- **CCT_RESULT**データ コンテキスト オブジェクトを結果ペイン。  
  
- **CCT_SNAPIN_MANAGER**マネージャー スナップインでコンテキストのデータ オブジェクト。  
  
- **CCT_UNINITIALIZED**データ オブジェクトには型が無効です。  
  
##  <a name="command"></a>  CSnapInItemImpl::Command  
 このメソッドは、Win32 関数を実装します。 [IExtendContextMenu::Command](http://msdn.microsoft.com/library/aa814842)です。  
  
```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>パラメーター  
 *lCommandID*  
 [in]メニュー項目のコマンド識別子を指定します。  
  
 `type`  
 [in]オブジェクトの種類を指定します。 次の値のいずれかを取ります。  
  
- **CCT_SCOPE**スコープ ウィンドウのコンテキストのデータ オブジェクト。  
  
- **CCT_RESULT**データ コンテキスト オブジェクトを結果ペイン。  
  
- **CCT_SNAPIN_MANAGER**マネージャー スナップインでコンテキストのデータ オブジェクト。  
  
- **CCT_UNINITIALIZED**データ オブジェクトには型が無効です。  
  
##  <a name="createpropertypages"></a>  CSnapInItemImpl::CreatePropertyPages  
 このメソッドは、Win32 関数を実装します。 [IExtendPropertySheet::CreatePropertyPages](http://msdn.microsoft.com/library/aa814846)です。  
  
```
CreatePropertyPages(  
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpProvider*  
 [in]ポインター、**プロパティ シート フレーム**インターフェイスです。  
  
 *handle*  
 [in]使用するハンドルを指定ルートに、 **MMCN_PROPERTY_CHANGE**適切なデータ クラスに通知メッセージです。  
  
 *pUnk*  
 [in]ポインター、 **IExtendPropertySheet**ノードに関するコンテキスト情報を格納しているオブジェクトのインターフェイスです。  
  
 `type`  
 [in]オブジェクトの種類を指定します。 次の値のいずれかを取ります。  
  
- **CCT_SCOPE**スコープ ウィンドウのコンテキストのデータ オブジェクト。  
  
- **CCT_RESULT**データ コンテキスト オブジェクトを結果ペイン。  
  
- **CCT_SNAPIN_MANAGER**マネージャー スナップインでコンテキストのデータ オブジェクト。  
  
- **CCT_UNINITIALIZED**データ オブジェクトには型が無効です。  
  
##  <a name="csnapinitemimpl"></a>  CSnapInItemImpl::CSnapInItemImpl  
 `CSnapInItemImpl` オブジェクトを構築します。  
  
```
CSnapInItemImpl();
```  
  
##  <a name="filldata"></a>  CSnapInItemImpl::FillData  
 この関数は、項目に関する情報を取得します。  
  
```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 [in]クリップボードの形式 (テキスト、リッチ テキスト、または OLE 項目を含む、リッチ テキスト)。  
  
 `pStream`  
 [in]オブジェクトのデータを格納しているストリームへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数を正しく実装するのには、ストリームに、正しい情報をコピー ( `pStream`) によって示されるクリップボードの形式に応じて、`cf`です。  
  
##  <a name="getresultviewtype"></a>  CSnapInItemImpl::GetResultViewType  
 この関数では、スナップイン オブジェクトの結果ペインのビューの型を取得します。  
  
```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```  
  
### <a name="parameters"></a>パラメーター  
 *取得可能です。*  
 [out]返されたビューの種類のアドレスへのポインター。  
  
 *pViewOptions*  
 [out]ポインター、 **MMC_VIEW_OPTIONS**列挙体は、所有するスナップインによって指定されたオプションで、コンソールを提供します。 この値は、次のいずれかになります。  
  
- **MMC_VIEW_OPTIONS_NOLISTVIEWS** = 0x00000001 で標準のリスト ビューの選択肢を表示しないようにするにはコンソールに指示、**ビュー**メニュー。 スナップインだけ、結果ビュー ペインで、独自のカスタム ビューを表示できます。 これは、この時点で定義されている唯一のオプション フラグです。  
  
- **MMC_VIEW_OPTIONS_NONE** 0 が既定の表示オプションを = です。  
  
##  <a name="getscopepaneinfo"></a>  CSnapInItemImpl::GetScopePaneInfo  
 取得するには、この関数を呼び出して、 **SCOPEDATAITEM**スナップインの構造。  
  
```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pScopeDataItem*  
 [out]ポインター、 **SCOPEDATAITEM**の構造、`CSnapInItemImpl`オブジェクト。  
  
##  <a name="getresultpaneinfo"></a>  CSnapInItemImpl::GetResultPaneInfo  
 取得するには、この関数を呼び出して、 **RESULTDATAITEM**スナップインの構造。  
  
```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pResultDataItem*  
 [out]ポインター、 **RESULTDATAITEM**の構造、`CSnapInItemImpl`オブジェクト。  
  
##  <a name="m_bstrdisplayname"></a>  CSnapInItemImpl::m_bstrDisplayName  
 ノードのアイテムに表示される文字列が含まれています。  
  
```
CComBSTR m_bstrDisplayName;
```  
  
##  <a name="m_scopedataitem"></a>  CSnapInItemImpl::m_scopeDataItem  
 `SCOPEDATAITEM`スナップイン データ オブジェクトの構造体。  
  
```
SCOPEDATAITEM m_scopeDataItem;
```  
  
##  <a name="m_resultdataitem"></a>  CSnapInItemImpl::m_resultDataItem  
 [RESULTDATAITEM](http://msdn.microsoft.com/library/aa815165)スナップイン データ オブジェクトの構造体。  
  
```
RESULTDATAITEM m_resultDataItem;
```  
  
##  <a name="notify"></a>  CSnapInItemImpl::Notify  
 ユーザーによって、スナップイン オブジェクトを操作したときに呼び出されます。  
  
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
 `event`  
 [in]ユーザーが行うアクションを識別します。 次の通知が考えられます。  
  
- **MMCN_ACTIVATE**がアクティブ化、非アクティブ化は、時、ウィンドウに送信します。  
  
- **MMCN_ADD_IMAGES**イメージを追加する、結果ウィンドウに送信します。  
  
- **MMCN_BTN_CLICK**ツール バー ボタンのいずれかのユーザーがクリックしたときに送信します。  
  
- **MMCN_CLICK**ユーザーがリスト ビューの項目上でマウス ボタンをクリックしたときに送信します。  
  
- **MMCN_DBLCLICK**ユーザーがリスト ビューの項目上でマウス ボタンをダブルクリックすると送信されます。  
  
- **MMCN_DELETE**スナップイン オブジェクトを通知するために送信された削除します。  
  
- **MMCN_EXPAND**フォルダーを展開または縮小する必要があるときに送信します。  
  
- **MMCN_MINIMIZED**最小または最大化されているが、ウィンドウの場合に送信します。  
  
- **MMCN_PROPERTY_CHANGE**を変更する、スナップイン オブジェクトのビューがあるスナップイン オブジェクトに通知を送信します。  
  
- **MMCN_REMOVE_CHILDREN**のスナップインで、指定したノードの下に追加全体のサブツリーを削除する必要がある時に送信します。  
  
- **MMCN_RENAME**を名前の変更を行うには、名前の変更のクエリを初めてと 2 番目の時間を送信します。  
  
- **MMCN_SELECT**スコープまたは結果の表示ウィンドウ内の項目が選択されているときに送信します。  
  
- **MMCN_SHOW**スコープ項目が選択されているかを初めて選択解除されたときに送信します。  
  
- **MMCN_VIEW_CHANGE**のスナップインですべてのビューを更新、変更が発生したときにときに送信します。  
  
 `arg`  
 [in]通知の種類によって異なります。  
  
 `param`  
 [in]通知の種類によって異なります。  
  
 *pComponentData*  
 [out]実装するオブジェクトへのポインター **IComponentData**です。 このパラメーターは**NULL**場合は、通知がから転送されていません**IComponentData::Notify**です。  
  
 *pComponent*  
 [out]実装するオブジェクトへのポインター **IComponent**です。 このパラメーターは**NULL**場合は、通知がから転送されていません**IComponent::Notify**です。  
  
 `type`  
 [in]オブジェクトの種類を指定します。 次の値のいずれかを取ります。  
  
- **CCT_SCOPE**スコープ ウィンドウのコンテキストのデータ オブジェクト。  
  
- **CCT_RESULT**データ コンテキスト オブジェクトを結果ペイン。  
  
- **CCT_SNAPIN_MANAGER**マネージャー スナップインでコンテキストのデータ オブジェクト。  
  
- **CCT_UNINITIALIZED**データ オブジェクトには型が無効です。  
  
##  <a name="querypagesfor"></a>  CSnapInItemImpl::QueryPagesFor  
 スナップインでノードにプロパティ ページでサポートされているかどうかに呼び出されます。  
  
```
QueryPagesFor(DATA_OBJECT_TYPES type);
```  
  
##  <a name="setmenuinsertionflags"></a>  CSnapInItemImpl::SetMenuInsertionFlags  
 指定された メニューの挿入のフラグを変更するには、この関数を呼び出す`pInsertionAllowed`、スナップイン オブジェクト。  
  
```
void SetMenuInsertionFlags(  
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```  
  
### <a name="parameters"></a>パラメーター  
 *bBeforeInsertion*  
 [in]以外の場合は、コンテキスト メニューに項目を追加する前に、関数を呼び出す必要があります。それ以外の場合 0 を返します。  
  
 `pInsertionAllowed`  
 [入力、出力].識別 Microsoft 管理コンソール MMC 定義メニュー項目挿入ポイントを使用することができます。 これにより、次のフラグの組み合わせが可能します。  
  
- **CCM_INSERTIONALLOWED_TOP**コンテキスト メニューの上部にある項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_NEW**新規作成 サブメニューで項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_TASK**タスク サブメニューに項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_VIEW**や結果ウィンドウのコンテキスト メニューのサブメニューの表示 ツールバーの表示 メニューで、項目を挿入することができます。  
  
### <a name="remarks"></a>コメント  
 プライマリのスナップインを開発している場合は、サード パーティ製の拡張機能を追加するメニュー項目の種類を制限する方法として挿入フラグのいずれかをリセットできます。 たとえば、プライマリ、スナップインをオフ、 **CCM_INSERTIONALLOWED_NEW**拡張機能が、独自の新規作成メニュー項目を追加するを防ぐためのフラグ。  
  
 のビットを設定しないで`pInsertionAllowed`を最初に消去されました。 MMC の将来のバージョンでは、bits が定義されていない現在が変わらないようにするために定義されていない bits を使用できます。  
  
##  <a name="settoolbarbuttoninfo"></a>  CSnapInItemImpl::SetToolbarButtonInfo  
 この関数では、ツールバーを作成する前に、スナップイン オブジェクトのツール バー ボタンのスタイルを変更します。  
  
```
void SetToolbarButtonInfo(  
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]設定する、ツール バー ボタンの ID。  
  
 `fsState`  
 [in]ボタンの状態フラグ。 次の 1 つ以上を指定できます。  
  
- `TBSTATE_CHECKED` このボタンは、**スタイル**スタイルを設定して、押されました。  
  
- `TBSTATE_ENABLED` ボタンは、ユーザー入力を受け入れます。 この状態がないボタンは、ユーザー入力は受け付けられません、淡色表示にします。  
  
- `TBSTATE_HIDDEN` ボタンが表示されていないと、ユーザー入力を受け取ることはできません。  
  
- `TBSTATE_INDETERMINATE` ボタンは淡色表示にします。  
  
- `TBSTATE_PRESSED` ボタンが押されたされています。  
  
- `TBSTATE_WRAP` 行の区切りには、ボタンが次に示します。 ボタンが必要、`TBSTATE_ENABLED`です。  
  
 *すれば*  
 [in]ボタンの状態フラグ。 次の 1 つ以上を指定できます。  
  
- `TBSTYLE_BUTTON` 標準プッシュ ボタンを作成します。  
  
- `TBSTYLE_CHECK` 押された状態と not 押された状態、ユーザーがクリックするたびを切り替えるボタンを作成します。 ボタンには、別の背景色は、押された状態にあるときです。  
  
- `TBSTYLE_CHECKGROUP` グループ内の別のボタンが押されるまで押されたチェック ボタンを作成します。  
  
- `TBSTYLE_GROUP` グループ内の別のボタンが押されるまで押されたボタンを作成します。  
  
- `TBSTYLE_SEP` ボタンのグループ間で小さなギャップを提供する、区切り記号を作成します。 このスタイルを持つボタンは、ユーザー入力を受け取りません。  
  
##  <a name="updatemenustate"></a>  CSnapInItemImpl::UpdateMenuState  
 この関数では、スナップイン オブジェクトのコンテキスト メニューに挿入される前に、メニュー項目を変更します。  
  
```
void UpdateMenuState(  
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]設定するメニュー項目の ID。  
  
 `pBuf`  
 [in]更新するメニュー項目の文字列へのポインター。  
  
 `flags`  
 [in]新しい状態フラグを指定します。 これにより、次のフラグの組み合わせが可能します。  
  
- **ならば**これが、コンテキスト メニューのサブメニューであることを指定します。 このサブメニューを使用するメニュー項目を挿入ポイント、およびさらにサブメニューを追加する可能性があります、 **lCommandID**としてその**IInsertionPointID**です。  
  
- **MF_BITMAP**と`MF_OWNERDRAW`これらのフラグが許可されておらず、戻り値になります`E_INVALIDARG`です。  
  
- **MF_SEPARATOR**水平分割線を描画します。 のみ**IContextMenuProvider**でメニュー項目の追加が許可された**MF_SEPARATOR**を設定します。  
  
- **MF_CHECKED**メニュー項目の横にチェックマークを付けます。  
  
- **MF_DISABLED**のため、これを選択することはできませんが、このフラグは灰色ではないことに、メニュー項目を無効にします。  
  
- `MF_ENABLED` メニュー項目は、選択できるように、灰色表示されている状態から復元するために使用できます。  
  
- **MF_GRAYED**選択することはできませんので灰色表示に、メニュー項目を無効にします。  
  
- **MF_MENUBARBREAK**と同様に機能、 **MF_MENUBREAK**メニュー バーのフラグ。 ドロップダウン メニューのサブメニュー、またはショートカット メニューの新しい列は垂直線で、古い列からに区切られます。  
  
- **MF_MENUBREAK** (メニュー バー) の新しい行にアイテムを配置または列を分離することがなく (ドロップダウン メニュー、サブメニュー、ショートカット メニューの) を新しい列にします。  
  
- **MF_UNCHECKED**項目 (既定値) の横にあるチェック マークは配置されません。  
  
 次のフラグのグループを一緒に使用できません。  
  
- **MF_DISABLED**、 `MF_ENABLED`、および**MF_GRAYED**です。  
  
- **MF_MENUBARBREAK**と**MF_MENUBREAK**です。  
  
- **MF_CHECKED**と**MF_UNCHECKED**です。  
  
##  <a name="updatetoolbarbutton"></a>  CSnapInItemImpl::UpdateToolbarButton  
 表示される前に、スナップイン オブジェクトのツールバーのボタンを変更するには、この関数を呼び出します。  
  
```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 更新する、ツール バー ボタンのボタン ID を指定します。  
  
 `fsState`  
 ツール バー ボタンの状態を指定します。 この状態を設定する場合は、返す**TRUE**です。 これにより、次のフラグの組み合わせが可能します。  
  
- **有効になっている**ボタンはユーザー入力を受け入れます。 この状態がないボタンは、ユーザー入力は受け付けられません、淡色表示にします。  
  
- **チェック**にこのボタンは、**チェック**スタイルを設定して、押されました。  
  
- **HIDDEN**ボタンが表示されていないと、ユーザー入力を受け取ることはできません。  
  
- **不確定な**ボタンが淡色表示されます。  
  
- **BUTTONPRESSED**ボタンが押されました。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
