---
description: '詳細情報: CSingleLock クラス'
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
ms.openlocfilehash: 7fa4fe32ce38bf47ede1b6ac133d1a057907f9c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342857"
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
|[CSingleLock:: CSingleLock](#csinglelock)|`CSingleLock` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSingleLock:: IsLocked](#islocked)|オブジェクトがロックされているかどうかを判断します。|
|[CSingleLock:: Lock](#lock)|同期オブジェクトを待機します。|
|[CSingleLock:: Unlock](#unlock)|同期オブジェクトを解放します。|

## <a name="remarks"></a>解説

`CSingleLock` に基底クラスがありません。

同期クラス [CSemaphore](../../mfc/reference/csemaphore-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)、および [CEvent](../../mfc/reference/cevent-class.md)を使用するに `CSingleLock` は、または [CMultiLock](../../mfc/reference/cmultilock-class.md) オブジェクトを作成して、同期オブジェクトを待機して解放する必要があります。 一度 `CSingleLock` に1つのオブジェクトだけを待機する必要がある場合に使用します。 `CMultiLock`特定の時刻に使用できる複数のオブジェクトがある場合は、を使用します。

オブジェクトを使用するには、制御された `CSingleLock` リソースのクラスのメンバー関数内でコンストラクターを呼び出します。 次に、 [Islocked](#islocked) メンバー関数を呼び出して、リソースが使用可能かどうかを確認します。 そのような場合は、メンバー関数の残りの部分を続行します。 リソースが使用できない場合は、リソースが解放されるまで、指定された時間待機するか、失敗を返します。 リソースの使用が完了したら、オブジェクトを再度使用する場合は [Unlock](#unlock) 関数を呼び出し、 `CSingleLock` オブジェクトの破棄を許可し `CSingleLock` ます。

`CSingleLock` オブジェクトでは、 [CSyncObject](../../mfc/reference/csyncobject-class.md)から派生したオブジェクトが存在する必要があります。 これは、通常、制御されたリソースのクラスのデータメンバーです。 オブジェクトの使用方法の詳細については、 `CSingleLock` 「 [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CSingleLock`

## <a name="requirements"></a>要件

**ヘッダー:** afxmt

## <a name="csinglelockcsinglelock"></a><a name="csinglelock"></a> CSingleLock:: CSingleLock

`CSingleLock` オブジェクトを構築します。

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>パラメーター

*pObject*<br/>
アクセスする同期オブジェクトを指します。 Nll は指定できません。

*bInitialLock*<br/>
指定されたオブジェクトに最初にアクセスを試みるかどうかを指定します。

### <a name="remarks"></a>解説

この関数は、通常、制御されたリソースのアクセスメンバー関数内から呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

## <a name="csinglelockislocked"></a><a name="islocked"></a> CSingleLock:: IsLocked

オブジェクトに関連付けられたオブジェクト `CSingleLock` が非シグナル状態 (利用不可) かどうかを判断します。

```
BOOL IsLocked();
```

### <a name="return-value"></a>戻り値

オブジェクトがロックされている場合は0以外の。それ以外の場合は0です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

## <a name="csinglelocklock"></a><a name="lock"></a> CSingleLock:: Lock

コンストラクターに渡された同期オブジェクトによって制御されるリソースへのアクセスを取得するには、この関数を呼び出し `CSingleLock` ます。

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>パラメーター

*dwTimeOut*<br/>
同期オブジェクトが使用可能になるまで待機する時間を指定します (シグナル状態)。 無限の場合、 `Lock` はオブジェクトがシグナル状態になるまで待機してから制御を戻します。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

同期オブジェクトがシグナル状態になる `Lock` と、は正常に戻り、スレッドはオブジェクトを所有するようになります。 同期オブジェクトが非シグナル状態 (利用不可) の場合、 `Lock` は、同期オブジェクトが *dwTimeOut* パラメーターで指定されたミリ秒数までシグナル状態になるのを待機します。 指定された時間内に同期オブジェクトがシグナル状態にならなかった場合、は `Lock` 失敗を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="csinglelockunlock"></a><a name="unlock"></a> CSingleLock:: Unlock

によって所有されている同期オブジェクトを解放 `CSingleLock` します。

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>パラメーター

*lCount*<br/>
解放するアクセスの数。 1 以上であることが必要です。 指定された量が原因でオブジェクトのカウントが最大値を超えた場合、カウントは変更されず、関数は FALSE を返します。

*lPrevCount*<br/>
は、同期オブジェクトの前のカウントを受け取る変数を指します。 NULL の場合、前のカウントは返されません。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、のデストラクターによって呼び出され `CSingleLock` ます。

セマフォのアクセスカウントを複数解放する必要がある場合は、2番目の形式のを使用 `Unlock` して、解放するアクセスの数を指定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CMultiLock クラス](../../mfc/reference/cmultilock-class.md)
