---
title: CCmdTarget クラス
ms.date: 11/04/2016
f1_keywords:
- CCmdTarget
- AFXWIN/CCmdTarget
- AFXWIN/CCmdTarget::CCmdTarget
- AFXWIN/CCmdTarget::BeginWaitCursor
- AFXWIN/CCmdTarget::DoOleVerb
- AFXWIN/CCmdTarget::EnableAutomation
- AFXWIN/CCmdTarget::EnableConnections
- AFXWIN/CCmdTarget::EnableTypeLib
- AFXWIN/CCmdTarget::EndWaitCursor
- AFXWIN/CCmdTarget::EnumOleVerbs
- AFXWIN/CCmdTarget::FromIDispatch
- AFXWIN/CCmdTarget::GetDispatchIID
- AFXWIN/CCmdTarget::GetIDispatch
- AFXWIN/CCmdTarget::GetTypeInfoCount
- AFXWIN/CCmdTarget::GetTypeInfoOfGuid
- AFXWIN/CCmdTarget::GetTypeLib
- AFXWIN/CCmdTarget::GetTypeLibCache
- AFXWIN/CCmdTarget::IsInvokeAllowed
- AFXWIN/CCmdTarget::IsResultExpected
- AFXWIN/CCmdTarget::OnCmdMsg
- AFXWIN/CCmdTarget::OnFinalRelease
- AFXWIN/CCmdTarget::RestoreWaitCursor
helpviewer_keywords:
- CCmdTarget [MFC], CCmdTarget
- CCmdTarget [MFC], BeginWaitCursor
- CCmdTarget [MFC], DoOleVerb
- CCmdTarget [MFC], EnableAutomation
- CCmdTarget [MFC], EnableConnections
- CCmdTarget [MFC], EnableTypeLib
- CCmdTarget [MFC], EndWaitCursor
- CCmdTarget [MFC], EnumOleVerbs
- CCmdTarget [MFC], FromIDispatch
- CCmdTarget [MFC], GetDispatchIID
- CCmdTarget [MFC], GetIDispatch
- CCmdTarget [MFC], GetTypeInfoCount
- CCmdTarget [MFC], GetTypeInfoOfGuid
- CCmdTarget [MFC], GetTypeLib
- CCmdTarget [MFC], GetTypeLibCache
- CCmdTarget [MFC], IsInvokeAllowed
- CCmdTarget [MFC], IsResultExpected
- CCmdTarget [MFC], OnCmdMsg
- CCmdTarget [MFC], OnFinalRelease
- CCmdTarget [MFC], RestoreWaitCursor
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
ms.openlocfilehash: 5ee4101302322a5212a80b32f095cdd13d9769e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352284"
---
# <a name="ccmdtarget-class"></a>CCmdTarget クラス

Microsoft ファウンデーション クラス ライブラリのメッセージ マップ アーキテクチャの基本クラス。

## <a name="syntax"></a>構文

```
class CCmdTarget : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CCmdターゲット::CCmdターゲット](#ccmdtarget)|`CCmdTarget` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を開始します。](#beginwaitcursor)|カーソルを砂時計カーソルとして表示します。|
|[をクリック :Dします。](#dooleverb)|OLE 動詞によって指定されたアクションを実行します。|
|[CCmdターゲット::オートメーションを有効にする](#enableautomation)|オブジェクトの OLE`CCmdTarget`オートメーションを許可します。|
|[接続を有効にします。](#enableconnections)|コネクション ポイントを介したイベントの発生を有効にします。|
|[をクリックします。](#enabletypelib)|オブジェクトのタイプ ライブラリを有効にします。|
|[をクリックします。](#endwaitcursor)|前のカーソルに戻ります。|
|[をクリックします。](#enumoleverbs)|オブジェクトの OLE 動詞を列挙します。|
|[次のコマンドを使用します。](#fromidispatch)|ポインターに関連付けられた`CCmdTarget`オブジェクトへのポインターを`IDispatch`返します。|
|[をクリックします。](#getdispatchiid)|プライマリ ディスパッチ インターフェイス ID を取得します。|
|[をクリックします。](#getidispatch)|オブジェクトに関連付けられた`IDispatch`オブジェクトへのポインターを`CCmdTarget`返します。|
|[をクリックします。](#gettypeinfocount)|オブジェクトが提供する型情報インターフェイスの数を取得します。|
|[を取得します。](#gettypeinfoofguid)|指定された GUID に対応するタイプ記述を取得します。|
|[をクリックします。](#gettypelib)|タイプ ライブラリへのポインターを取得します。|
|[をクリックします。](#gettypelibcache)|タイプ ライブラリ キャッシュを取得します。|
|[を呼び出すことができます。](#isinvokeallowed)|オートメーション メソッドの呼び出しを有効にします。|
|[期待される結果を示します。](#isresultexpected)|オートメーション関数が値を返す必要がある場合は、0 以外を返します。|
|[をクリックします。](#oncmdmsg)|コマンド メッセージをルーティングおよびディスパッチします。|
|[CCmdターゲット::オンファイナルリリース](#onfinalrelease)|最後の OLE 参照が解放された後にクリーンアップします。|
|[をクリックします。](#restorewaitcursor)|砂時計カーソルを復元します。|

## <a name="remarks"></a>解説

メッセージ マップは、コマンドまたはメッセージを処理するために記述したメンバー関数にルーティングします。 (コマンドは、メニュー項目、コマンド ボタン、またはアクセラレータ キーからのメッセージです)。

派生`CCmdTarget`する主要なフレームワーク クラスには[、CView](../../mfc/reference/cview-class.md) [、CWinApp、CDocument](../../mfc/reference/cwinapp-class.md) [、CWnd](../../mfc/reference/cwnd-class.md)、および[CFrameWnd](../../mfc/reference/cframewnd-class.md)が含まれます。 [CDocument](../../mfc/reference/cdocument-class.md) メッセージを処理する新しいクラスを作成する場合は、これらの`CCmdTarget`派生クラスの 1 つから派生します。 `CCmdTarget`クラスを直接派生させることはめったにありません。

コマンド`OnCmdMsg`ターゲットとルーティングの概要については、「[コマンド ターゲット](../../mfc/command-targets.md)」、「コマンド[ルーティング](../../mfc/command-routing.md)」、「[メッセージのマッピング](../../mfc/mapping-messages.md)」を参照してください。

`CCmdTarget`には、砂時計カーソルの表示を処理するメンバー関数が含まれています。 コマンドが実行する時間間隔が顕著になると予想される場合は、砂時計カーソルを表示します。

メッセージ マップと同様に、ディスパッチ マップを使用して`IDispatch`OLE オートメーション機能を公開します。 このインターフェイスを公開することにより、他のアプリケーション (Visual Basic など) がアプリケーションを呼び出すことができます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="ccmdtargetbeginwaitcursor"></a><a name="beginwaitcursor"></a>を開始します。

コマンドが実行する時間間隔が顕著になると予想される場合に、カーソルを砂時計として表示します。

```
void BeginWaitCursor();
```

### <a name="remarks"></a>解説

フレームワークは、オブジェクトが読み込みまたはファイルに自分自身を保存するとき`CDocument`など、ビジー状態であることをユーザーに示すために、この関数を呼び出します。

のアクション`BeginWaitCursor`は、処理などの`OnSetCursor`他のアクションがカーソルを変更する可能性があるため、単一のメッセージ ハンドラの外部では常に有効であるとは限りません。

前`EndWaitCursor`のカーソルを復元するために呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetccmdtarget"></a><a name="ccmdtarget"></a>CCmdターゲット::CCmdターゲット

`CCmdTarget` オブジェクトを構築します。

```
CCmdTarget();
```

## <a name="ccmdtargetdooleverb"></a><a name="dooleverb"></a>をクリック :Dします。

OLE 動詞によって指定されたアクションを実行します。

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*i動詞*<br/>
動詞の数値識別子。

*をクリックします。*<br/>
動詞を呼び出したイベント (ダブルクリックなど) を記述する[MSG](/windows/win32/api/winuser/ns-winuser-msg)構造体へのポインター。

*スーンドペアレント*<br/>
オブジェクトを保持しているドキュメント ウィンドウのハンドル。

*Lprect*<br/>
*hwndParent*でオブジェクトの外接する四角形を定義する座標 (ピクセル単位) を含む[RECT](/previous-versions/dd162897\(v=vs.85\))構造体へのポインター。

### <a name="return-value"></a>戻り値

TRUE が成功した場合は FALSE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメンバー関数は、基本的に[IOleObject::DoVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb)の実装です。 可能なアクションは[、CCmd ターゲット::列挙動詞](#enumoleverbs)によって列挙されます。

## <a name="ccmdtargetenableautomation"></a><a name="enableautomation"></a>CCmdターゲット::オートメーションを有効にする

オブジェクトの OLE オートメーションを有効にします。

```
void EnableAutomation();
```

### <a name="remarks"></a>解説

この関数は、通常、オブジェクトのコンストラクターから呼び出され、クラスに対してディスパッチ マップが宣言されている場合にのみ呼び出されます。 オートメーションの詳細については、「[オートメーション クライアントとオートメーション](../../mfc/automation-clients.md)[サーバー」を](../../mfc/automation-servers.md)参照してください。

## <a name="ccmdtargetenableconnections"></a><a name="enableconnections"></a>接続を有効にします。

コネクション ポイントを介したイベントの発生を有効にします。

```
void EnableConnections();
```

### <a name="remarks"></a>解説

コネクション ポイントを有効にするには、派生クラスのコンストラクターでこのメンバー関数を呼び出します。

## <a name="ccmdtargetenabletypelib"></a><a name="enabletypelib"></a>をクリックします。

オブジェクトのタイプ ライブラリを有効にします。

```
void EnableTypeLib();
```

### <a name="remarks"></a>解説

型情報を提供する場合は、派生`CCmdTarget`オブジェクトのコンストラクターでこのメンバー関数を呼び出します。

## <a name="ccmdtargetendwaitcursor"></a><a name="endwaitcursor"></a>をクリックします。

砂時計カーソルから前の`BeginWaitCursor`カーソルに戻るメンバー関数を呼び出した後、この関数を呼び出します。

```
void EndWaitCursor();
```

### <a name="remarks"></a>解説

フレームワークは、砂時計カーソルを呼び出した後もこのメンバー関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="ccmdtargetenumoleverbs"></a><a name="enumoleverbs"></a>をクリックします。

オブジェクトの OLE 動詞を列挙します。

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[インターフェイスへの](/windows/win32/api/oleidl/nn-oleidl-ienumoleverb)ポインターへのポインター。

### <a name="return-value"></a>戻り値

オブジェクトが少なくとも 1 つの OLE 動詞 (\*この場合*は ppenumOleVerb*が列挙子インターフェイスを指す) を`IEnumOLEVERB`サポートしている場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメンバー関数は基本的に[IOleObject::列挙動詞の実装です](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs)。

## <a name="ccmdtargetfromidispatch"></a><a name="fromidispatch"></a>次のコマンドを使用します。

クラスのオートメーション メンバー関数`IDispatch`から受け取ったポインターを、`CCmdTarget``IDispatch`オブジェクトのインターフェイスを実装するオブジェクトにマップします。

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>パラメーター

*を割り出す*<br/>
`IDispatch` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

*lpDispatch*に`CCmdTarget`関連付けられているオブジェクトへのポインター。 オブジェクトが`IDispatch`Microsoft ファウンデーション クラス`IDispatch`オブジェクトとして認識されない場合、この関数は NULL を返します。

### <a name="remarks"></a>解説

この関数の結果は、メンバー関数 の呼び出しの逆`GetIDispatch`です。

## <a name="ccmdtargetgetdispatchiid"></a><a name="getdispatchiid"></a>をクリックします。

プライマリ ディスパッチ インターフェイス ID を取得します。

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>パラメーター

*pIID*<br/>
インターフェイス ID [(GUID](/previous-versions/cc317743(v%3dmsdn.10))) へのポインター。

### <a name="return-value"></a>戻り値

TRUE が成功した場合は FALSE、それ以外の場合は FALSE。 成功した場合\**、pIID*はプライマリ ディスパッチ インターフェイス ID に設定されます。

### <a name="remarks"></a>解説

派生クラスは、このメンバー関数をオーバーライドする必要があります`GetDispatchIID`(オーバーライドされていない場合は FALSE を返します)。 [「コントロールコントロール」を](../../mfc/reference/colecontrol-class.md)参照してください。

## <a name="ccmdtargetgetidispatch"></a><a name="getidispatch"></a>をクリックします。

ポインターを返すか、参照によって`IDispatch`ポインターを受け取るオートメーション メソッド`IDispatch`からポインターを`IDispatch`取得します。

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>パラメーター

*参照を追加します。*<br/>
オブジェクトの参照カウントをインクリメントするかどうかを指定します。

### <a name="return-value"></a>戻り値

オブジェクト`IDispatch`に関連付けられているポインター。

### <a name="remarks"></a>解説

コンストラクターで呼び`EnableAutomation`出し、オートメーションを有効にするオブジェクトの場合、この関数は、インターフェイスを介して通信`IDispatch`するクライアントによって使用される Foundation クラス`IDispatch`実装へのポインターを返します。 この関数を呼び出すと、ポインターへの参照が自動的に追加されるため、呼び出しを行う必要はありません[。](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)

## <a name="ccmdtargetgettypeinfocount"></a><a name="gettypeinfocount"></a>をクリックします。

オブジェクトが提供する型情報インターフェイスの数を取得します。

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>戻り値

型情報インターフェイスの数。

### <a name="remarks"></a>解説

このメンバー関数は基本的に[IDispatch::GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)を実装します。

派生クラスは、この関数をオーバーライドして、提供される型情報インターフェイスの数 (0 または 1) を返す必要があります。 オーバーライドされていない場合は`GetTypeInfoCount`0 を返します。 オーバーライドするには[、IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib)マクロ`GetTypeLib`を`GetTypeLibCache`使用します。

## <a name="ccmdtargetgettypeinfoofguid"></a><a name="gettypeinfoofguid"></a>を取得します。

指定された GUID に対応するタイプ記述を取得します。

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>パラメーター

*lcid*<br/>
ロケール識別子 ( `LCID`)

*guid*<br/>
型の説明の[GUID。](/previous-versions/cc317743(v%3dmsdn.10))

*をクリックします。*<br/>
`ITypeInfo`インターフェイスへのポインターへのポインター。

### <a name="return-value"></a>戻り値

呼び出しの成功または失敗を示す HRESULT。 成功した場合\**、ppTypeInfo*は型情報インターフェイスを指します。

## <a name="ccmdtargetgettypelib"></a><a name="gettypelib"></a>をクリックします。

タイプ ライブラリへのポインターを取得します。

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>パラメーター

*lcid*<br/>
ロケール識別子 (LCID)。

*をクリックします。*<br/>
`ITypeLib`インターフェイスへのポインターへのポインター。

### <a name="return-value"></a>戻り値

呼び出しの成功または失敗を示す HRESULT。 正常に実行\*された場合 *、ppTypeLib*はタイプ ライブラリ インターフェイスを指します。

### <a name="remarks"></a>解説

派生クラスは、このメンバー関数をオーバーライドする必要があります`GetTypeLib`(オーバーライドされていない場合は、TYPE_E_CANTLOADLIBRARYを返します)。 IMPLEMENT_OLETYPELIB[マクロを](../../mfc/reference/type-library-access.md#implement_oletypelib)使用`GetTypeInfoCount`します`GetTypeLibCache`。

## <a name="ccmdtargetgettypelibcache"></a><a name="gettypelibcache"></a>をクリックします。

タイプ ライブラリ キャッシュを取得します。

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>戻り値

`CTypeLibCache` オブジェクトを指すポインターです。

### <a name="remarks"></a>解説

派生クラスは、このメンバー関数をオーバーライドする必要があります`GetTypeLibCache`(オーバーライドされていない場合は NULL を返します)。 IMPLEMENT_OLETYPELIB[マクロを](../../mfc/reference/type-library-access.md#implement_oletypelib)使用`GetTypeInfoCount`します`GetTypeLib`。

## <a name="ccmdtargetisinvokeallowed"></a><a name="isinvokeallowed"></a>を呼び出すことができます。

この関数は、MFC の`IDispatch::Invoke`実装によって呼び出され、特定のオートメーション メソッド ( *dispid*で識別 ) を呼び出すことができるかどうかを判断します。

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
ディスパッチ ID。

### <a name="return-value"></a>戻り値

メソッドを呼び出すことができる場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

TRUE`IsInvokeAllowed`を返`Invoke`す場合は、メソッドの呼び出しに進みます。それ以外`Invoke`の場合は失敗し、E_UNEXPECTED返します。

派生クラスは、この関数をオーバーライドして適切な値を返すことができます`IsInvokeAllowed`(オーバーライドされていない場合は TRUE を返します)。 特に[、COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed)を参照してください。

## <a name="ccmdtargetisresultexpected"></a><a name="isresultexpected"></a>期待される結果を示します。

クライアント`IsResultExpected`がオートメーション関数の呼び出しから戻り値を期待しているかどうかを確認するために使用します。

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>戻り値

オートメーション関数が値を返す必要がある場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

OLE インターフェイスは、クライアントが関数呼び出しの結果を使用しているか無視しているかに関する情報を MFC に提供し、MFC はこの情報を使用して`IsResultExpected`呼び出しの結果を判断します。 戻り値の生成時間またはリソースを消費する場合は、戻り値を計算する前にこの関数を呼び出すことによって効率を高めることができます。

この関数は、クライアントが呼び出したオートメーション関数から呼び出した場合に、他のオートメーション関数から有効な戻り値を取得するために、0 を 1 回だけ返します。

`IsResultExpected`オートメーション関数呼び出しが進行中でないときに呼び出された場合は、ゼロ以外の値を返します。

## <a name="ccmdtargetoncmdmsg"></a><a name="oncmdmsg"></a>をクリックします。

コマンド メッセージをルーティングおよびディスパッチし、コマンド ユーザー インターフェイス オブジェクトの更新を処理するために、フレームワークによって呼び出されます。

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コマンド ID が含まれています。

*nコード*<br/>
コマンド通知コードを識別します。 *nCode*の値の詳細については **、「解説**」を参照してください。

*pエクストラ*<br/>
*nCode*の値に従って使用されます。 *pExtra*の詳細については **、「解説」** を参照してください。

*をクリックします。*<br/>
NULL でない場合`OnCmdMsg`は、コマンドをディスパッチする代わりに*pHandlerInfo*構造体の*pTarget*および*pmf*メンバーを埋めます。 通常、このパラメーターは NULL にする必要があります。

### <a name="return-value"></a>戻り値

メッセージが処理される場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

これはフレームワークコマンドアーキテクチャの主要な実装ルーチンです。

実行時に、コマンド`OnCmdMsg`を他のオブジェクトにディスパッチするか、実際のメッセージ マップ 検索を行`CCmdTarget::OnCmdMsg`う root クラス を呼び出してコマンド自体を処理します。 デフォルトのコマンド・ルーティングの詳細については、[メッセージ処理とマッピングのトピックを参照してください](../../mfc/message-handling-and-mapping.md)。

まれに、このメンバー関数をオーバーライドして、フレームワークの標準コマンド ルーティングを拡張する必要があります。 コマンド ルーティング アーキテクチャの詳細については、[テクニカル ノート 21](../../mfc/tn021-command-and-message-routing.md)を参照してください。

を`OnCmdMsg`オーバーライドする場合は *、nCode*の値に応じて nCode 、コマンド通知コード、および*pExtra*に適切な値を指定する必要*があります。* 次の表に、対応する値を示します。

|*nコード*値|*p エクストラ*値|
|-------------------|--------------------|
|CN_COMMAND|[Ccmdui](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|CN_UPDATE_COMMAND_UI|CCmdUI\*|
|CN_OLECOMMAND|[Colecmdui](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

## <a name="ccmdtargetonfinalrelease"></a><a name="onfinalrelease"></a>CCmdターゲット::オンファイナルリリース

オブジェクトへの最後の OLE 参照またはオブジェクトからの OLE 参照が解放されたときに、フレームワークによって呼び出されます。

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>解説

この状況に対する特別な処理を提供するには、この関数をオーバーライドします。 既定の実装では、オブジェクトを削除します。

## <a name="ccmdtargetrestorewaitcursor"></a><a name="restorewaitcursor"></a>をクリックします。

システム カーソルが変更された後 (たとえば、メッセージ ボックスが開いて閉じた後に、長い操作の途中で) 適切な砂時計カーソルを復元します。

```
void RestoreWaitCursor();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[クラスをディスパッチします。](../../mfc/reference/coledispatchdriver-class.md)
