---
title: CEvent クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 1da3dc6df825988794481795ca7e47e72b5736bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367504"
---
# <a name="cevent-class"></a>CEvent クラス
これは 1 つのスレッドに別のイベントが発生したことを通知できるようにする同期オブジェクト、イベントを表します。  
  
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
|[CEvent::PulseEvent](#pulseevent)|セットは、そのイベントを利用可能な (シグナル)、待機中のスレッドを解放し、イベントを (非シグナル) 利用不可に設定します。|  
|[CEvent::ResetEvent](#resetevent)|(非シグナル) を使用できないイベントを設定します。|  
|[CEvent::SetEvent](#setevent)|使用可能な (シグナル)、イベントを設定し、待機中のスレッドを解放します。|  
|[CEvent::Unlock](#unlock)|イベント オブジェクトを解放します。|  
  
## <a name="remarks"></a>コメント  
 イベントは、スレッドは、そのタスクを実行するタイミングを知る必要があるときに便利です。 たとえば、データ アーカイブにデータをコピーするスレッドは、新しいデータが使用可能な場合に通知する必要があります。 使用して、`CEvent`オブジェクトに新しいデータがある場合、コピー スレッドの通知をできるだけ早く、スレッドがそのタスクを行うことができます。  
  
 `CEvent` オブジェクトに 2 種類があります: 手動と自動です。  
  
 自動`CEvent`には、少なくとも 1 つのスレッドが解放された後、このオブジェクトは、自動的を非シグナル (使用不可) 状態を返します。 既定では、`CEvent`しない限り、オブジェクトが自動`TRUE`の`bManualReset`構築時にパラメーター。  
  
 手動`CEvent`設定された状態のままになるオブジェクト[SetEvent](#setevent)または[ResetEvent](#resetevent)他の関数が呼び出されるまでです。 手動作成を`CEvent`オブジェクトを渡す`TRUE`の`bManualReset`構築時にパラメーター。  
  
 使用する、`CEvent`オブジェクトを構築、`CEvent`オブジェクトが必要なとき。 待機しても、アプリケーションする必要があります最初に所有いることを指定するイベントの名前を指定します。 コンス トラクターは、返されるときにイベントを表示できます。 呼び出す[SetEvent](#setevent)をシグナル (使用可能な)、イベント オブジェクトとを呼び出します[Unlock](#unlock)が完了すると被制御リソースにアクセスします。  
  
 別の方法を使用するため`CEvent`オブジェクトは、型の変数を追加する`CEvent`を制御クラスにデータ メンバーとして参加します。 コンス トラクターの呼び出し、制御されるオブジェクトの構築時に、`CEvent`データ メンバーかどうか、イベントがシグナル状態が最初と指定する、イベント オブジェクト (がプロセスで使用される場合、イベントの名前の型と境界)、および必要な任意のセキュリティ属性。  
  
 によって制御されるリソースにアクセスする、`CEvent`オブジェクトのこのようないずれかの型の変数をまず作成[CSingleLock](../../mfc/reference/csinglelock-class.md)または型[CMultiLock](../../mfc/reference/cmultilock-class.md)リソースのアクセス方法にします。 まず、`Lock`ロック オブジェクトのメソッド (たとえば、 [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock))。 この時点では、スレッドはいずれかリソース、リソースに解放して、アクセスを取得またはリソースが解放されるまで待つを待っている間にタイムアウトへのアクセスし、リソースにアクセスするために失敗します。 いずれの場合、リソースがスレッド セーフな方法でアクセスされました。 リソースを解放する呼び出し`SetEvent`イベント オブジェクトを通知し、使用して、`Unlock`ロック オブジェクトのメソッド (たとえば、 [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock))、させたり、ロック オブジェクトがスコープ外に分類されます。  
  
 使用する方法の詳細についての`CEvent`、オブジェクトを参照してください[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。  
  
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
 名前付きまたは名前のない構築`CEvent`オブジェクト。  
  
```  
CEvent(
    BOOL bInitiallyOwn = FALSE,  
    BOOL bManualReset = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bInitiallyOwn`  
 場合**TRUE**、スレッドの**CMultilock**または`CSingleLock`オブジェクトが有効にします。 それ以外の場合、リソースのアクセスを求めているすべてのスレッドは待機する必要があります。  
  
 *bManualReset*  
 場合**TRUE**、イベント オブジェクトが手動イベントか、それ以外の場合、イベント オブジェクトは、自動イベントを指定します。  
  
 `lpszName`  
 `CEvent` オブジェクトの名前。 プロセスの境界を越えてオブジェクトを使用する場合を指定する必要があります。 コンス トラクターは、ビルド、新しい名前には、既存のイベントが一致すると、`CEvent`その名前のイベントを参照するオブジェクト。 名前には、イベントではない既存の同期オブジェクトが一致すると、構築が失敗します。 場合**NULL**名前は null になります。  
  
 `lpsaAttribute`  
 イベント オブジェクトのセキュリティ属性。 この構造体の詳細を参照してください。 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK に含まれています。  
  
### <a name="remarks"></a>コメント  
 アクセスまたはリリース、`CEvent`オブジェクトを作成、 [CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。  
  
 状態を変更する、`CEvent`シグナル状態にオブジェクト (スレッドがない待機する) を呼び出す[SetEvent](#setevent)または[PulseEvent](#pulseevent)です。 状態を設定する、`CEvent`シグナルをオブジェクト (スレッド待つ必要があります)、呼び出す[ResetEvent](#resetevent)です。  
  
> [!IMPORTANT]
>  作成した後、`CEvent`オブジェクトを使用して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)ミュー テックスが既に存在していないすることを確認します。 ミュー テックスが予期せず存在、悪意のあるプロセスが発生したり、悪意ミュー テックスを使用することがある必ずしも意図している可能性があります。 ここでは、推奨されるセキュリティを考慮したプロシージャがハンドルを終了し、クリックすると、オブジェクトの作成でエラーが発生しました。  
  
##  <a name="pulseevent"></a>  CEvent::PulseEvent  
 (使用可能) イベントが通知の状態を設定、任意の待機中のスレッドを解放し、リセットを非シグナル (使用不可) 自動的にします。  
  
```  
BOOL PulseEvent();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 イベントが手動の場合は、すべての待機中のスレッドが解放されます、イベントが非シグナル状態に設定されてと`PulseEvent`を返します。 イベントが自動の場合は、1 つのスレッドが解放される、イベントが非シグナル状態に設定されてと`PulseEvent`を返します。  
  
 待機しているスレッドがないか、すぐに解放する`PulseEvent`するイベントの状態を非シグナル状態に設定しを返します。  
  
 `PulseEvent` 基になる Win32 を使用して`PulseEvent`関数で、すぐに削除できます待機状態から、カーネル モードの非同期のプロシージャ呼び出しで。 したがって、`PulseEvent`信頼性が低いと、新しいアプリケーションでは使用できません。 詳細については、次を参照してください。、 [PulseEvent 関数](http://msdn.microsoft.com/library/windows/desktop/ms684914)です。  
  
##  <a name="resetevent"></a>  CEvent::ResetEvent  
 設定するイベントの状態まで非シグナル状態に明示的にシグナル状態に設定、 [SetEvent](#setevent)メンバー関数。  
  
```  
BOOL ResetEvent();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これにより、すべてのスレッドが待機するには、このイベントにアクセスしようとしています。  
  
 このメンバー関数は、自動イベントでは使用されません。  
  
##  <a name="setevent"></a>  CEvent::SetEvent  
 待機中のスレッドを解放するイベントをシグナルの状態を設定します。  
  
```  
BOOL SetEvent();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 イベントをまでシグナル状態になりますが、イベントが手動の場合は、 [ResetEvent](#resetevent)と呼びます。 ここでは、複数のスレッドが解放できます。 イベントが自動の場合は、イベント シグナル状態になります、1 つのスレッドが解放されるまでです。 システムは、非シグナル状態に、イベントの状態が設定されます。 スレッドが待機していない場合、状態は、1 つのスレッドが解放されるまでシグナル状態のままです。  
  
##  <a name="unlock"></a>  CEvent::Unlock  
 イベント オブジェクトを解放します。  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>戻り値  
 イベント オブジェクトとイベント スレッドが所有している場合は 0 以外は、自動イベントです。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を解放することが、終了後、ロック オブジェクトが再利用することがある場合、自動イベントを現在所有するスレッドで呼び出されます。 ロック オブジェクトは、再利用することはできませんの場合は、ロック オブジェクトのデストラクターでこの関数が呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)

