---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
ms.openlocfilehash: ebfbc185cdca2effc96ce2e6d96d05f997c52bf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365972"
---
# <a name="csyncobject-class"></a>クラス

Win32 の同期オブジェクトに共通の機能を提供する純粋仮想クラスです。

## <a name="syntax"></a>構文

```
class CSyncObject : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[オブジェクトを同期します。](#csyncobject)|`CSyncObject` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ロックオブジェクト::ロック](#lock)|同期オブジェクトへのアクセス権を取得します。|
|[オブジェクトのロック解除](#unlock)|同期オブジェクトへのアクセス権を取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[ハンドルを操作します。](#operator_handle)|同期オブジェクトへのアクセスを提供します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[オブジェクト:m_hObject](#m_hobject)|基になる同期オブジェクトへのハンドル。|

## <a name="remarks"></a>解説

Microsoft Foundation クラス ライブラリには、`CSyncObject`から派生したクラスがいくつか用意されています。 これらは[、CEvent](../../mfc/reference/cevent-class.md) [、CMutex、CCriticalSection、](../../mfc/reference/cmutex-class.md)および[CSemaphore](../../mfc/reference/csemaphore-class.md)です。 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)

同期オブジェクトの使用方法については、「[マルチスレッド : 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

## <a name="csyncobjectcsyncobject"></a><a name="csyncobject"></a>オブジェクトを同期します。

指定された名前を持つ同期オブジェクトを構築します。

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
オブジェクトの名前。 NULL の場合 *、pstrName*は null になります。

## <a name="csyncobjectlock"></a><a name="lock"></a>ロックオブジェクト::ロック

同期オブジェクトによって制御されるリソースにアクセスするために、この関数を呼び出します。

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>パラメーター

*タイムアウト*<br/>
同期オブジェクトが使用可能 (シグナル状態) になるまで待機する時間をミリ秒単位で指定します。 INFINITE の`Lock`場合、オブジェクトがシグナル状態になるまで待機してから戻ります。

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

同期オブジェクトがシグナル状態になっている場合、`Lock`正常に返され、スレッドがオブジェクトを所有するようになりました。 同期オブジェクトが非シグナル状態 (使用不可)`Lock`の場合は *、dwTimeOut*パラメーターで指定されたミリ秒数まで同期オブジェクトがシグナル状態になるまで待機します。 同期オブジェクトが指定された時間内にシグナル状態にならなかった場合は、`Lock`失敗を返します。

## <a name="csyncobjectm_hobject"></a><a name="m_hobject"></a>オブジェクト:m_hObject

基になる同期オブジェクトへのハンドル。

```
HANDLE m_hObject;
```

## <a name="csyncobjectoperator-handle"></a><a name="operator_handle"></a>ハンドルを操作します。

この演算子を使用して、オブジェクトのハンドル`CSyncObject`を取得します。

```
operator HANDLE() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、同期オブジェクトのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

ハンドルを使用して、Windows API を直接呼び出すことができます。

## <a name="csyncobjectunlock"></a><a name="unlock"></a>オブジェクトのロック解除

パラメーターなしの`Unlock`宣言は純粋仮想関数であり、 から`CSyncObject`派生するすべてのクラスによってオーバーライドされる必要があります。

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>パラメーター

*Lcount*<br/>
既定の実装では使用されません。

*カウント*<br/>
既定の実装では使用されません。

### <a name="return-value"></a>戻り値

既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

2 つのパラメーターを持つ宣言の既定の実装は常に TRUE を返します。 この関数は、呼び出し元のスレッドが所有する同期オブジェクトへのアクセスを解放するために呼び出されます。 2 番目の宣言は、制御されたリソースの複数のアクセスを許可するセマフォなどの同期オブジェクトに対して提供されます。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
