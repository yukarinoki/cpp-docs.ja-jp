---
title: CEvent クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CEvent
- AFXMT/CEvent
- AFXMT/CEvent::CEvent
- AFXMT/CEvent::PulseEvent
- AFXMT/CEvent::ResetEvent
- AFXMT/CEvent::SetEvent
- AFXMT/CEvent::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CEvent [MFC], CEvent
- CEvent [MFC], PulseEvent
- CEvent [MFC], ResetEvent
- CEvent [MFC], SetEvent
- CEvent [MFC], Unlock
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8dff47314c5e8932a6f5a2a2078fd70a86c9229b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386497"
---
# <a name="cevent-class"></a>CEvent クラス

1 つのスレッドに別のイベントが発生したことを通知できるようにする同期オブジェクトであるイベントを表します。

## <a name="syntax"></a>構文

```
class CEvent : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CEvent::CEvent](#cevent)|`CEvent` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CEvent::PulseEvent](#pulseevent)|セットは使用可能なイベント (通知)、待機中のスレッドを解放し、(非シグナル) を使用できないイベントを設定します。|
|[CEvent::ResetEvent](#resetevent)|(非シグナル) を使用できないイベントを設定します。|
|[CEvent::SetEvent](#setevent)|(シグナル) を使用可能なイベントを設定し、待機中のスレッドを解放します。|
|[CEvent::Unlock](#unlock)|イベント オブジェクトを解放します。|

## <a name="remarks"></a>Remarks

イベントは、スレッドがそのタスクを実行するタイミングを知る必要がある場合に便利です。 たとえば、新しいデータが使用可能なときに、データ アーカイブにデータをコピーするスレッドを通知する必要があります。 使用して、`CEvent`オブジェクトに新しいデータがある場合、コピーのスレッドを通知する、スレッドは、できるだけ早くそのタスクを行うことができます。

`CEvent` オブジェクトが 2 種類があります。 手動および自動。

自動`CEvent`を少なくとも 1 つのスレッドが解放された後、このオブジェクトは、自動的に非シグナル (使用不可) 状態を返します。 既定で、`CEvent`しない限り、オブジェクトが自動`TRUE`の*bManualReset*構築時にパラメーター。

手動`CEvent`オブジェクトによって設定された状態のままになる[SetEvent](#setevent)または[ResetEvent](#resetevent)他の関数が呼び出されるまでです。 手動で作成する`CEvent`オブジェクトを渡す`TRUE`の`bManualReset`構築時にパラメーター。

使用する、`CEvent`オブジェクトを構築、`CEvent`オブジェクトが必要です。 待機し、アプリケーションが最初に所有していることを指定するイベントの名前を指定します。 コンス トラクターは、返されるときにイベントを表示できます。 呼び出す[SetEvent](#setevent)信号 (利用できるように) に、イベント オブジェクトと、呼び出し[ロックの解除](#unlock)したら被制御リソースにアクセスします。

代替の方法を使用して`CEvent`オブジェクトは、型の変数を追加する`CEvent`を制御クラスにデータ メンバーとして参加します。 コンス トラクターを呼び出し、制御されるオブジェクトの構築時に、`CEvent`データ メンバー イベントが最初に通知するかどうか、およびイベント オブジェクトが、(プロセス全体で使用される場合、イベントの名前の型も指定境界)、および必要な任意のセキュリティ属性。

によって制御されるリソースにアクセスする、`CEvent`オブジェクトのこの方法では、まずいずれかの型の変数を作成[CSingleLock](../../mfc/reference/csinglelock-class.md)または型[CMultiLock](../../mfc/reference/cmultilock-class.md)リソースのアクセス方法にします。 呼び出して、`Lock`ロック オブジェクトのメソッド (たとえば、 [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock))。 この時点では、スレッドか、リソース、リリースされると、アクセスを取得またはリソースが解放されるを待機するリソースの待機、タイムアウトへのアクセスをリソースへのアクセスに失敗します。 いずれの場合も、リソースがスレッド セーフな方法でアクセスされました。 リソースを解放する呼び出し`SetEvent`、イベント オブジェクトを通知し、使用して、`Unlock`ロック オブジェクトのメソッド (たとえば、 [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock))、またはロック オブジェクトがスコープ外に分類されます。

使用する方法の詳細についての`CEvent`、オブジェクトを参照してください[マルチ スレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。

## <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>要件

**ヘッダー:** afxmt.h

##  <a name="cevent"></a>  CEvent::CEvent

名前付きセーブポイントまたは名前のない、コンストラクト`CEvent`オブジェクト。

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>パラメーター

*bInitiallyOwn*<br/>
TRUE の場合、スレッド、`CMultilock`または`CSingleLock`オブジェクトが有効になっています。 それ以外の場合、リソースにアクセスしようとしているすべてのスレッドが待機する必要があります。

*bManualReset*<br/>
TRUE の場合は、イベント オブジェクトは、手動イベント、それ以外の場合、イベント オブジェクトは、自動のイベントを指定します。

*lpszName*<br/>
`CEvent` オブジェクトの名前。 プロセスの境界を越えてオブジェクトを使用する場合を指定する必要があります。 名前が既存のイベントに一致する場合、コンス トラクターは新しい`CEvent`その名前のイベントを参照するオブジェクト。 名前には、イベントではない既存の同期オブジェクトが一致すると、構築は失敗します。 NULL の場合、名前が null になります。

*lpsaAttribute*<br/>
イベント オブジェクトのセキュリティ属性。 この構造体の詳細については、次を参照してください。 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK に含まれています。

### <a name="remarks"></a>Remarks

アクセスまたはリリースを`CEvent`オブジェクトを作成、 [CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。

状態を変更する、`CEvent`シグナル状態になるオブジェクト (スレッドがないを待機する) を呼び出す[SetEvent](#setevent)または[PulseEvent](#pulseevent)します。 状態を設定する、`CEvent`非シグナル状態のオブジェクト (スレッド待つ必要があります)、呼び出す[ResetEvent](#resetevent)します。

> [!IMPORTANT]
>  作成した後、`CEvent`オブジェクトを使用して[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)ミュー テックスが既に存在していないことを確認します。 予期せずにミュー テックスが存在して、不正なプロセスが発生したり、悪意のあるミュー テックスを使用するつもりが可能性があります。 ここでは、セキュリティ意識の推奨手順は、ハンドルを終了し、クリックすると、オブジェクトの作成でエラーが発生しました。

##  <a name="pulseevent"></a>  CEvent::PulseEvent

(使用可能) イベントをシグナルの状態を設定、待機スレッドを解放、自動的にリセットするように非シグナル (使用不可)。

```
BOOL PulseEvent();
```

### <a name="return-value"></a>戻り値

関数が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

イベントが手動の場合は、待機中のすべてのスレッドがリリースされた、イベントが非シグナル状態に設定されてと`PulseEvent`を返します。 イベントが自動の場合は、1 つのスレッドが解放される、イベントが非シグナル状態に設定されてと`PulseEvent`を返します。

スレッドが待機しているないか、すぐに解放する`PulseEvent`するイベントの状態を非シグナル状態に設定し、返します。

`PulseEvent` 基になる Win32 を使用して`PulseEvent`関数は、一時的に削除できる待機状態からカーネル モードの非同期プロシージャ呼び出しで。 そのため、`PulseEvent`の信頼性が低いと、新しいアプリケーションでは使用されません。 詳細については、次を参照してください。、 [PulseEvent 関数](/windows/desktop/api/winbase/nf-winbase-pulseevent)します。

##  <a name="resetevent"></a>  CEvent::ResetEvent

設定するイベントの状態まで非シグナル状態に明示的にシグナル状態に設定、 [SetEvent](#setevent)メンバー関数。

```
BOOL ResetEvent();
```

### <a name="return-value"></a>戻り値

関数が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

これにより、すべてのスレッドが待機するには、このイベントにアクセスしたいです。

このメンバー関数は、自動イベントでは使用されません。

##  <a name="setevent"></a>  CEvent::SetEvent

待機中のスレッドを解放するシグナルを受信するイベントの状態を設定します。

```
BOOL SetEvent();
```

### <a name="return-value"></a>戻り値

0 以外の場合、関数が成功した場合は 0 それ以外の場合。

### <a name="remarks"></a>Remarks

イベントをまでシグナル状態になりますが、イベントが手動の場合は、 [ResetEvent](#resetevent)が呼び出されます。 複数のスレッドは、ここで解放できます。 イベントが自動の場合は、1 つのスレッドが解放されるまで、イベントがシグナル状態残ります。 システムは、非シグナル状態イベントの状態が設定されます。 スレッドが待機していない場合、状態は、1 つのスレッドが解放されるまでシグナル状態のままです。

##  <a name="unlock"></a>  CEvent::Unlock

イベント オブジェクトを解放します。

```
BOOL Unlock();
```

### <a name="return-value"></a>戻り値

自動イベントをイベント オブジェクトと、イベント、スレッドが所有している場合は 0 以外にはそれ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、自動イベントにリリースが完了したら、後に再利用する場合は、ロック オブジェクトを現在所有されたスレッドにより呼び出されます。 ロック オブジェクトは、再利用することはありませんが場合、は、ロック オブジェクトのデストラクターでこの関数と呼ばれます。

## <a name="see-also"></a>関連項目

[CSyncObject クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)

