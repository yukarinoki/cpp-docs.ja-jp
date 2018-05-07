---
title: CCmdTarget クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b76e4a0c0533ceb0200757f86f332d77c3b39ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ccmdtarget-class"></a>CCmdTarget クラス
Microsoft Foundation Class ライブラリのメッセージ マップ アーキテクチャの基本クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CCmdTarget : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCmdTarget::CCmdTarget](#ccmdtarget)|`CCmdTarget` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|砂時計カーソル、カーソルを表示します。|  
|[CCmdTarget::DoOleVerb](#dooleverb)|実行する OLE 動詞によって指定されたアクションが発生します。|  
|[CCmdTarget::EnableAutomation](#enableautomation)|OLE オートメーションを許可、`CCmdTarget`オブジェクト。|  
|[CCmdTarget::EnableConnections](#enableconnections)|コネクション ポイントでイベントの発生を有効にします。|  
|[CCmdTarget::EnableTypeLib](#enabletypelib)|オブジェクトのタイプ ライブラリを有効にします。|  
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|以前のカーソルを返します。|  
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|オブジェクトの OLE 動詞を列挙します。|  
|[CCmdTarget::FromIDispatch](#fromidispatch)|ポインターを返します、`CCmdTarget`オブジェクトに関連付けられている、`IDispatch`ポインター。|  
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|プライマリ ディスパッチ インターフェイス ID を取得します|  
|[CCmdTarget::GetIDispatch](#getidispatch)|ポインターを返します、`IDispatch`オブジェクトに関連付けられている、`CCmdTarget`オブジェクト。|  
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|オブジェクトを提供する型情報インターフェイスの数を取得します。|  
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|指定した GUID に対応する型の説明を取得します。|  
|[CCmdTarget::GetTypeLib](#gettypelib)|タイプ ライブラリへのポインターを取得します。|  
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|タイプ ライブラリ キャッシュを取得します。|  
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|オートメーション メソッドの呼び出しを有効にします。|  
|[CCmdTarget::IsResultExpected](#isresultexpected)|オートメーション関数の場合は 0 以外を返しますでは、値を返す必要があります。|  
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|ルーティングし、コマンドのメッセージをディスパッチします。|  
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|OLE の最後の参照のリリース後にクリーンアップされます。|  
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|砂時計カーソルを復元します。|  
  
## <a name="remarks"></a>コメント  
 メッセージ マップは、それらを処理するために、メンバー関数にコマンドまたはメッセージをルーティングします。 (コマンドとは、メニュー項目、コマンド ボタンまたはアクセラレータ キーからのメッセージのことです)。  
  
 派生したキー フレームワーク クラス`CCmdTarget`含める[CView](../../mfc/reference/cview-class.md)、 [CWinApp](../../mfc/reference/cwinapp-class.md)、 [CDocument](../../mfc/reference/cdocument-class.md)、 [CWnd](../../mfc/reference/cwnd-class.md)、および[CFrameWnd](../../mfc/reference/cframewnd-class.md)です。 メッセージを処理する新しいクラスの場合は、次のいずれかからクラスを派生`CCmdTarget`-クラスを派生します。 クラスを派生させることはほとんどありませんは`CCmdTarget`直接です。  
  
 コマンド ターゲットの概要については、`OnCmdMsg`ルーティングを参照してください[コマンド ターゲット](../../mfc/command-targets.md)、[コマンド ルーティング](../../mfc/command-routing.md)、および[メッセージの割り当て](../../mfc/mapping-messages.md)です。  
  
 `CCmdTarget` 砂時計カーソルの表示を処理するメンバー関数が含まれます。 コマンドの実行にかなりの時間を要するが予想される場合は、砂時計カーソルを表示します。  
  
 ディスパッチ マップ、メッセージ マップに似た、OLE オートメーションを公開するため`IDispatch`機能します。 このインターフェイスを公開すると、その他のアプリケーション (Visual Basic の場合) などは、アプリケーションに呼び出すことができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="beginwaitcursor"></a>  CCmdTarget::BeginWaitCursor  
 コマンドの実行にかなりの時間を要するが予想される場合は砂時計として、カーソルを表示するには、この関数を呼び出します。  
  
```  
void BeginWaitCursor();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークが場合など、ビジー状態であることをユーザーに表示するには、この関数を呼び出す、 **CDocument**オブジェクトが読み込まれるか、またはそれ自体をファイルに保存します。  
  
 アクション`BeginWaitCursor`などはありません常に 1 つのメッセージ ハンドラーの外部で効果的なその他のアクションとして`OnSetCursor`カーソルに変更を処理する可能性があります。  
  
 呼び出す`EndWaitCursor`を以前のカーソルを復元します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="ccmdtarget"></a>  CCmdTarget::CCmdTarget  
 `CCmdTarget` オブジェクトを構築します。  
  
```  
CCmdTarget();
```  
  
##  <a name="dooleverb"></a>  CCmdTarget::DoOleVerb  
 実行する OLE 動詞によって指定されたアクションが発生します。  
  
```  
BOOL DoOleVerb(
    LONG iVerb,  
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 動詞の数値識別子。  
  
 `lpMsg`  
 ポインター、 [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) (ダブルクリック) などの動詞を起動したイベントを記述する構造体。  
  
 `hWndParent`  
 オブジェクトを保持しているドキュメント ウィンドウのハンドル。  
  
 `lpRect`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体を含む、座標 (ピクセル単位)、オブジェクトを定義する外接する四角形で*hwndParent*です。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、成功すると、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、の実装では基本的に[IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)です。 によって実行可能なアクションを列挙する[CCmdTarget::EnumOleVerbs](#enumoleverbs)です。  
  
##  <a name="enableautomation"></a>  CCmdTarget::EnableAutomation  
 オブジェクトの OLE オートメーションを有効にするには、この関数を呼び出します。  
  
```  
void EnableAutomation();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、通常は、オブジェクトのコンス トラクターから呼び出されるし、クラスのディスパッチ マップが宣言されている場合にのみ呼び出す必要があります。 Automation の詳細については、記事を参照してください。[オートメーション クライアント](../../mfc/automation-clients.md)と[オートメーション サーバー](../../mfc/automation-servers.md)です。  
  
##  <a name="enableconnections"></a>  CCmdTarget::EnableConnections  
 コネクション ポイントでイベントの発生を有効にします。  
  
```  
void EnableConnections();
```  
  
### <a name="remarks"></a>コメント  
 接続ポイントを有効にするには、派生クラスのコンス トラクターでこのメンバー関数を呼び出します。  
  
##  <a name="enabletypelib"></a>  CCmdTarget::EnableTypeLib  
 オブジェクトのタイプ ライブラリを有効にします。  
  
```  
void EnableTypeLib();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数のコンス トラクターを呼び出して、 `CCmdTarget`-派生オブジェクトの種類の情報を提供する場合。 詳細については、サポート技術情報の記事 Q185720 を参照してください"HOWTO: MFC オートメーション サーバーから型情報を提供します。"。 サポート技術情報については、「 [ http://support.microsoft.com](http://support.microsoft.com/)です。  
  
##  <a name="endwaitcursor"></a>  CCmdTarget::EndWaitCursor  
 呼び出した後に、この関数を呼び出して、`BeginWaitCursor`砂時計カーソルから以前のカーソルを返すメンバー関数。  
  
```  
void EndWaitCursor();
```  
  
### <a name="remarks"></a>コメント  
 砂時計カーソルを呼び出した後、フレームワークはまた、このメンバー関数を呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="enumoleverbs"></a>  CCmdTarget::EnumOleVerbs  
 オブジェクトの OLE 動詞を列挙します。  
  
```  
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppenumOleVerb`  
 ポインターへのポインター、[返します](http://msdn.microsoft.com/library/windows/desktop/ms695084)インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトは、少なくとも 1 つの OLE 動詞をサポートしている場合は TRUE (後者\*`ppenumOleVerb`を指す、**返します**列挙子インターフェイス)、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、の実装では基本的に[IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781)です。  
  
##  <a name="fromidispatch"></a>  CCmdTarget::FromIDispatch  
 マップするには、この関数を呼び出して、`IDispatch`ポインターで、クラスのメンバー関数はオートメーションから受信した、`CCmdTarget`のインターフェイスを実装するオブジェクト、`IDispatch`オブジェクト。  
  
```  
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDispatch`  
 `IDispatch` オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CCmdTarget`オブジェクトに関連付けられている`lpDispatch`です。 この関数を返します**NULL**場合、`IDispatch`オブジェクトは、Microsoft Foundation Class として認識されません`IDispatch`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数の結果は、メンバー関数への呼び出しの逆`GetIDispatch`です。  
  
##  <a name="getdispatchiid"></a>  CCmdTarget::GetDispatchIID  
 プライマリ ディスパッチ インターフェイス ID を取得します  
  
```  
virtual BOOL GetDispatchIID(IID* pIID);
```  
  
### <a name="parameters"></a>パラメーター  
 *pIID*  
 インターフェイス ID へのポインター (、 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931))。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、成功すると、それ以外の場合は FALSE。 成功した場合、 \* *pIID*プライマリ ディスパッチ インターフェイス ID に設定されています。  
  
### <a name="remarks"></a>コメント  
 派生クラスは、このメンバー関数をオーバーライドする必要があります (オーバーライドされなかった場合、 `GetDispatchIID` FALSE を返します)。 参照してください[COleControl](../../mfc/reference/colecontrol-class.md)です。  
  
 詳細については、サポート技術情報の記事 Q185720 を参照してください"HOWTO: MFC オートメーション サーバーから型情報を提供します。"。 サポート技術情報については、「 [ http://support.microsoft.com](http://support.microsoft.com/)です。  
  
##  <a name="getidispatch"></a>  CCmdTarget::GetIDispatch  
 取得するには、このメンバー関数を呼び出す、`IDispatch`ポインター オートメーション メソッドからはどちらかが返されます、`IDispatch`ポインターまたは受け取り、`IDispatch`ポインターの参照。  
  
```  
LPDISPATCH GetIDispatch(BOOL bAddRef);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAddRef*  
 オブジェクトの参照カウントをインクリメントするかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `IDispatch`オブジェクトに関連付けられたポインター。  
  
### <a name="remarks"></a>コメント  
 オブジェクトを呼び出す`EnableAutomation`オートメーションを有効にすること、コンス トラクターでこの関数のポインターを返しますの基礎クラスの実装に`IDispatch`を介して通信するクライアントによって使用される、`IDispatch`インターフェイスです。 呼び出しを行う必要はありませんので、ポインターへの参照を追加する自動的にこの関数を呼び出す[:addref](http://msdn.microsoft.com/library/windows/desktop/ms691379)です。  
  
##  <a name="gettypeinfocount"></a>  CCmdTarget::GetTypeInfoCount  
 オブジェクトを提供する型情報インターフェイスの数を取得します。  
  
```  
virtual UINT GetTypeInfoCount();
```  
  
### <a name="return-value"></a>戻り値  
 型情報インターフェイスの数。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は基本的には、実装[IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12)です。  
  
 派生クラスでは、(0 または 1) を提供する型情報インターフェイスの数を返すには、この関数をオーバーライドする必要があります。 オーバーライドされなかった場合、**しなかった**0 を返します。 オーバーライドする、 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib)も実装されているマクロ`GetTypeLib`と`GetTypeLibCache`です。  
  
##  <a name="gettypeinfoofguid"></a>  CCmdTarget::GetTypeInfoOfGuid  
 指定した GUID に対応する型の説明を取得します。  
  
```  
HRESULT GetTypeInfoOfGuid(
    LCID lcid,  
    const GUID& guid,  
    LPTYPEINFO* ppTypeInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `lcid`  
 ロケール識別子 ( `LCID`)。  
  
 `guid`  
 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931)の種類の説明。  
  
 `ppTypeInfo`  
 ポインターへのポインター、`ITypeInfo`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 呼び出しの成否を示す HRESULT。 成功した場合、*`ppTypeInfo`型情報インターフェイスを指します。  
  
##  <a name="gettypelib"></a>  CCmdTarget::GetTypeLib  
 タイプ ライブラリへのポインターを取得します。  
  
```  
virtual HRESULT GetTypeLib(
    LCID lcid,  
    LPTYPELIB* ppTypeLib);
```  
  
### <a name="parameters"></a>パラメーター  
 `lcid`  
 ロケール識別子 ( `LCID`)。  
  
 `ppTypeLib`  
 ポインターへのポインター、`ITypeLib`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 呼び出しの成否を示す HRESULT。 成功した場合、*`ppTypeLib`タイプ ライブラリのインターフェイスを指します。  
  
### <a name="remarks"></a>コメント  
 派生クラスは、このメンバー関数をオーバーライドする必要があります (オーバーライドされなかった場合、 `GetTypeLib` TYPE_E_CANTLOADLIBRARY を返します)。 使用して、 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib)も実装されているマクロ`GetTypeInfoCount`と`GetTypeLibCache`です。  
  
##  <a name="gettypelibcache"></a>  CCmdTarget::GetTypeLibCache  
 タイプ ライブラリ キャッシュを取得します。  
  
```  
virtual CTypeLibCache* GetTypeLibCache();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 **CTypeLibCache**オブジェクト。  
  
### <a name="remarks"></a>コメント  
 派生クラスは、このメンバー関数をオーバーライドする必要があります (オーバーライドされなかった場合、**によりオーバーライド**は NULL を返します)。 使用して、 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib)も実装されているマクロ`GetTypeInfoCount`と`GetTypeLib`です。  
  
##  <a name="isinvokeallowed"></a>  CCmdTarget::IsInvokeAllowed  
 この関数は mfc の**idispatch::invoke**場合、指定されたオートメーション メソッド (で識別される`dispid`) 呼び出すことができます。  
  
```  
virtual BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 ディスパッチ id。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、メソッドが呼び出される、それ以外の場合は FALSE を指定できます。  
  
### <a name="remarks"></a>コメント  
 場合`IsInvokeAllowed`に TRUE を返します**Invoke**メソッドを呼び出します。 に進みますそれ以外の場合、`Invoke`が失敗すると、E_UNEXPECTED を返します。  
  
 派生クラスは、適切な値を返すには、この関数をオーバーライドできます (オーバーライドされなかった場合、 `IsInvokeAllowed` TRUE を返します)。 具体的にを参照してください[COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed)です。  
  
##  <a name="isresultexpected"></a>  CCmdTarget::IsResultExpected  
 使用して`IsResultExpected`クライアントがそのオートメーション関数の呼び出しからの戻り値を求めているかどうかを確認するためにします。  
  
```  
BOOL IsResultExpected();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、オートメーション関数が値を返す必要があります。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 OLE インターフェイスが MFC をクライアントを使用してまたは関数の呼び出しの結果を無視するかどうかについての情報を提供し、MFC 順番に使用してこの情報への呼び出しの結果を決定`IsResultExpected`です。 戻り値の実稼働が時間のまたはリソースの消費が大きい場合は、戻り値を計算する前にこの関数を呼び出すことによって効率を高めることができます。  
  
 この関数は、クライアントによって呼び出されたから呼び出す場合に、オートメーション関数を他のオートメーション関数から有効な戻り値を取得することの 1 回だけ、0 を返します。  
  
 `IsResultExpected` オートメーション関数呼び出しが実行されていないときに呼び出された場合は、0 以外の値を返します。  
  
##  <a name="oncmdmsg"></a>  CCmdTarget::OnCmdMsg  
 コマンド メッセージをディスパッチするため、コマンドのユーザー インターフェイス オブジェクトの更新を処理して、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コマンド ID が含まれています  
  
 `nCode`  
 コマンド通知コードを識別します。 参照してください**解説**の値の詳細については詳細`nCode`です。  
  
 `pExtra`  
 値に従って使用`nCode`です。 参照してください**解説**の詳細については`pExtra`します。  
  
 `pHandlerInfo`  
 ない場合**NULL**、`OnCmdMsg`を入力、 **pTarget**と**pmf**のメンバー、`pHandlerInfo`ディスパッチ コマンドではなく構造体。 通常、このパラメーターを指定する必要があります**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これは、フレームワーク コマンド アーキテクチャの主な実装ルーチンです。  
  
 実行時に、`OnCmdMsg`ルート クラスを呼び出すことによって、コマンド自体を取り扱う他のオブジェクトへのコマンドをディスパッチ`CCmdTarget::OnCmdMsg`、どのは実際のメッセージ マップ検索します。 既定のコマンド ルーティングの詳細については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)です。  
  
 まれに、フレームワークを拡張するには、このメンバー関数を無効にすることがあります標準コマンド ルーティングします。 参照してください[テクニカル ノート 21](../../mfc/tn021-command-and-message-routing.md)コマンド ルーティングのアーキテクチャの詳細についてはします。  
  
 オーバーライドする場合は`OnCmdMsg`、適切な値を指定する必要があります`nCode`、コマンド通知コードおよび`pExtra`の値に依存する`nCode`です。 次の表は、対応する値を示します。  
  
|`nCode` の値|`pExtra` の値|  
|-------------------|--------------------|  
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)*|  
|CN_EVENT|AFX_EVENT *|  
|CN_UPDATE_COMMAND_UI|CCmdUI *|  
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)*|  
|CN_OLE_UNREGISTER|NULL|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]  
  
##  <a name="onfinalrelease"></a>  CCmdTarget::OnFinalRelease  
 またはオブジェクトからの最後の OLE 参照がリリースされたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnFinalRelease();
```  
  
### <a name="remarks"></a>コメント  
 このような場合の特別な処理を提供するには、この関数をオーバーライドします。 既定の実装では、オブジェクトを削除します。  
  
##  <a name="restorewaitcursor"></a>  CCmdTarget::RestoreWaitCursor  
 システム カーソル後に変更された (たとえば、メッセージ ボックスが開き、し、時間のかかる操作の途中で終了) した後、適切な砂時計カーソルを復元するには、この関数を呼び出します。  
  
```  
void RestoreWaitCursor();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル ACDUAL](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [COleDispatchDriver クラス](../../mfc/reference/coledispatchdriver-class.md)
