---
title: イベントクラス
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
ms.openlocfilehash: 009a17342cb92025d67bf2fe0df1b9d5c7c0c6f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373958"
---
# <a name="cevent-class"></a>イベントクラス

イベント (あるスレッドがイベントが発生したことを別のスレッドに通知できるようにする同期オブジェクト) を表します。

## <a name="syntax"></a>構文

```
class CEvent : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[イベント::イベント](#cevent)|`CEvent` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[イベント::Pウルセイベント](#pulseevent)|イベントを使用可能 (シグナル状態) に設定し、待機スレッドを解放し、イベントを使用不可 (非シグナル状態) に設定します。|
|[イベント::リセットイベント](#resetevent)|イベントを利用不可(非シグナル状態)に設定します。|
|[イベント::セットイベント](#setevent)|イベントを使用可能 (シグナル状態) に設定し、待機中のスレッドをすべて解放します。|
|[イベント::ロック解除](#unlock)|イベント オブジェクトを解放します。|

## <a name="remarks"></a>解説

イベントは、スレッドがタスクを実行するタイミングを認識する必要がある場合に役立ちます。 たとえば、データをデータ アーカイブにコピーするスレッドは、新しいデータが使用可能になったときに通知する必要があります。 オブジェクトを`CEvent`使用して、新しいデータが使用可能になったときにコピー・スレッドに通知することにより、スレッドはできるだけ早くタスクを実行できます。

`CEvent`オブジェクトには、手動と自動の 2 つのタイプがあります。

自動`CEvent`オブジェクトは、少なくとも 1 つのスレッドが解放された後、自動的に非シグナル状態 (使用不可) 状態に戻ります。 既定では、構築`CEvent`時に`TRUE`*bManualReset*パラメータを渡す場合を除き、オブジェクトは自動的に実行されます。

手動`CEvent`オブジェクトは、他の関数が呼び出されるまで[、SetEvent](#setevent)または[ResetEvent](#resetevent)によって設定された状態にとどまります。 手動`CEvent`オブジェクトを作成するには、構築`TRUE`時に`bManualReset`パラメータを渡します。

オブジェクトを`CEvent`使用するには、必要なときに`CEvent`オブジェクトを構築します。 待機するイベントの名前を指定し、アプリケーションが最初にイベントを所有するように指定します。 コンストラクターが返されるときに、イベントにアクセスできます。 イベント オブジェクトに信号を送信 (使用可能) するには[、SetEvent](#setevent)を呼び出し、制御されたリソースへのアクセスが完了したら[Unlock](#unlock)を呼び出します。

オブジェクトを使用`CEvent`する別の方法として、データ メンバーとして`CEvent`型の変数を、制御するクラスに追加する方法があります。 制御されたオブジェクトの構築時に、データ メンバーの`CEvent`コンストラクターを呼び出し、イベントが最初にシグナル状態になるかどうかを指定し、必要なイベント オブジェクトの種類、イベントの名前 (プロセス境界を越えて使用する場合)、および必要なセキュリティ属性を指定します。

この方法で`CEvent`オブジェクトによって制御されるリソースにアクセスするには、まず、CSingleLock 型[CSingleLock](../../mfc/reference/csinglelock-class.md)の変数を作成するか、リソースのアクセス方法で[CMultiLock](../../mfc/reference/cmultilock-class.md)と入力します。 次に、`Lock`ロック オブジェクトのメソッドを呼び出します (たとえば[、CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock))。 この時点で、スレッドはリソースへのアクセス権を取得するか、リソースが解放されてアクセスできるようになるのを待つか、リソースが解放されるのを待ち、タイムアウトしてリソースにアクセスできなくなります。 いずれの場合も、リソースはスレッド セーフな方法でアクセスされています。 リソースを解放するには、イベント`SetEvent`オブジェクトにシグナルを送信し、ロック`Unlock`オブジェクトのメソッド ([たとえば、CMultiLock::Unlock)](../../mfc/reference/cmultilock-class.md#unlock)を使用するか、ロック オブジェクトをスコープから外します。

オブジェクトの使用方法`CEvent`の詳細については、「[マルチスレッド : 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

## <a name="ceventcevent"></a><a name="cevent"></a>イベント::イベント

名前付きオブジェクトまたは名前`CEvent`のないオブジェクトを構築します。

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
TRUE の場合、`CMultilock`または`CSingleLock`オブジェクトのスレッドが有効になります。 それ以外の場合は、リソースにアクセスするすべてのスレッドが待機する必要があります。

*b手動リセット*<br/>
TRUE の場合、イベント オブジェクトが手動イベントであることを指定します。

*名前を指定します。*<br/>
`CEvent` オブジェクトの名前。 オブジェクトがプロセス境界を越えて使用される場合は、指定する必要があります。 名前が既存のイベントと一致する場合、コンストラクターは`CEvent`、その名前のイベントを参照する新しいオブジェクトを構築します。 名前がイベントではない既存の同期オブジェクトと一致する場合、構築は失敗します。 NULL の場合、名前は NULL になります。

*属性*<br/>
イベント オブジェクトのセキュリティ属性。 この構造の詳細については、Windows SDK の[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))を参照してください。

### <a name="remarks"></a>解説

`CEvent`オブジェクトにアクセスまたは解放するには[、CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトを作成し、[そのロック](../../mfc/reference/csinglelock-class.md#lock)と[ロック解除](../../mfc/reference/csinglelock-class.md#unlock)のメンバー関数を呼び出します。

オブジェクトの状態を`CEvent`シグナル状態に変更するには (スレッドが待機する必要はありません)、SetEvent または[PulseEvent](#setevent)を呼び出します。 [PulseEvent](#pulseevent) オブジェクトの状態を`CEvent`非シグナル状態に設定するには (スレッドは待機する必要があります)、ResetEvent を呼び出します。 [ResetEvent](#resetevent)

> [!IMPORTANT]
> オブジェクトを作成`CEvent`した後[、GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を使用して、ミューテックスが存在していないかどうかを確認します。 ミューテックスが予期せず存在した場合、不正なプロセスがスクワッティングしていることを示している可能性があり、悪意を持ってミューテックスを使用しようとしている可能性があります。 この場合、推奨されるセキュリティ上の問題を意識した手順は、ハンドルを閉じて、オブジェクトの作成に失敗したかのように続行することです。

## <a name="ceventpulseevent"></a><a name="pulseevent"></a>イベント::Pウルセイベント

イベントの状態をシグナル状態 (使用可能) に設定し、待機中のスレッドを解放し、非シグナル状態 (使用不可) に自動的にリセットします。

```
BOOL PulseEvent();
```

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

イベントが手動の場合、待機中のすべてのスレッドが解放され、イベントは非シグナル状態に設定され`PulseEvent`、戻ります。 イベントが自動の場合、単一のスレッドが解放され、イベントは非シグナル状態に設定され`PulseEvent`、戻ります。

待機中のスレッドがない場合、またはすぐに解放できるスレッドがない場合`PulseEvent`は、イベントの状態を非シグナル状態に設定して戻ります。

`PulseEvent`は、カーネル モードの`PulseEvent`非同期プロシージャ呼び出しによって一時的に待機状態から削除できる、基になる Win32 関数を使用します。 したがって、`PulseEvent`信頼性が低いため、新しいアプリケーションで使用しないでください。 詳細については[、PulseEvent 関数](/windows/win32/api/winbase/nf-winbase-pulseevent)を参照してください。

## <a name="ceventresetevent"></a><a name="resetevent"></a>イベント::リセットイベント

イベントの状態を非シグナル状態に[設定](#setevent)します。

```
BOOL ResetEvent();
```

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

これにより、このイベントにアクセスするすべてのスレッドが待機します。

このメンバー関数は、自動イベントでは使用されません。

## <a name="ceventsetevent"></a><a name="setevent"></a>イベント::セットイベント

イベントの状態をシグナル状態に設定し、待機中のスレッドを解放します。

```
BOOL SetEvent();
```

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

イベントが手動の場合[、ResetEvent](#resetevent)が呼び出されるまでイベントはシグナル状態のままになります。 この場合、複数のスレッドを解放できます。 イベントが自動の場合、イベントは単一のスレッドが解放されるまでシグナル状態のままになります。 システムは、イベントの状態を非シグナル状態に設定します。 待機中のスレッドがない場合、1 つのスレッドが解放されるまで、状態はシグナル状態のままです。

## <a name="ceventunlock"></a><a name="unlock"></a>イベント::ロック解除

イベント オブジェクトを解放します。

```
BOOL Unlock();
```

### <a name="return-value"></a>戻り値

スレッドがイベント オブジェクトを所有し、イベントが自動イベントである場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、ロック オブジェクトを再利用する場合、そのスレッドが終了後に解放する自動イベントを現在所有しているスレッドによって呼び出されます。 ロック オブジェクトが再利用されない場合、この関数はロック オブジェクトのデストラクターによって呼び出されます。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
