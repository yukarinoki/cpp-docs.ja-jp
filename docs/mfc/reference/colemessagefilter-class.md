---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
dev_langs:
- C++
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85161e7f3dd752c6df27afedf6276f8823e7ec6e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371365"
---
# <a name="colemessagefilter-class"></a>関数クラス
OLE アプリケーション間の相互の要求を同時に管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|`COleMessageFilter` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleMessageFilter::BeginBusyState](#beginbusystate)|ビジー状態でアプリケーションを配置します。|  
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|有効にし、呼び出し先のアプリケーションがビジー状態のときに表示されるダイアログ ボックスを無効にします。|  
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|有効にし、呼び出し先のアプリケーションが応答していないときに表示されるダイアログ ボックスを無効にします。|  
|[COleMessageFilter::EndBusyState](#endbusystate)|アプリケーションのビジー状態を終了します。|  
|[COleMessageFilter::OnMessagePending](#onmessagepending)|OLE 呼び出しが進行中は、メッセージを処理するためにフレームワークによって呼び出されます。|  
|[COleMessageFilter::Register](#register)|OLE システム Dll をメッセージ フィルターを登録します。|  
|[COleMessageFilter::Revoke](#revoke)|OLE システム Dll とメッセージ フィルターの登録を取り消します。|  
|[COleMessageFilter::SetBusyReply](#setbusyreply)|OLE 呼び出しにビジー状態のアプリケーションの応答を決定します。|  
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|アプリケーションが OLE 呼び出しに対する応答を待機する時間を決定します。|  
|[COleMessageFilter::SetRetryReply](#setretryreply)|ビジー状態のアプリケーションへの呼び出し元のアプリケーションの応答を決定します。|  
  
## <a name="remarks"></a>コメント  
 `COleMessageFilter`クラスはビジュアル編集サーバーとコンテナー アプリケーションだけでなく OLE オートメーション アプリケーションに便利です。 呼び出されるサーバー アプリケーションでは、アプリケーションにするのには「ビジー」その他のコンテナー アプリケーションからの着信呼び出しか、取り消されたか、後で再試行できるようにこのクラスを使用できます。 このクラスは、呼び出し先のアプリケーションがビジー状態のときに、呼び出し元アプリケーションによって実行される操作を決定するも使用できます。  
  
 サーバー アプリケーションを呼び出すための一般的な使用方法は、 [BeginBusyState](#beginbusystate)と[EndBusyState](#endbusystate)した方がドキュメントまたはその他の OLE アクセス可能なオブジェクトを破棄するは危険です。 これらの呼び出しが行われた[CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)ユーザー インターフェイスの更新中です。  
  
 既定では、`COleMessageFilter`アプリケーションの初期化時にオブジェクトが割り当てられます。 取得できる[AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)です。  
  
 これは高度なクラスです。頻度の低い、直接使用する必要があります。  
  
 詳細については、記事を参照してください。[サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="beginbusystate"></a>  COleMessageFilter::BeginBusyState  
 この関数では、ビジー状態を開始します。  
  
```  
virtual void BeginBusyState();
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて動作[EndBusyState](#endbusystate)をアプリケーションのビジー状態を制御します。 関数は、 [SetBusyReply](#setbusyreply)呼び出し元アプリケーションのビジー状態であるときに、アプリケーションの応答を決定します。  
  
 `BeginBusyState`と`EndBusyState`呼び出しインクリメントし、それぞれ、アプリケーションがビジー状態であるかどうかを決定するカウンターをデクリメントします。 たとえば、2 回の呼び出しに`BeginBusyState`とに 1 回の呼び出し`EndBusyState`ビジー状態の結果をまだです。 呼び出す必要があるビジー状態をキャンセルする`EndBusyState`同じ回数`BeginBusyState`が呼び出されています。  
  
 既定では、フレームワークの状態にビジー状態で実行される、アイドル状態の処理中に[CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)です。 アプリケーションの処理中に**ON_COMMANDUPDATEUI**アイドル処理が完了したら、通知、着信呼び出しが後で、処理されます。  
  
##  <a name="colemessagefilter"></a>  COleMessageFilter::COleMessageFilter  
 
          `COleMessageFilter` オブジェクトを作成します。  
  
```  
COleMessageFilter();
```  
  
##  <a name="enablebusydialog"></a>  COleMessageFilter::EnableBusyDialog  
 有効にし、保留中のメッセージの遅延時間の有効期限が切れるときに表示されるダイアログ ボックスが無効になります (を参照してください[ビジー](#setretryreply)) OLE 呼び出し中にします。  
  
```  
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnableBusy*  
 「ビジー」のダイアログ ボックスを有効または無効になっているかどうかを指定します。  
  
##  <a name="enablenotrespondingdialog"></a>  COleMessageFilter::EnableNotRespondingDialog  
 有効にし、キーボードまたはマウスのメッセージが保留されている場合に表示される「応答していない」の ダイアログ ボックスを無効にする OLE 中の呼び出しと呼び出しがタイムアウトしました。  
  
```  
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnableNotResponding*  
 「応答していない」のダイアログ ボックスを有効または無効になっているかどうかを指定します。  
  
##  <a name="endbusystate"></a>  COleMessageFilter::EndBusyState  
 この関数では、ビジー状態を終了します。  
  
```  
virtual void EndBusyState();
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて動作[BeginBusyState](#beginbusystate)をアプリケーションのビジー状態を制御します。 関数は、 [SetBusyReply](#setbusyreply)呼び出し元アプリケーションのビジー状態であるときに、アプリケーションの応答を決定します。  
  
 `BeginBusyState`と`EndBusyState`呼び出しインクリメントし、それぞれ、アプリケーションがビジー状態であるかどうかを決定するカウンターをデクリメントします。 たとえば、2 回の呼び出しに`BeginBusyState`とに 1 回の呼び出し`EndBusyState`ビジー状態の結果をまだです。 呼び出す必要があるビジー状態をキャンセルする`EndBusyState`同じ回数`BeginBusyState`が呼び出されています。  
  
 既定では、フレームワークの状態にビジー状態で実行される、アイドル状態の処理中に[CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)です。 アプリケーションの処理中に`ON_UPDATE_COMMAND_UI`アイドル処理が完了したら、通知の受信呼び出しが処理されます。  
  
##  <a name="onmessagepending"></a>  COleMessageFilter::OnMessagePending  
 OLE 呼び出しが進行中は、メッセージを処理するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMessagePending(const MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 保留中のメッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のアプリケーションは、呼び出しの完了を待っている、ときに、フレームワークによって呼び出されます`OnMessagePending`保留中のメッセージへのポインター。 既定では、フレームワークのディスパッチ`WM_PAINT`メッセージ、長い時間がかかっている呼び出し中にウィンドウの更新を実行できるようにします。  
  
 呼び出しを使用して、メッセージ フィルターを登録する必要があります[登録](#register)前に、アクティブになることができます。  
  
##  <a name="register"></a>  COleMessageFilter::Register  
 OLE システム Dll をメッセージ フィルターを登録します。  
  
```  
BOOL Register();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 システム Dll に登録されていない限りは、メッセージ フィルターを指定しても効果はありません。 通常、アプリケーションの初期化コードは、アプリケーションのメッセージ フィルターを登録します。 呼び出しによって、プログラムが終了する前に、アプリケーションで登録されている他のメッセージ フィルターを取り消す必要があります[取り消す](#revoke)です。  
  
 フレームワークの既定のメッセージ フィルターは自動的に初期化中に登録され、終了時に失効します。  
  
##  <a name="revoke"></a>  COleMessageFilter::Revoke  
 呼び出しによって実行される前の登録では失効[登録](#register)です。  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>コメント  
 メッセージ フィルターは、プログラムが終了する前に取り消す必要があります。  
  
 作成され、フレームワークによって自動的に登録されている、既定のメッセージ フィルターが自動的に失効します。  
  
##  <a name="setbusyreply"></a>  COleMessageFilter::SetBusyReply  
 この関数は、アプリケーションの"ビジー状態の応答です。"を設定します。  
  
```  
void SetBusyReply(SERVERCALL nBusyReply);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBusyReply*  
 値、 `SERVERCALL` COMPOBJ で定義されている列挙します。H. 次の値のいずれかを取ります。  
  
- **SERVERCALL_ISHANDLED**アプリケーションは呼び出しを受け取ることができますが、特定の呼び出しの処理に失敗する可能性があります。  
  
- **SERVERCALL_REJECTED**アプリケーションおそらくできなくなりますの呼び出しを処理できません。  
  
- **SERVERCALL_RETRYLATER**アプリケーションが一時的に、状態では、呼び出しを処理できません。  
  
### <a name="remarks"></a>コメント  
 [BeginBusyState](#beginbusystate)と[EndBusyState](#endbusystate)関数は、アプリケーションのビジー状態を制御します。  
  
 ときに、アプリケーションが行われたへの呼び出しでビジー状態`BeginBusyState`からに応答する通話 OLE システム Dll の最後の設定によって決定される値と`SetBusyReply`です。 呼び出し元のアプリケーションでは、このビジー状態の応答を使って、実行するアクションを決定します。  
  
 ビジー状態の応答は、既定では、 **SERVERCALL_RETRYLATER**です。 この応答は、できるだけ早く呼び出しを再試行する呼び出し側アプリケーションです。  
  
##  <a name="setmessagependingdelay"></a>  COleMessageFilter::SetMessagePendingDelay  
 これ以上の操作を実行する前に呼び出されたアプリケーションからの応答の呼び出し元のアプリケーションの待機を決定します。  
  
```  
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```  
  
### <a name="parameters"></a>パラメーター  
 `nTimeout`  
 保留中のメッセージの遅延時間 (ミリ秒) の数です。  
  
### <a name="remarks"></a>コメント  
 この関数と連携して動作[ビジー](#setretryreply)です。  
  
##  <a name="setretryreply"></a>  COleMessageFilter::SetRetryReply  
 呼び出し先のアプリケーションがビジー状態の応答を受け取ると、呼び出し元のアプリケーションのアクションを決定します。  
  
```  
void SetRetryReply(DWORD nRetryReply = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nRetryReply`  
 再試行の間隔 (ミリ秒) の数です。  
  
### <a name="remarks"></a>コメント  
 呼び出し先のアプリケーションでは、ビジー状態であることを示します、ときに、呼び出し元アプリケーションは、サーバーがビジー状態、すぐを再試行するか、指定した時間後に再試行するされなくなるまで待つことができます。 呼び出しをキャンセルすることもできます。  
  
 呼び出し元の応答は、関数によって制御されます`SetRetryReply`と[SetMessagePendingDelay](#setmessagependingdelay)です。 `SetRetryReply` 呼び出し元のアプリケーションが待機、特定の呼び出しの再試行の間隔を決定します。 `SetMessagePendingDelay` さらに操作を実行する前にサーバーからの応答を呼び出し元のアプリケーション待機時間を決定します。  
  
 通常の既定値は許容され、変更する必要はありません。 フレームワークは、呼び出しを再試行すべて`nRetryReply`呼び出しがまたは保留中のメッセージの遅延時間が経過するまで、ミリ秒です。 値 0 を`nRetryReply`を指定、呼び出しのキャンセルの即時再試行、および 1 を指定します。  
  
 保留中のメッセージの遅延時間が有効期限が切れて、OLE「ビジー状態 ダイアログ ボックス」(を参照してください[COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) が表示され、ユーザーを取り消すか、呼び出しを再実行を選択できます。 呼び出す[EnableBusyDialog](#enablebusydialog)を有効にするにまたは、このダイアログ ボックスを無効にします。  
  
 キーボードまたはマウスのメッセージが保留中の場合、呼び出しと呼び出し中にタイムアウトしました (保留中のメッセージの遅延時間を超えると)、「応答していない」のダイアログ ボックスが表示されます。 呼び出す[EnableNotRespondingDialog](#enablenotrespondingdialog)を有効にするにまたは、このダイアログ ボックスを無効にします。 通常事態は、この状態は、問題の発生し、ユーザーは待たことを示します。  
  
 ダイアログ ボックスが無効な場合、現在「再試行」の応答は常に使用ビジー状態のアプリケーションへの呼び出し。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
