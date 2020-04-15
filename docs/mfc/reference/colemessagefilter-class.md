---
title: COleMessageFilter クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: f6db5f012aedf08edd87980e304e181295bfb953
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374922"
---
# <a name="colemessagefilter-class"></a>COleMessageFilter クラス

OLE アプリケーション間の相互に要求されるコンカレンシーを管理します。

## <a name="syntax"></a>構文

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[メッセージ フィルター::メッセージ フィルター](#colemessagefilter)|`COleMessageFilter` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[メッセージフィルター::ビジー状態を開始します。](#beginbusystate)|アプリケーションをビジー状態にします。|
|[メッセージ フィルター::ビジーダイアログを有効にします。](#enablebusydialog)|呼び出されたアプリケーションがビジー状態のときに表示されるダイアログ ボックスを有効または無効にします。|
|[メッセージ フィルター::応答なしのダイアログを有効にします。](#enablenotrespondingdialog)|呼び出されたアプリケーションが応答しない場合に表示されるダイアログ ボックスを有効または無効にします。|
|[メッセージフィルター::エンドビジー状態](#endbusystate)|アプリケーションのビジー状態を終了します。|
|[メッセージフィルター::メッセージ処理中](#onmessagepending)|OLE 呼び出しの実行中にメッセージを処理するために、フレームワークによって呼び出されます。|
|[メッセージ フィルター::登録](#register)|OLE システム DLL にメッセージ フィルタを登録します。|
|[メッセージフィルター::取り消し](#revoke)|OLE システム DLL に対するメッセージ フィルタの登録を取り消します。|
|[メッセージフィルター::ビジー応答を設定します。](#setbusyreply)|OLE 呼び出しに対するビジー状態のアプリケーションの応答を決定します。|
|[メッセージフィルター::メッセージを保留するディミディ](#setmessagependingdelay)|アプリケーションが OLE 呼び出しに対する応答を待機する時間を決定します。|
|[メッセージフィルター::再試行応答を設定します。](#setretryreply)|ビジー状態のアプリケーションに対する呼び出し元アプリケーションの応答を決定します。|

## <a name="remarks"></a>解説

この`COleMessageFilter`クラスは、OLE オートメーション アプリケーションだけでなく、ビジュアル編集サーバー アプリケーションやコンテナ アプリケーションにも役立ちます。 呼び出されるサーバー アプリケーションの場合、このクラスを使用してアプリケーションを "ビジー" にして、他のコンテナー アプリケーションからの着信呼び出しをキャンセルするか、後で再試行することができます。 このクラスは、呼び出し側アプリケーションがビジー状態のときに呼び出し側アプリケーションが実行するアクションを決定するためにも使用できます。

一般的な使用方法は、ドキュメントまたは他の OLE アクセス可能なオブジェクトが破棄される危険がある場合に、サーバー アプリケーションが[BeginBusyState](#beginbusystate)と[EndBusyState](#endbusystate)を呼び出す方法です。 これらの呼び出しは、ユーザー インターフェイスの更新中に[CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)で行われます。

既定では、アプリケーション`COleMessageFilter`の初期化時にオブジェクトが割り当てられます。 を[使用して](application-control.md#afxolegetmessagefilter)取得できます。

これは高度なクラスです。直接作業する必要はありません。

詳細については、「サーバー :[サーバーの実装](../../mfc/servers-implementing-a-server.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="colemessagefilterbeginbusystate"></a><a name="beginbusystate"></a>メッセージフィルター::ビジー状態を開始します。

ビジー状態を開始するには、この関数を呼び出します。

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>解説

これは[、アプリケーションのビジー](#endbusystate)状態を制御するために EndBusyState と連携して動作します。 関数[SetBusyReply](#setbusyreply)は、アプリケーションがビジー状態のときに呼び出し元のアプリケーションに対する応答を決定します。

呼`BeginBusyState`び`EndBusyState`出しは、アプリケーションがビジー状態かどうかを判断するカウンターをそれぞれインクリメントとデクリメントを呼び出します。 たとえば、2 回の`BeginBusyState`呼び出し`EndBusyState`と 1 回の呼び出しがビジー状態に引き続き発生します。 ビジー状態をキャンセルするには、同じ回数`EndBusyState``BeginBusyState`の呼び出しが必要です。

既定では、フレームワークは[、CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)によって実行されるアイドル処理中にビジー状態に入ります。 アプリケーションがON_COMMANDUPDATEUI通知を処理している間、アイドル処理が完了した後で着信呼び出しが処理されます。

## <a name="colemessagefiltercolemessagefilter"></a><a name="colemessagefilter"></a>メッセージ フィルター::メッセージ フィルター

`COleMessageFilter` オブジェクトを作成します。

```
COleMessageFilter();
```

## <a name="colemessagefilterenablebusydialog"></a><a name="enablebusydialog"></a>メッセージ フィルター::ビジーダイアログを有効にします。

OLE 呼び出し中にメッセージ保留の遅延が切れたときに表示されるビジー ダイアログ ボックスを有効または無効にします ( [SetRetryReply](#setretryreply)を参照 ) 。

```
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>パラメーター

*ビクビを有効にする*<br/>
[ビジー状態] ダイアログ ボックスを有効にするか無効にするかを指定します。

## <a name="colemessagefilterenablenotrespondingdialog"></a><a name="enablenotrespondingdialog"></a>メッセージ フィルター::応答なしのダイアログを有効にします。

OLE 呼び出し中にキーボードまたはマウス のメッセージが保留状態で、呼び出しがタイムアウトした場合に表示される [応答なし] ダイアログ ボックスを有効または無効にします。

```
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>パラメーター

*応答していません。*<br/>
[応答なし] ダイアログ ボックスを有効にするか無効にするかを指定します。

## <a name="colemessagefilterendbusystate"></a><a name="endbusystate"></a>メッセージフィルター::エンドビジー状態

ビジー状態を終了するには、この関数を呼び出します。

```
virtual void EndBusyState();
```

### <a name="remarks"></a>解説

これは、アプリケーションのビジー状態を制御するために[BeginBusyState](#beginbusystate)と連携して動作します。 関数[SetBusyReply](#setbusyreply)は、アプリケーションがビジー状態のときに呼び出し元のアプリケーションに対する応答を決定します。

呼`BeginBusyState`び`EndBusyState`出しは、アプリケーションがビジー状態かどうかを判断するカウンターをそれぞれインクリメントとデクリメントを呼び出します。 たとえば、2 回の`BeginBusyState`呼び出し`EndBusyState`と 1 回の呼び出しがビジー状態に引き続き発生します。 ビジー状態をキャンセルするには、同じ回数`EndBusyState``BeginBusyState`の呼び出しが必要です。

既定では、フレームワークは[、CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)によって実行されるアイドル処理中にビジー状態に入ります。 アプリケーションがON_UPDATE_COMMAND_UI通知を処理している間、着信呼び出しはアイドル処理が完了した後に処理されます。

## <a name="colemessagefilteronmessagepending"></a><a name="onmessagepending"></a>メッセージフィルター::メッセージ処理中

OLE 呼び出しの実行中にメッセージを処理するために、フレームワークによって呼び出されます。

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*Pmsg*<br/>
保留中のメッセージへのポインター。

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>解説

呼び出し元のアプリケーションが呼び出しの完了を待機`OnMessagePending`しているとき、フレームワークは保留中のメッセージへのポインターを使用して呼び出します。 既定では、フレームワークはWM_PAINTメッセージをディスパッチするため、長時間の通話中にウィンドウの更新が行われる可能性があります。

アクティブになる前に[、Register](#register)への呼び出しを使用してメッセージ フィルターを登録する必要があります。

## <a name="colemessagefilterregister"></a><a name="register"></a>メッセージ フィルター::登録

OLE システム DLL にメッセージ フィルタを登録します。

```
BOOL Register();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>解説

メッセージ フィルタは、システム DLL に登録されていない限り、効果はありません。 通常、アプリケーションの初期化コードは、アプリケーションのメッセージ フィルターを登録します。 アプリケーションによって登録されたその他のメッセージ フィルタは、Revoke の呼び出しによってプログラムが終了する前に[取り消](#revoke)す必要があります。

フレームワークの既定のメッセージ フィルターは、初期化中に自動的に登録され、終了時に取り消されます。

## <a name="colemessagefilterrevoke"></a><a name="revoke"></a>メッセージフィルター::取り消し

Register の呼び出しによって実行された以前の[登録](#register)を取り消します。

```
void Revoke();
```

### <a name="remarks"></a>解説

プログラムが終了する前に、メッセージ フィルターを取り消す必要があります。

フレームワークによって自動的に作成および登録される既定のメッセージ フィルターも自動的に取り消されます。

## <a name="colemessagefiltersetbusyreply"></a><a name="setbusyreply"></a>メッセージフィルター::ビジー応答を設定します。

この関数は、アプリケーションの「ビジー応答」を設定します。

```
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>パラメーター

*応答の多い応答*<br/>
COMPOBJ で`SERVERCALL`定義されている列挙型からの値。H。 次のいずれかの値を指定できます。

- SERVERCALL_ISHANDLED アプリケーションは呼び出しを受け入れることができますが、特定の呼び出しの処理に失敗する可能性があります。

- SERVERCALL_REJECTED アプリケーションはおそらく呼び出しを処理できません。

- SERVERCALL_RETRYLATER アプリケーションは一時的に呼び出しを処理できない状態にあります。

### <a name="remarks"></a>解説

[BeginBusyState](#beginbusystate)関数と[EndBusyState](#endbusystate)関数は、アプリケーションのビジー状態を制御します。

アプリケーションが呼び出し`BeginBusyState`でビジー状態になると、最後の設定で指定された値を使用して、OLE システム DLL からの呼び`SetBusyReply`出しに応答します。 呼び出し元アプリケーションは、このビジー応答を使用して、実行するアクションを決定します。

既定では、ビジー応答はSERVERCALL_RETRYLATERです。 この応答により、呼び出し元のアプリケーションはできるだけ早く呼び出しを再試行します。

## <a name="colemessagefiltersetmessagependingdelay"></a><a name="setmessagependingdelay"></a>メッセージフィルター::メッセージを保留するディミディ

呼び出し元のアプリケーションが、呼び出し元のアプリケーションからの応答を待機してから、さらにアクションを実行する時間を決定します。

```
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>パラメーター

*タイムアウト*<br/>
メッセージ保留遅延のミリ秒数。

### <a name="remarks"></a>解説

この関数は、[設定再試行応答](#setretryreply)と一緒に動作します。

## <a name="colemessagefiltersetretryreply"></a><a name="setretryreply"></a>メッセージフィルター::再試行応答を設定します。

呼び出し元アプリケーションからビジー応答を受信したときの呼び出し元アプリケーションのアクションを決定します。

```
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>パラメーター

*返信を再試行する*<br/>
再試行の間隔 (ミリ秒単位)。

### <a name="remarks"></a>解説

呼び出されたアプリケーションがビジー状態であることを示した場合、呼び出し側のアプリケーションは、サーバーがビジー状態でなくなるまで待機するか、すぐに再試行するか、指定した間隔の後に再試行するかを決定することがあります。 また、通話を完全にキャンセルすることもできます。

呼び出し元の応答は、関数`SetRetryReply`と[SetMessagePendingDelay](#setmessagependingdelay)によって制御されます。 `SetRetryReply`呼び出し元のアプリケーションが、特定の呼び出しの再試行の間に待機する時間を決定します。 `SetMessagePendingDelay`呼び出し側アプリケーションがサーバーからの応答を待機してから、さらにアクションを実行する時間を決定します。

通常、デフォルトは許容可能であり、変更する必要はありません。 フレームワークは、呼び出しが完了するか、メッセージ保留遅延が経過するまで *、nRetryReply*ミリ秒ごとに呼び出しを再試行します。 *nRetryReply*の値 0 は即時再試行を指定し、- 1 は呼び出しの取り消しを指定します。

メッセージ保留の遅延が期限切れになると、ユーザーが呼び出しをキャンセルまたは再試行できるように、OLE の "ビジー ダイアログ ボックス" [(COleBusyDialog](../../mfc/reference/colebusydialog-class.md)を参照) が表示されます。 このダイアログ ボックスを有効または無効にするには[、呼](#enablebusydialog)び出します。

キーボードまたはマウスのメッセージが通話中に保留中で、呼び出しがタイムアウト (メッセージ保留の遅延を超えている) 場合は、[応答なし] ダイアログ ボックスが表示されます。 このダイアログ ボックスを有効または無効にするには[、EnableNotRespondingDialog を](#enablenotrespondingdialog)呼び出します。 通常、この状態は、何かが間違って、ユーザーがせっかちになっていったことを示しています。

ダイアログが無効になっている場合、現在の「再試行応答」は、常にビジー状態のアプリケーションへの呼び出しに使用されます。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
