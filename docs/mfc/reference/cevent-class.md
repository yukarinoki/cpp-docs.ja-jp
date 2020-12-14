---
description: '詳細情報: CEvent クラス'
title: CEvent クラス
ms.date: 11/04/2016
f1_keywords:
- CEvent
- AFXMT/CEvent
- AFXMT/CEvent::CEvent
- AFXMT/CEvent::PulseEvent
- AFXMT/CEvent::ResetEvent
- AFXMT/CEvent::SetEvent
- AFXMT/CEvent::Unlock
helpviewer_keywords:
- CEvent [MFC], CEvent
- CEvent [MFC], PulseEvent
- CEvent [MFC], ResetEvent
- CEvent [MFC], SetEvent
- CEvent [MFC], Unlock
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
ms.openlocfilehash: 0db33c89b52c3c6cb3dbf37cb3ea3da96e6c6c71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184699"
---
# <a name="cevent-class"></a>CEvent クラス

イベントを表します。これは、イベントが発生したことを1つのスレッドが別のスレッドに通知できるようにする同期オブジェクトです。

## <a name="syntax"></a>構文

```
class CEvent : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CEvent:: CEvent](#cevent)|`CEvent` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CEvent::P ulseEvent](#pulseevent)|イベントを使用可能 (シグナル状態) に設定し、待機中のスレッドを解放して、イベントを使用不可 (非シグナル状態) に設定します。|
|[CEvent:: ResetEvent](#resetevent)|イベントを使用不可 (非シグナル状態) に設定します。|
|[CEvent:: SetEvent](#setevent)|イベントを使用可能 (シグナル状態) に設定し、待機中のスレッドをすべて解放します。|
|[CEvent:: Unlock](#unlock)|イベントオブジェクトを解放します。|

## <a name="remarks"></a>解説

イベントは、スレッドがタスクを実行するタイミングを知る必要がある場合に便利です。 たとえば、データアーカイブにデータをコピーするスレッドは、新しいデータが利用可能になったときに通知を受ける必要があります。 オブジェクトを使用して、 `CEvent` 新しいデータが利用可能になったときにコピースレッドに通知することで、スレッドはできるだけ早くタスクを実行できます。

`CEvent` オブジェクトには、手動と自動の2種類があります。

少なくと `CEvent` も1つのスレッドが解放されると、自動オブジェクトは、シグナルを返さない (使用できない) 状態に自動的に戻ります。 既定では、 `CEvent` `TRUE` 構築時に *bmanualreset* パラメーターにを渡していない限り、オブジェクトは自動です。

手動オブジェクトは、 `CEvent` 他の関数が呼び出されるまで、 [SetEvent](#setevent) または [ResetEvent](#resetevent) によって設定された状態のままになります。 手動オブジェクトを作成するには `CEvent` 、 `TRUE` `bManualReset` 構築時にパラメーターにを渡します。

オブジェクトを使用するには `CEvent` 、 `CEvent` 必要に応じてオブジェクトを構築します。 待機するイベントの名前を指定し、アプリケーションで最初に所有する必要があることを指定します。 コンストラクターから制御が戻ったときに、イベントにアクセスできます。 [SetEvent](#setevent)を呼び出してイベントオブジェクトを通知し (利用可能にします)、制御されたリソースへのアクセスが完了したら、 [Unlock](#unlock)を呼び出します。

オブジェクトを使用する別の方法として、 `CEvent` `CEvent` 制御するクラスにデータメンバーとして型の変数を追加する方法があります。 制御されたオブジェクトの構築時に、データメンバーのコンストラクターを呼び出し、 `CEvent` イベントが最初にシグナル状態になるかどうかを指定します。また、必要なイベントオブジェクトの種類、イベントの名前 (プロセスの境界を越えて使用する場合)、および必要なセキュリティ属性も指定します。

この方法でオブジェクトによって制御されるリソースにアクセスするに `CEvent` は、まず、リソースのアクセスメソッドに [CSingleLock](../../mfc/reference/csinglelock-class.md) 型または [CMultiLock](../../mfc/reference/cmultilock-class.md) 型の変数を作成します。 次に、 `Lock` lock オブジェクトのメソッド (たとえば、 [CMultiLock:: lock](../../mfc/reference/cmultilock-class.md#lock)) を呼び出します。 この時点で、スレッドはリソースへのアクセス権を取得し、リソースが解放されてアクセスできるまで待機します。または、リソースが解放されるまで待機し、タイムアウトし、リソースへのアクセスを取得できなくなります。 いずれの場合も、スレッドセーフな方法でリソースにアクセスしています。 リソースを解放するには、 `SetEvent` を呼び出してイベントオブジェクトを通知した後、 `Unlock` lock オブジェクトのメソッド (たとえば、 [CMultiLock:: Unlock](../../mfc/reference/cmultilock-class.md#unlock)) を使用するか、ロックオブジェクトがスコープ外になるようにします。

オブジェクトの使用方法の詳細については `CEvent` 、「 [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>要件

**ヘッダー:** afxmt

## <a name="ceventcevent"></a><a name="cevent"></a> CEvent:: CEvent

名前付きオブジェクトまたは名前のないオブジェクトを構築 `CEvent` します。

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>パラメーター

*ビン分割*<br/>
TRUE の場合、 `CMultilock` オブジェクトまたはオブジェクトのスレッド `CSingleLock` が有効になります。 それ以外の場合は、リソースにアクセスしようとしているすべてのスレッドが待機する必要があります。

*bManualReset*<br/>
TRUE の場合、イベントオブジェクトが手動イベントであることを指定します。それ以外の場合、イベントオブジェクトは自動イベントです。

*lpszName*<br/>
`CEvent` オブジェクトの名前。 オブジェクトがプロセスの境界を越えて使用される場合は、を指定する必要があります。 名前が既存のイベントと一致する場合、コンストラクターは `CEvent` その名前のイベントを参照する新しいオブジェクトを作成します。 名前がイベントではない既存の同期オブジェクトと一致する場合、構築は失敗します。 NULL の場合、名前は null になります。

*lpsaAttribute*<br/>
イベントオブジェクトのセキュリティ属性。 この構造の詳細については、Windows SDK の「 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 」を参照してください。

### <a name="remarks"></a>解説

オブジェクトにアクセスしたり解放したりするには `CEvent` 、 [CMultiLock](../../mfc/reference/cmultilock-class.md) オブジェクトまたは [CSingleLock](../../mfc/reference/csinglelock-class.md) オブジェクトを作成し、その [Lock](../../mfc/reference/csinglelock-class.md#lock) および [Unlock](../../mfc/reference/csinglelock-class.md#unlock) メンバー関数を呼び出します。

オブジェクトの状態 `CEvent` をシグナル状態に変更する (スレッドが待機する必要がない) 場合は、 [SetEvent](#setevent) または [PulseEvent](#pulseevent)を呼び出します。 オブジェクトの状態を非 `CEvent` シグナル状態 (スレッドが待機する必要があります) に設定するには、 [ResetEvent](#resetevent)を呼び出します。

> [!IMPORTANT]
> オブジェクトを作成した後 `CEvent` 、 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) を使用して、ミューテックスが既に存在していないことを確認します。 ミューテックスが予期せずに存在する場合は、不正なプロセスがスクワッティングであることを示している可能性があります。また、ミューテックスを悪用する可能性があります。 この場合、推奨されるセキュリティ意識の高い手順は、ハンドルを閉じて、オブジェクトの作成でエラーが発生したかのように続行することです。

## <a name="ceventpulseevent"></a><a name="pulseevent"></a> CEvent::P ulseEvent

イベントの状態をシグナル状態 (利用可能) に設定し、待機中のスレッドを解放して、自動的に非シグナル状態 (利用不可) にリセットします。

```
BOOL PulseEvent();
```

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

イベントが manual の場合は、待機中のすべてのスレッドが解放され、イベントは非シグナル状態に設定され、が `PulseEvent` 返されます。 イベントが自動の場合、1つのスレッドが解放されると、イベントは非シグナル状態に設定され、が `PulseEvent` 返されます。

待機中のスレッドがない場合、またはスレッドをすぐに解放できない場合、は `PulseEvent` イベントの状態を非シグナル状態に設定し、を返します。

`PulseEvent` は、基になる Win32 `PulseEvent` 関数を使用します。これは、カーネルモードの非同期プロシージャ呼び出しによって待機状態から一時的に削除することができます。 したがって、 `PulseEvent` は信頼性が低く、新しいアプリケーションでは使用できません。 詳細については、「 [PulseEvent 関数](/windows/win32/api/winbase/nf-winbase-pulseevent)」を参照してください。

## <a name="ceventresetevent"></a><a name="resetevent"></a> CEvent:: ResetEvent

[SetEvent](#setevent)メンバー関数によって明示的にシグナル状態に設定されるまで、イベントの状態を非シグナル状態に設定します。

```
BOOL ResetEvent();
```

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

これにより、このイベントにアクセスするすべてのスレッドが待機します。

このメンバー関数は、自動イベントでは使用されません。

## <a name="ceventsetevent"></a><a name="setevent"></a> CEvent:: SetEvent

イベントの状態をシグナル状態に設定し、待機中のスレッドを解放します。

```
BOOL SetEvent();
```

### <a name="return-value"></a>戻り値

関数が正常に実行された場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

イベントが manual の場合、 [ResetEvent](#resetevent) が呼び出されるまでイベントはシグナル状態のままになります。 この場合、複数のスレッドを解放できます。 イベントが自動の場合、イベントは1つのスレッドが解放されるまでシグナル状態のままになります。 その後、システムはイベントの状態を非シグナル状態に設定します。 待機中のスレッドがない場合、状態は1つのスレッドが解放されるまでシグナル状態のままになります。

## <a name="ceventunlock"></a><a name="unlock"></a> CEvent:: Unlock

イベントオブジェクトを解放します。

```
BOOL Unlock();
```

### <a name="return-value"></a>戻り値

スレッドがイベントオブジェクトを所有し、イベントが自動イベントである場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数は、ロックオブジェクトを再利用する必要がある場合に、完了後に解放する自動イベントを現在所有しているスレッドによって呼び出されます。 ロックオブジェクトを再利用しない場合、この関数はロックオブジェクトのデストラクターによって呼び出されます。

## <a name="see-also"></a>関連項目

[CSyncObject クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
