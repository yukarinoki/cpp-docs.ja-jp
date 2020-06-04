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
ms.openlocfilehash: a051c6a510c53ac0c7c0a6efd8b4b5720080b264
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319714"
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
|[コマルチロック::Cマルチロック](#cmultilock)|`CMultiLock` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コマルチロック::イズロック](#islocked)|アレイ内の特定の同期オブジェクトがロックされているかどうかを判断します。|
|[コマルチロック::ロック](#lock)|同期オブジェクトの配列を待機します。|
|[CMultiLock::ロック解除](#unlock)|所有している同期オブジェクトを解放します。|

## <a name="remarks"></a>解説

`CMultiLock`は基本クラスを持っていません。

同期クラス[CSemaphore](../../mfc/reference/csemaphore-class.md) [、CMutex](../../mfc/reference/cmutex-class.md)、[および CEvent](../../mfc/reference/cevent-class.md)を使用するには、`CMultiLock`同期オブジェクトを待機して解放するオブジェクトまたは[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトを作成します。 特定`CMultiLock`の時間に使用できる複数のオブジェクトがある場合に使用します。 一`CSingleLock`度に 1 つのオブジェクトだけを待つ必要がある場合に使用します。

オブジェクトを`CMultiLock`使用するには、まず待機する同期オブジェクトの配列を作成します。 次に、制御`CMultiLock`されたリソースのクラスのメンバー関数内でオブジェクトのコンストラクターを呼び出します。 次に[、Lock](#lock)メンバー関数を呼び出して、リソースが使用可能 (シグナル状態) であるかどうかを確認します。 1 つが含み場合は、メンバー関数の残りの部分を続行します。 リソースが使用可能な場合は、指定された時間待ってからリソースが解放されるまで待機するか、または失敗を返します。 リソースの使用が完了したら、オブジェクトを再使用[Unlock](#unlock)する場合は`CMultiLock`Unlock 関数を呼び出すか、オブジェクト`CMultiLock`を破棄できるようにします。

`CMultiLock`オブジェクトは、スレッドが応答できるオブジェクトの`CEvent`数が多い場合に最も便利です。 すべてのポインターを含む配列`CEvent`を作成し、`Lock`を呼び出します。 これにより、スレッドはイベントの 1 つがシグナル状態になるまで待機します。

オブジェクトの使用方法`CMultiLock`の詳細については、「[マルチスレッド : 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CMultiLock`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

## <a name="cmultilockcmultilock"></a><a name="cmultilock"></a>コマルチロック::Cマルチロック

`CMultiLock` オブジェクトを構築します。

```
CMultiLock(
    CSyncObject* ppObjects [ ],
    DWORD dwCount,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>パラメーター

*ppオブジェクト*<br/>
待機する同期オブジェクトへのポインターの配列。 Nll は指定できません。

*カウントカウント*<br/>
*ppObjects*内のオブジェクトの数。 1 以上であることが必要です。

*b イニシャルロック*<br/>
提供されたオブジェクトに最初にアクセスを試みるかどうかを指定します。

### <a name="remarks"></a>解説

この関数は、待機する同期オブジェクトの配列を作成した後に呼び出されます。 通常、スレッド内から呼び出され、同期オブジェクトの 1 つが使用可能になるのを待つ必要があります。

## <a name="cmultilockislocked"></a><a name="islocked"></a>コマルチロック::イズロック

指定したオブジェクトが非シグナル状態 (使用できない) かどうかを判断します。

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>パラメーター

*ドワークアイテム*<br/>
状態が照会されるオブジェクトに対応するオブジェクトの配列内のインデックス。

### <a name="return-value"></a>戻り値

指定したオブジェクトがロックされている場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cmultilocklock"></a><a name="lock"></a>コマルチロック::ロック

`CMultiLock`コンストラクターに指定された同期オブジェクトによって制御される 1 つ以上のリソースにアクセスします。

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>パラメーター

*を実行します。*<br/>
同期オブジェクトが使用可能になるまで待機する時間 (シグナル状態) を指定します。 INFINITE の`Lock`場合、オブジェクトがシグナル状態になるまで待機してから戻ります。

*すべてを待つ*<br/>
待機中のすべてのオブジェクトが、戻る前に同時にシグナル状態にする必要があるかどうかを指定します。 FALSE の`Lock`場合、待機中のオブジェクトのいずれかがシグナル状態になったときに戻ります。

*ドウウェイクマスク*<br/>
待機を中止できる他の条件を指定します。 このパラメーターで使用できるオプションの完全な一覧については、Windows SDK の[MsgWaitForMultiple オブジェクト](/windows/win32/api/winuser/nf-winuser-msgwaitformultipleobjects)を参照してください。

### <a name="return-value"></a>戻り値

失敗`Lock`した場合は、 - 1 を返します。 成功した場合は、次のいずれかの値を返します。

- WAIT_OBJECT_0とWAIT_OBJECT_0 + の間 (オブジェクトの数 - 1)

   *bWaitForAll*が TRUE の場合、すべてのオブジェクトがシグナル状態になります (使用可能)。 *bWaitForAll*が FALSE の場合、戻り値 - WAIT_OBJECT_0シグナルされるオブジェクトのオブジェクトの配列内のインデックス (使用可能) です。

- WAIT_OBJECT_0 + (オブジェクトの数)

   *dwWakeMask*で指定されたイベントは、スレッドの入力キューで使用できます。

- WAIT_ABANDONED_0とWAIT_ABANDONED_0 + の間 (オブジェクトの数 - 1)

   *bWaitForAll*が TRUE の場合、すべてのオブジェクトがシグナル状態になり、少なくとも 1 つのオブジェクトが放棄されたミューテックス オブジェクトです。 *bWaitForAll*が FALSE の場合、戻り値 - WAIT_ABANDONED_0は待機を満たす放棄されたミューテックス オブジェクトのオブジェクトの配列内のインデックスです。

- WAIT_TIMEOUT

   *dwTimeOut*で指定されたタイムアウト間隔が、待機が成功せずに期限切れになりました。

### <a name="remarks"></a>解説

*bWaitForAll*が TRUE`Lock`の場合、すべての同期オブジェクトが同時にシグナル状態になるとすぐに正常に戻ります。 *bWaitForAll*が FALSE`Lock`の場合、1 つ以上の同期オブジェクトがシグナル状態になるとすぐに戻ります。

すぐに`Lock`戻ることができない場合は *、dwTimeOut*パラメーターに指定されたミリ秒数を超えて待機してから戻ります。 *dwTimeOut*が INFINITE`Lock`の場合、オブジェクトへのアクセスが取得されるか *、dwWakeMask*で指定された条件が満たされるまでは戻りません。 それ以外の`Lock`場合、同期オブジェクトを取得できた場合は、正常に戻ります。失敗した場合は、失敗を返します。

## <a name="cmultilockunlock"></a><a name="unlock"></a>CMultiLock::ロック解除

が所有する同期オブジェクトを`CMultiLock`解放します。

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>パラメーター

*Lcount*<br/>
リリースする参照カウントの数。 1 以上であることが必要です。 指定した量がオブジェクトのカウントの最大値を超える場合、カウントは変更されず、関数は FALSE を返します。

*カウント*<br/>
同期オブジェクトの前のカウントを受け取る変数へのポイント。 NULL の場合、前のカウントは返されません。

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は's`CMultiLock`のデストラクタによって呼び出されます。

の最初の`Unlock`形式は、 によって`CMultiLock`管理される同期オブジェクトのロックを解除しようとします。 の 2`Unlock`番目の形式は`CSemaphore`、 が`CMultiLock`所有するオブジェクトのロックを解除しようとします。 ロック`CMultiLock`された`CSemaphore`オブジェクトを所有していない場合、関数は FALSE を返します。それ以外の場合は TRUE を返します。 *lCount*と*lpPrevCount*は[、CSingleLock::ロック解除](../../mfc/reference/csinglelock-class.md#unlock)のパラメーターとまったく同じです。 の 2`Unlock`番目の形式は、マルチロックの状況に適用されることはほとんどありません。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)
