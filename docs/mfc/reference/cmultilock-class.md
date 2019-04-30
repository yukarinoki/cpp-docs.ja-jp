---
title: CMultiLock クラス
ms.date: 11/04/2016
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
helpviewer_keywords:
- CMultiLock [MFC], CMultiLock
- CMultiLock [MFC], IsLocked
- CMultiLock [MFC], Lock
- CMultiLock [MFC], Unlock
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
ms.openlocfilehash: 107ed227c5515cbf2fcb08e957a64a4a17d8287a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366811"
---
# <a name="cmultilock-class"></a>CMultiLock クラス

マルチスレッド プログラムで複数のリソースのアクセス制御に使うアクセス コントロール機構を表します。

## <a name="syntax"></a>構文

```
class CMultiLock
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMultiLock::CMultiLock](#cmultilock)|`CMultiLock` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMultiLock::IsLocked](#islocked)|配列内の特定の同期オブジェクトがロックされているかどうかを決定します。|
|[CMultiLock::Lock](#lock)|同期オブジェクトの配列を待機します。|
|[CMultiLock::Unlock](#unlock)|すべての所有する同期オブジェクトを解放します。|

## <a name="remarks"></a>Remarks

`CMultiLock` 基本クラスはありません。

同期クラスを使用する[CSemaphore](../../mfc/reference/csemaphore-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、および[CEvent](../../mfc/reference/cevent-class.md)、いずれかを作成することができます、`CMultiLock`または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトを待機し、同期オブジェクトを解放します。 使用して、`CMultiLock`特定の時刻に使用できる複数のオブジェクトがある場合。 使用`CSingleLock`のみ必要がある場合、一度に 1 つのオブジェクトで待機します。

使用する、`CMultiLock`オブジェクトは、まずで待機する同期オブジェクトの配列を作成します。 次に、呼び出し、`CMultiLock`制御されるリソースのクラスのメンバー関数内のオブジェクトのコンス トラクター。 呼び出して、[ロック](#lock)リソースが使用可能なかどうかを判断するメンバー関数 (通知)。 1 つは、メンバー関数の残りの部分に進みます。 リソースが使用できない場合は、一定のリソースが解放されるまでの時間を待つか、failure を返します。 リソースの使用が完了したら、後、 [Unlock](#unlock)関数の場合、`CMultiLock`オブジェクトがもう一度、使用するか、許可するが、`CMultiLock`オブジェクトを破棄します。

`CMultiLock` オブジェクトは、スレッドの数が多いが最も役に立つ`CEvent`オブジェクトに対応できます。 すべてを含む配列を作成、`CEvent`ポインター、および呼び出し`Lock`します。 これにより、イベントのいずれかが通知されるまで待機するスレッド。

使用する方法の詳細についての`CMultiLock`オブジェクトは、記事をご覧ください。[マルチ スレッド。同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`CMultiLock`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

##  <a name="cmultilock"></a>  CMultiLock::CMultiLock

`CMultiLock` オブジェクトを構築します。

```
CMultiLock(
    CSyncObject* ppObjects [ ],
    DWORD dwCount,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>パラメーター

*ppObjects*<br/>
待機する同期オブジェクトへのポインターの配列。 Nll は指定できません。

*dwCount*<br/>
オブジェクトの数*ppObjects*します。 1 以上であることが必要です。

*bInitialLock*<br/>
最初に指定されたオブジェクトのいずれかにアクセスしようとするかどうかを指定します。

### <a name="remarks"></a>Remarks

この関数は待機する同期オブジェクトの配列を作成後に呼び出されます。 通常、使用可能になる同期オブジェクトの 1 つを待機する必要がありますのスレッド内から呼び出されます。

##  <a name="islocked"></a>  CMultiLock::IsLocked

指定したオブジェクトが非シグナル状態かどうかを (使用不可)。

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>パラメーター

*dwItem*<br/>
状態が照会されるオブジェクトに対応するオブジェクトの配列内のインデックス。

### <a name="return-value"></a>戻り値

指定したオブジェクトがロックされている場合は 0 以外それ以外の場合 0 を返します。

##  <a name="lock"></a>  CMultiLock::Lock

指定された同期オブジェクトによって制御されるリソースの 1 つ以上にアクセスするには、この関数を呼び出して、`CMultiLock`コンス トラクター。

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>パラメーター

*dwTimeOut*<br/>
使用できる同期オブジェクトを待機する時間を指定します (通知)。 場合、無限`Lock`を返す前に、オブジェクトがシグナル状態になるまで待機します。

*bWaitForAll*<br/>
待機時間のすべてのオブジェクトを返す前に同時にシグナル状態になる必要があるかどうかを指定します。 FALSE の場合、`Lock`待機オブジェクトのいずれかがシグナルを受け取るが返されます。

*dwWakeMask*<br/>
待機を中止できるはその他の条件を指定します。 このパラメーターの使用可能なオプションの完全な一覧は、次を参照してください。 [MsgWaitForMultipleObjects](/windows/desktop/api/winuser/nf-winuser-msgwaitformultipleobjects) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

場合`Lock`失敗すると、以下の値を返します - 1。 成功した場合、次の値のいずれかが返されます。

- WAIT_OBJECT_0 と WAIT_OBJECT_0 と (1 - オブジェクトの数) の間

   場合*bWaitForAll*が true の場合、すべてのオブジェクトが (使用可能) に通知されます。 場合*bWaitForAll* false で、戻り値 - WAIT_OBJECT_0 が (使用可能) に通知されるオブジェクトのオブジェクトの配列内のインデックス。

- WAIT_OBJECT_0 + (オブジェクトの数)

   指定されたイベント*dwWakeMask*はスレッドの入力キューで使用できます。

- WAIT_ABANDONED_0 と WAIT_ABANDONED_0 と (1 - オブジェクトの数) の間

   場合*bWaitForAll* true、すべてのオブジェクトがシグナル状態、および放棄されたミュー テックス オブジェクトは、少なくとも 1 つのオブジェクト。 場合*bWaitForAll* false で、戻り値 - WAIT_ABANDONED_0 は待機を実行する放棄されたミュー テックス オブジェクトのオブジェクトの配列内のインデックス。

- 正常に終了しました。

   指定されたタイムアウト間隔*dwTimeOut*待機に成功することがなく有効期限が切れました。

### <a name="remarks"></a>Remarks

場合*bWaitForAll*が true の場合、`Lock`は正常に同時にすべての同期オブジェクトがシグナル状態になるとすぐに返します。 場合*bWaitForAll* false で、`Lock`が、1 つまたは複数の同期オブジェクトがシグナル状態にすると、すぐに返されます。

場合`Lock`以上で指定されたミリ秒数を待つ、すぐに返すことがない、 *dwTimeOut*パラメーターを返す前にします。 場合*dwTimeOut*無限、`Lock`オブジェクトへのアクセスを獲得またはで指定された条件になるまでは返されません*dwWakeMask*が満たされています。 の場合`Lock`された同期オブジェクトを取得すること、が返されますが正常にはない場合は、エラーが返されます。

##  <a name="unlock"></a>  CMultiLock::Unlock

によって所有されている同期オブジェクトを解放`CMultiLock`します。

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>パラメーター

*lCount*<br/>
解放する参照の数をカウントします。 1 以上であることが必要です。 指定された量を最大値を超えるオブジェクトの数となる、カウントは変更されませんし、関数は FALSE を返します。

*lPrevCount*<br/>
同期オブジェクトが、前のカウントを受け取るように、変数へのポインター。 NULL の場合、前のカウントは返されません。

### <a name="return-value"></a>戻り値

関数が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数を呼び出して`CMultiLock`のデストラクター。

最初のフォーム`Unlock`によって管理される同期オブジェクトのロックを解除しようとしています。`CMultiLock`します。 2 番目の形式の`Unlock`のロックを解除しようとする、`CSemaphore`が所有するオブジェクト`CMultiLock`します。 場合`CMultiLock`いずれかを所有していないロック`CSemaphore`オブジェクト、関数は FALSE を返します。 それ以外の場合、TRUE を返します。 *lCount*と*lpPrevCount*のパラメーターと同じではまったく[CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)します。 2 番目の形式の`Unlock`は多重状況に適用可能なことはほとんどありません。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)
