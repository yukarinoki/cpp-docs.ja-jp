---
description: '詳細情報: COleMessageFilter クラス'
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
ms.openlocfilehash: f0ab1d473704f5355933c04072a195c12fb71c73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226897"
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
|[COleMessageFilter:: COleMessageFilter](#colemessagefilter)|`COleMessageFilter` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleMessageFilter:: BeginBusyState](#beginbusystate)|アプリケーションをビジー状態にします。|
|[COleMessageFilter:: EnableBusyDialog](#enablebusydialog)|呼び出されたアプリケーションがビジー状態のときに表示されるダイアログボックスを有効または無効にします。|
|[COleMessageFilter:: Enablenotのプロパティダイアログ](#enablenotrespondingdialog)|呼び出されたアプリケーションが応答していない場合に表示されるダイアログボックスを有効または無効にします。|
|[COleMessageFilter:: EndBusyState](#endbusystate)|アプリケーションのビジー状態を終了します。|
|[COleMessageFilter:: OnMessagePending](#onmessagepending)|OLE 呼び出しの進行中にメッセージを処理するために、フレームワークによって呼び出されます。|
|[COleMessageFilter:: Register](#register)|メッセージフィルターを OLE システム Dll に登録します。|
|[COleMessageFilter:: Revoke](#revoke)|OLE システム Dll を使用して、メッセージフィルターの登録を取り消します。|
|[COleMessageFilter:: SetBusyReply](#setbusyreply)|ビジー状態のアプリケーションの OLE 呼び出しへの応答を決定します。|
|[COleMessageFilter:: SetMessagePendingDelay](#setmessagependingdelay)|アプリケーションが OLE 呼び出しへの応答を待機する時間を指定します。|
|[COleMessageFilter:: SetRetryReply](#setretryreply)|ビジー状態のアプリケーションに対する呼び出し元アプリケーションの応答を決定します。|

## <a name="remarks"></a>解説

クラスは、 `COleMessageFilter` OLE オートメーションアプリケーションだけでなく、ビジュアル編集サーバーおよびコンテナーアプリケーションにも役立ちます。 呼び出されているサーバーアプリケーションの場合、このクラスを使用して、他のコンテナーアプリケーションからの着信呼び出しが取り消されるか、後で再試行されるようにアプリケーションを "ビジー" にすることができます。 このクラスは、呼び出されたアプリケーションがビジー状態のときに、呼び出し元アプリケーションによって実行されるアクションを決定するためにも使用できます。

一般的な使用方法は、ドキュメントまたはその他の OLE アクセス可能なオブジェクトが破棄される危険がある場合に、サーバーアプリケーションが [BeginBusyState](#beginbusystate) と [EndBusyState](#endbusystate) を呼び出すことです。 これらの呼び出しは、ユーザーインターフェイスの更新中に [CWinApp:: OnIdle](../../mfc/reference/cwinapp-class.md#onidle) で作成されます。

既定では、 `COleMessageFilter` オブジェクトは、アプリケーションの初期化時に割り当てられます。 [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)を使用して取得できます。

これは高度なクラスです。ほとんどの場合、直接操作する必要はありません。

詳細については、「サーバー [: サーバーの実装](../../mfc/servers-implementing-a-server.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>要件

**ヘッダー:** afxole

## <a name="colemessagefilterbeginbusystate"></a><a name="beginbusystate"></a> COleMessageFilter:: BeginBusyState

ビジー状態を開始するには、この関数を呼び出します。

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>解説

[EndBusyState](#endbusystate)と連携して、アプリケーションのビジー状態を制御します。 関数 [SetBusyReply](#setbusyreply) は、アプリケーションがビジー状態のときに、呼び出し元のアプリケーションに対する応答を判断します。

とは、 `BeginBusyState` `EndBusyState` アプリケーションがビジー状態かどうかを判断するカウンターとして、それぞれインクリメントとデクリメントを呼び出します。 たとえば、への2回の呼び出しと、の `BeginBusyState` 1 回の呼び出しで `EndBusyState` は、ビジー状態になります。 ビジー状態を取り消すには `EndBusyState` 、が呼び出されたときと同じ回数を呼び出す必要があり `BeginBusyState` ます。

既定では、フレームワークはアイドル処理中に、 [CWinApp:: OnIdle](../../mfc/reference/cwinapp-class.md#onidle)によって実行されるビジー状態に入ります。 アプリケーションが ON_COMMANDUPDATEUI 通知を処理している間、アイドル処理が完了すると、後で着信呼び出しが処理されます。

## <a name="colemessagefiltercolemessagefilter"></a><a name="colemessagefilter"></a> COleMessageFilter:: COleMessageFilter

`COleMessageFilter` オブジェクトを作成します。

```
COleMessageFilter();
```

## <a name="colemessagefilterenablebusydialog"></a><a name="enablebusydialog"></a> COleMessageFilter:: EnableBusyDialog

[ビジー] ダイアログボックスを有効または無効にします。このダイアログボックスは、OLE 呼び出し中に、メッセージ保留の遅延が期限切れになったときに表示されます ( [SetRetryReply](#setretryreply)を参照)。

```cpp
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnableBusy*<br/>
[ビジー] ダイアログボックスを有効にするか無効にするかを指定します。

## <a name="colemessagefilterenablenotrespondingdialog"></a><a name="enablenotrespondingdialog"></a> COleMessageFilter:: Enablenotのプロパティダイアログ

OLE 呼び出し中にキーボードまたはマウスメッセージが保留中であり、呼び出しがタイムアウトした場合に表示される [応答なし] ダイアログボックスを有効または無効にします。

```cpp
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnableNotResponding*<br/>
[応答なし] ダイアログボックスを有効にするか無効にするかを指定します。

## <a name="colemessagefilterendbusystate"></a><a name="endbusystate"></a> COleMessageFilter:: EndBusyState

ビジー状態を終了するには、この関数を呼び出します。

```
virtual void EndBusyState();
```

### <a name="remarks"></a>解説

[BeginBusyState](#beginbusystate)と連携して、アプリケーションのビジー状態を制御します。 関数 [SetBusyReply](#setbusyreply) は、アプリケーションがビジー状態のときに、呼び出し元のアプリケーションに対する応答を判断します。

とは、 `BeginBusyState` `EndBusyState` アプリケーションがビジー状態かどうかを判断するカウンターとして、それぞれインクリメントとデクリメントを呼び出します。 たとえば、への2回の呼び出しと、の `BeginBusyState` 1 回の呼び出しで `EndBusyState` は、ビジー状態になります。 ビジー状態を取り消すには `EndBusyState` 、が呼び出されたときと同じ回数を呼び出す必要があり `BeginBusyState` ます。

既定では、フレームワークはアイドル処理中に、 [CWinApp:: OnIdle](../../mfc/reference/cwinapp-class.md#onidle)によって実行されるビジー状態に入ります。 アプリケーションが ON_UPDATE_COMMAND_UI 通知を処理している間、アイドル処理が完了した後に着信呼び出しが処理されます。

## <a name="colemessagefilteronmessagepending"></a><a name="onmessagepending"></a> COleMessageFilter:: OnMessagePending

OLE 呼び出しの進行中にメッセージを処理するために、フレームワークによって呼び出されます。

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*pMsg*<br/>
保留中のメッセージへのポインター。

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>解説

呼び出し元のアプリケーションが呼び出しの完了を待機している場合、フレームワークは、 `OnMessagePending` 保留中のメッセージへのポインターを使用してを呼び出します。 既定では、フレームワークは WM_PAINT メッセージをディスパッチします。これにより、長い時間がかかっている呼び出し中にウィンドウの更新が発生する可能性があります。

メッセージフィルターは、アクティブになる前に、 [登録](#register) を呼び出すことによって登録する必要があります。

## <a name="colemessagefilterregister"></a><a name="register"></a> COleMessageFilter:: Register

メッセージフィルターを OLE システム Dll に登録します。

```
BOOL Register();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>解説

メッセージフィルターは、システム Dll に登録されていない限り無効です。 通常、アプリケーションの初期化コードによって、アプリケーションのメッセージフィルターが登録されます。 アプリケーションによって登録された他のすべてのメッセージフィルターは、プログラムが [Revoke](#revoke)の呼び出しによって終了する前に取り消す必要があります。

フレームワークの既定のメッセージフィルターは、初期化中に自動的に登録され、終了時に失効します。

## <a name="colemessagefilterrevoke"></a><a name="revoke"></a> COleMessageFilter:: Revoke

[Register](#register)を呼び出すことによって実行された以前の登録を取り消します。

```cpp
void Revoke();
```

### <a name="remarks"></a>解説

メッセージフィルターは、プログラムが終了する前に取り消す必要があります。

フレームワークによって自動的に作成および登録される既定のメッセージフィルターも自動的に失効します。

## <a name="colemessagefiltersetbusyreply"></a><a name="setbusyreply"></a> COleMessageFilter:: SetBusyReply

この関数は、アプリケーションの "ビジー応答" を設定します。

```cpp
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>パラメーター

*nBusyReply*<br/>
`SERVERCALL`COMPOBJ. H で定義されている列挙体の値。 次のいずれかの値を指定できます。

- SERVERCALL_ISHANDLED アプリケーションは呼び出しを受け入れることができますが、特定の呼び出しの処理に失敗する可能性があります。

- SERVERCALL_REJECTED アプリケーションは、呼び出しを処理できない可能性があります。

- アプリケーションが一時的に呼び出しを処理できない状態にある SERVERCALL_RETRYLATER ます。

### <a name="remarks"></a>解説

[BeginBusyState](#beginbusystate)関数と[EndBusyState](#endbusystate)関数は、アプリケーションのビジー状態を制御します。

アプリケーションがを呼び出してビジー状態になると `BeginBusyState` 、の最後の設定によって決定された値を使用して、OLE システム dll からの呼び出しに応答し `SetBusyReply` ます。 呼び出し元のアプリケーションは、このビジー状態の応答を使用して、実行するアクションを決定します。

既定では、ビジー状態の応答は SERVERCALL_RETRYLATER です。 この応答により、呼び出し元のアプリケーションは、できるだけ早く呼び出しを再試行します。

## <a name="colemessagefiltersetmessagependingdelay"></a><a name="setmessagependingdelay"></a> COleMessageFilter:: SetMessagePendingDelay

呼び出し元のアプリケーションが、呼び出されたアプリケーションからの応答を待機する時間を決定してから、さらにアクションを実行します。

```cpp
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>パラメーター

*nTimeout*<br/>
メッセージを保留している遅延時間のミリ秒数。

### <a name="remarks"></a>解説

この関数は、 [SetRetryReply](#setretryreply)と連携して動作します。

## <a name="colemessagefiltersetretryreply"></a><a name="setretryreply"></a> COleMessageFilter:: SetRetryReply

呼び出されたアプリケーションからビジー状態の応答を受信したときの、呼び出し元アプリケーションのアクションを決定します。

```cpp
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>パラメーター

*nRetryReply*<br/>
再試行の間隔 (ミリ秒単位)。

### <a name="remarks"></a>解説

呼び出されたアプリケーションがビジー状態であることを示すと、呼び出し元のアプリケーションは、サーバーがビジー状態になるまで待機するか、すぐに再試行するか、指定した間隔の後に再試行するかを決定できます。 また、呼び出しを完全に取り消すこともできます。

呼び出し元の応答は、functions `SetRetryReply` と [Setmessagependingdelay](#setmessagependingdelay)によって制御されます。 `SetRetryReply` 呼び出し元のアプリケーションが、特定の呼び出しの再試行の間に待機する時間を指定します。 `SetMessagePendingDelay` 呼び出し元のアプリケーションがサーバーからの応答を待機する時間を指定します。

通常、既定値は許容されるため、変更する必要はありません。 フレームワークは、呼び出しが行われるまで、またはメッセージの保留遅延が期限切れになるまで、 *nRetryReply* ミリ秒ごとに呼び出しを再試行します。 *NRetryReply* の値に0を指定すると、即時再試行が指定され、-1 は呼び出しの取り消しを指定します。

メッセージ保留の遅延が期限切れになると、OLE の [ビジー] ダイアログボックス ( [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)を参照) が表示され、ユーザーは呼び出しをキャンセルするか再試行するかを選択できます。 [EnableBusyDialog](#enablebusydialog)を呼び出して、このダイアログボックスを有効または無効にします。

通話中にキーボードまたはマウスのメッセージが保留状態になっていて、呼び出しがタイムアウトした (メッセージが保留中の遅延を超えている) 場合は、[応答なし] ダイアログボックスが表示されます。 このダイアログボックスを有効または無効にするには、 [Enablenotの設定ダイアログ](#enablenotrespondingdialog) を呼び出してください。 通常、この問題の状態は、何らかの問題が発生し、ユーザーが待ちきれずを取得していることを示します。

ダイアログが無効になっている場合、ビジー状態のアプリケーションの呼び出しでは、現在の "再試行応答" が常に使用されます。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
