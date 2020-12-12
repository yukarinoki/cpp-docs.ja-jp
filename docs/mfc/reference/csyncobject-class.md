---
description: '詳細情報: CSyncObject クラス'
title: CSyncObject クラス
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
ms.openlocfilehash: 5743f632f9a8c482ac15995e8d2429851ba015d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318599"
---
# <a name="csyncobject-class"></a>CSyncObject クラス

Win32 の同期オブジェクトに共通の機能を提供する純粋仮想クラスです。

## <a name="syntax"></a>構文

```
class CSyncObject : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSyncObject::CSyncObject](#csyncobject)|`CSyncObject` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSyncObject:: Lock](#lock)|同期オブジェクトへのアクセスを取得します。|
|[CSyncObject:: Unlock](#unlock)|同期オブジェクトへのアクセスを取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CSyncObject:: operator ハンドル](#operator_handle)|同期オブジェクトへのアクセスを提供します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CSyncObject:: m_hObject](#m_hobject)|基になる同期オブジェクトへのハンドル。|

## <a name="remarks"></a>解説

Microsoft Foundation Class ライブラリには、から派生した複数のクラスが用意されて `CSyncObject` います。 これらは、 [CEvent](../../mfc/reference/cevent-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)、および [CSemaphore](../../mfc/reference/csemaphore-class.md)です。

同期オブジェクトの使用方法の詳細については、「 [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>要件

**ヘッダー:** afxmt

## <a name="csyncobjectcsyncobject"></a><a name="csyncobject"></a> CSyncObject::CSyncObject

指定された名前を使用して同期オブジェクトを構築します。

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>パラメーター

*pstrName*<br/>
オブジェクトの名前。 NULL の場合、 *Pstrname* は null になります。

## <a name="csyncobjectlock"></a><a name="lock"></a> CSyncObject:: Lock

同期オブジェクトによって制御されるリソースにアクセスするには、この関数を呼び出します。

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>パラメーター

*dwTimeout*<br/>
同期オブジェクトが使用可能になるまでの待機時間をミリ秒単位で指定します (シグナル状態)。 無限の場合、 `Lock` はオブジェクトがシグナル状態になるまで待機してから制御を戻します。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

同期オブジェクトがシグナル状態になる `Lock` と、は正常に戻り、スレッドはオブジェクトを所有するようになります。 同期オブジェクトが非シグナル状態 (利用不可) の場合、 `Lock` は、同期オブジェクトが *dwTimeOut* パラメーターで指定されたミリ秒数までシグナル状態になるのを待機します。 指定された時間内に同期オブジェクトがシグナル状態にならなかった場合、は `Lock` 失敗を返します。

## <a name="csyncobjectm_hobject"></a><a name="m_hobject"></a> CSyncObject:: m_hObject

基になる同期オブジェクトへのハンドル。

```
HANDLE m_hObject;
```

## <a name="csyncobjectoperator-handle"></a><a name="operator_handle"></a> CSyncObject:: operator ハンドル

オブジェクトのハンドルを取得するには、この演算子を使用し `CSyncObject` ます。

```
operator HANDLE() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、同期オブジェクトのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

ハンドルを使用すると、Windows Api を直接呼び出すことができます。

## <a name="csyncobjectunlock"></a><a name="unlock"></a> CSyncObject:: Unlock

パラメーターを指定しないの宣言 `Unlock` は純粋仮想関数であり、から派生するすべてのクラスでオーバーライドする必要があり `CSyncObject` ます。

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>パラメーター

*lCount*<br/>
既定の実装では使用されません。

*lpPrevCount*<br/>
既定の実装では使用されません。

### <a name="return-value"></a>戻り値

既定の実装では、常に TRUE が返されます。

### <a name="remarks"></a>解説

2つのパラメーターを持つ宣言の既定の実装では、常に TRUE が返されます。 この関数は、呼び出し元のスレッドが所有する同期オブジェクトへのアクセスを解放するために呼び出されます。 2つ目の宣言は、制御されたリソースへの複数のアクセスを許可するセマフォなどの同期オブジェクトに対して提供されます。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
