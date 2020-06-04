---
title: CSingleLock クラス
ms.date: 11/04/2016
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
ms.openlocfilehash: 231397228d94e58665602453b5d377571e24a967
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318272"
---
# <a name="csinglelock-class"></a>CSingleLock クラス

マルチスレッド プログラムで 1 つのリソースのアクセス制御に使うアクセス コントロール機構を表します。

## <a name="syntax"></a>構文

```
class CSingleLock
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cシングルロック::Cシングルロック](#csinglelock)|`CSingleLock` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cシングルロック::イズロック](#islocked)|オブジェクトがロックされているかどうかを判断します。|
|[シングルロック::ロック](#lock)|同期オブジェクトを待機します。|
|[Cシングルロック::ロック解除](#unlock)|同期オブジェクトを解放します。|

## <a name="remarks"></a>解説

`CSingleLock`は基本クラスを持っていません。

同期クラス[CSemaphore](../../mfc/reference/csemaphore-class.md) [、CMutex](../../mfc/reference/cmutex-class.md) [、CCriticalSection](../../mfc/reference/ccriticalsection-class.md)、および[CEvent](../../mfc/reference/cevent-class.md)を使用するには、同期`CSingleLock`オブジェクトを待機して解放する[CMultiLock](../../mfc/reference/cmultilock-class.md)オブジェクトを作成する必要があります。 一`CSingleLock`度に 1 つのオブジェクトだけを待つ必要がある場合に使用します。 特定`CMultiLock`の時間に使用できる複数のオブジェクトがある場合に使用します。

オブジェクトを`CSingleLock`使用するには、制御されたリソースのクラスのメンバー関数内でコンストラクターを呼び出します。 次に[、IsLocked](#islocked)メンバー関数を呼び出して、リソースが使用可能かどうかを確認します。 メンバー関数の残りの部分を続行します。 リソースが使用できない場合は、リソースが解放されるまで指定された時間待機するか、またはエラーを返します。 リソースの使用が完了したら、`CSingleLock`オブジェクトを再使用する場合は[Unlock](#unlock)関数を呼び出すか、オブジェクト`CSingleLock`を破棄できるようにします。

`CSingleLock`オブジェクトは[、CSyncObject](../../mfc/reference/csyncobject-class.md)から派生したオブジェクトが存在する必要があります。 通常、これは制御されたリソースのクラスのデータ メンバーです。 オブジェクトの使用方法`CSingleLock`の詳細については、「[マルチスレッド : 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CSingleLock`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

## <a name="csinglelockcsinglelock"></a><a name="csinglelock"></a>Cシングルロック::Cシングルロック

`CSingleLock` オブジェクトを構築します。

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>パラメーター

*pObject*<br/>
アクセスする同期オブジェクトへのポイント。 Nll は指定できません。

*b イニシャルロック*<br/>
指定されたオブジェクトに最初にアクセスを試みるかどうかを指定します。

### <a name="remarks"></a>解説

この関数は、通常、制御されたリソースのアクセス メンバー関数内から呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

## <a name="csinglelockislocked"></a><a name="islocked"></a>Cシングルロック::イズロック

オブジェクトに関連付けられているオブジェクトが`CSingleLock`非シグナル状態 (使用不可) であるかどうかを判断します。

```
BOOL IsLocked();
```

### <a name="return-value"></a>戻り値

オブジェクトがロックされている場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

## <a name="csinglelocklock"></a><a name="lock"></a>シングルロック::ロック

`CSingleLock`コンストラクターに指定された同期オブジェクトによって制御されるリソースにアクセスします。

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>パラメーター

*を実行します。*<br/>
同期オブジェクトが使用可能になるまで待機する時間 (シグナル状態) を指定します。 INFINITE の`Lock`場合、オブジェクトがシグナル状態になるまで待機してから戻ります。

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

同期オブジェクトがシグナル状態になっている場合、`Lock`正常に返され、スレッドがオブジェクトを所有するようになりました。 同期オブジェクトが非シグナル状態 (使用不可)`Lock`の場合は *、dwTimeOut*パラメーターで指定されたミリ秒数まで同期オブジェクトがシグナル状態になるまで待機します。 同期オブジェクトが指定された時間内にシグナル状態にならなかった場合は、`Lock`失敗を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="csinglelockunlock"></a><a name="unlock"></a>Cシングルロック::ロック解除

が所有する同期オブジェクトを`CSingleLock`解放します。

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>パラメーター

*Lcount*<br/>
リリースするアクセス数。 1 以上であることが必要です。 指定した量がオブジェクトのカウントの最大値を超える場合、カウントは変更されず、関数は FALSE を返します。

*カウント*<br/>
同期オブジェクトの以前のカウントを受け取る変数へのポイント。 NULL の場合、前のカウントは返されません。

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は's`CSingleLock`のデストラクタによって呼び出されます。

セマフォの複数のアクセスカウントを解放する必要がある場合は、2 番目の`Unlock`形式を使用し、解放するアクセス数を指定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CMultiLock クラス](../../mfc/reference/cmultilock-class.md)
