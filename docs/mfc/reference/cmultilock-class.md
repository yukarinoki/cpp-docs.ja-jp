---
description: '詳細情報: CMultiLock クラス'
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
ms.openlocfilehash: 1a45c3c302b9f8028061649e2a0d270d47ed58aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331547"
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
|[CMultiLock:: CMultiLock](#cmultilock)|`CMultiLock` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMultiLock:: IsLocked](#islocked)|配列内の特定の同期オブジェクトがロックされているかどうかを判断します。|
|[CMultiLock:: Lock](#lock)|同期オブジェクトの配列を待機します。|
|[CMultiLock:: Unlock](#unlock)|所有されている同期オブジェクトをすべて解放します。|

## <a name="remarks"></a>解説

`CMultiLock` に基底クラスがありません。

同期クラスの[CSemaphore](../../mfc/reference/csemaphore-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、および[CEvent](../../mfc/reference/cevent-class.md)を使用するには、または CSingleLock オブジェクトを作成して、 `CMultiLock` 同期オブジェクトを待機して[](../../mfc/reference/csinglelock-class.md)解放します。 `CMultiLock`特定の時刻に使用できる複数のオブジェクトがある場合は、を使用します。 一度 `CSingleLock` に1つのオブジェクトだけを待機する必要がある場合に使用します。

オブジェクトを使用するには `CMultiLock` 、まず、待機する同期オブジェクトの配列を作成します。 次に、オブジェクトのコンストラクターを、制御された `CMultiLock` リソースのクラスのメンバー関数内で呼び出します。 次に、 [Lock](#lock) メンバー関数を呼び出して、リソースが使用可能 (シグナル状態) であるかどうかを確認します。 存在する場合は、メンバー関数の残りの部分で続行します。 使用可能なリソースがない場合は、リソースが解放されるまで、指定された時間待機するか、失敗を返します。 リソースの使用が完了した後、オブジェクトを再度使用する場合は [Unlock](#unlock) 関数を呼び出し、 `CMultiLock` オブジェクトを破棄することを許可し `CMultiLock` ます。

`CMultiLock` オブジェクトが最も役に立つのは、スレッドが多数の `CEvent` オブジェクトに応答できる場合です。 すべてのポインターを含む配列を作成し、を `CEvent` 呼び出し `Lock` ます。 これにより、イベントの1つがシグナル状態になるまでスレッドは待機します。

オブジェクトの使用方法の詳細については、 `CMultiLock` 「 [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CMultiLock`

## <a name="requirements"></a>要件

**ヘッダー:** afxmt

## <a name="cmultilockcmultilock"></a><a name="cmultilock"></a> CMultiLock:: CMultiLock

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
*Ppobjects* 内のオブジェクトの数。 1 以上であることが必要です。

*bInitialLock*<br/>
指定されたオブジェクトのいずれかに最初にアクセスしようとするかどうかを指定します。

### <a name="remarks"></a>解説

この関数は、待機する同期オブジェクトの配列を作成した後に呼び出されます。 通常は、同期オブジェクトの1つが使用可能になるのを待機する必要があるスレッド内から呼び出されます。

## <a name="cmultilockislocked"></a><a name="islocked"></a> CMultiLock:: IsLocked

指定したオブジェクトが非シグナル状態 (利用不可) かどうかを判断します。

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>パラメーター

*dwItem*<br/>
状態を照会するオブジェクトに対応するオブジェクトの配列内のインデックス。

### <a name="return-value"></a>戻り値

指定したオブジェクトがロックされている場合は0以外の場合は。それ以外の場合は0です。

## <a name="cmultilocklock"></a><a name="lock"></a> CMultiLock:: Lock

コンストラクターに渡された同期オブジェクトによって制御される1つ以上のリソースへのアクセスを取得するには、この関数を呼び出し `CMultiLock` ます。

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>パラメーター

*dwTimeOut*<br/>
同期オブジェクトが使用可能になるまで待機する時間を指定します (シグナル状態)。 無限の場合、 `Lock` はオブジェクトがシグナル状態になるまで待機してから制御を戻します。

*bWaitForAll*<br/>
待機しているすべてのオブジェクトが、を返す前に同時にシグナル状態になる必要があるかどうかを指定します。 FALSE の場合、 `Lock` が待機しているいずれかのオブジェクトがシグナル状態になると、はを返します。

*dwWakeMask*<br/>
待機を中止することが許可されている他の条件を指定します。 このパラメーターに使用できるオプションの完全な一覧については、Windows SDK の「 [MsgWaitForMultipleObjects](/windows/win32/api/winuser/nf-winuser-msgwaitformultipleobjects) 」を参照してください。

### <a name="return-value"></a>戻り値

が失敗した場合は、 `Lock` -1 を返します。 成功した場合は、次のいずれかの値が返されます。

- WAIT_OBJECT_0 と WAIT_OBJECT_0 + (オブジェクトの数-1)

   *Bwaitforall* が TRUE の場合、すべてのオブジェクトが通知されます (利用可能)。 *Bwaitforall* が FALSE の場合、戻り値-WAIT_OBJECT_0 は、シグナル状態 (利用可能) であるオブジェクトのオブジェクトの配列内のインデックスです。

- WAIT_OBJECT_0 + (オブジェクトの数)

   *DwWakeMask* で指定されたイベントは、スレッドの入力キューで使用できます。

- WAIT_ABANDONED_0 と WAIT_ABANDONED_0 + (オブジェクトの数-1)

   *Bwaitforall* が TRUE の場合、すべてのオブジェクトがシグナル状態になり、少なくとも1つのオブジェクトが破棄された mutex オブジェクトになります。 *Bwaitforall* が FALSE の場合、戻り値-WAIT_ABANDONED_0 は、待機を満たした破棄された mutex オブジェクトのオブジェクトの配列内のインデックスです。

- WAIT_TIMEOUT

   *DwTimeOut* で指定されたタイムアウト間隔が、待機の終了なしで期限切れになりました。

### <a name="remarks"></a>解説

*Bwaitforall* が TRUE の場合、 `Lock` すべての同期オブジェクトが同時に通知されるとすぐに、が正常に返されます。 *Bwaitforall* が FALSE の場合、は `Lock` 1 つ以上の同期オブジェクトがシグナル状態になるとすぐに、を返します。

`Lock`がすぐに制御を返すことができない場合、 *dwTimeOut* パラメーターに指定されたミリ秒数を超えるまで待機してから制御が戻るようにします。 *DwTimeOut* が無限の場合、 `Lock` オブジェクトへのアクセスが取得されるか、 *dwWakeMask* で指定された条件が満たされるまで、はを返しません。 それ以外の場合、 `Lock` が同期オブジェクトを取得できた場合は、正常に返されます。存在しない場合は、エラーが返されます。

## <a name="cmultilockunlock"></a><a name="unlock"></a> CMultiLock:: Unlock

によって所有されている同期オブジェクトを解放 `CMultiLock` します。

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>パラメーター

*lCount*<br/>
解放する参照カウントの数。 1 以上であることが必要です。 指定された量が原因でオブジェクトのカウントが最大値を超えた場合、カウントは変更されず、関数は FALSE を返します。

*lPrevCount*<br/>
は、同期オブジェクトの前のカウントを受け取る変数を指します。 NULL の場合、前のカウントは返されません。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、のデストラクターによって呼び出され `CMultiLock` ます。

の最初の形式は、 `Unlock` によって管理される同期オブジェクトのロックを解除しようとし `CMultiLock` ます。 の2番目の形式は、 `Unlock` によって所有されているオブジェクトのロックを解除しようと `CSemaphore` `CMultiLock` します。 `CMultiLock`がロックされたオブジェクトを所有していない場合、 `CSemaphore` 関数は FALSE を返します。それ以外の場合は TRUE を返します。 *lCount* と *Lpprevcount* は、 [CSingleLock:: Unlock](../../mfc/reference/csinglelock-class.md#unlock)のパラメーターとまったく同じです。 の2番目の形式 `Unlock` は、マルチロックの状況にはほとんど適用されません。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)
