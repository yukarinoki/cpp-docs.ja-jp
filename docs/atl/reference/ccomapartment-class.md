---
title: CComApartment クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
dev_langs:
- C++
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39750bcb6b8852e692e52f163e83bb815ecebe97
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755438"
---
# <a name="ccomapartment-class"></a>CComApartment クラス

このクラスは、アパートメント スレッド プールの EXE モジュールでの管理のサポートを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CComApartment
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComApartment::CComApartment](#ccomapartment)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComApartment::Apartment](#apartment)|スレッドの開始アドレスをマークします。|
|[CComApartment::GetLockCount](#getlockcount)|スレッドの現在のロック カウントを返します。|
|[CComApartment::Lock](#lock)|スレッドのロック カウントをインクリメントします。|
|[CComApartment::Unlock](#unlock)|スレッドのロック カウントをデクリメントします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComApartment::m_dwThreadID](#m_dwthreadid)|スレッドの識別子が含まれています。|
|[CComApartment::m_hThread](#m_hthread)|スレッドのハンドルが含まれています。|
|[CComApartment::m_nLockCnt](#m_nlockcnt)|スレッドの現在のロック カウントが含まれています。|

## <a name="remarks"></a>Remarks

`CComApartment` 使って[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)アパートメントにスレッド プールの EXE モジュールを管理します。 `CComApartment` インクリメントおよびデクリメント、ロックのメソッドは、スレッドではカウントを提供します。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase.h

##  <a name="apartment"></a>  CComApartment::Apartment

スレッドの開始アドレスをマークします。

```
DWORD Apartment();
```

### <a name="return-value"></a>戻り値

常に 0 です。

### <a name="remarks"></a>Remarks

中に自動的に設定[CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init)します。

##  <a name="ccomapartment"></a>  CComApartment::CComApartment

コンストラクターです。

```
CComApartment();
```

### <a name="remarks"></a>Remarks

初期化します、`CComApartment`データ メンバー [m_nLockCnt](#m_nlockcnt)と[で](#m_hthread)します。

##  <a name="getlockcount"></a>  CComApartment::GetLockCount

スレッドの現在のロック カウントを返します。

```
LONG GetLockCount();
```

### <a name="return-value"></a>戻り値

スレッドのロック カウントします。

##  <a name="lock"></a>  CComApartment::Lock

スレッドのロック カウントをインクリメントします。

```
LONG Lock();
```

### <a name="return-value"></a>戻り値

テストや診断に使用する値。

### <a name="remarks"></a>Remarks

によって呼び出される[CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)します。

スレッドのロック カウントは、統計的な目的で使用されます。

##  <a name="m_dwthreadid"></a>  CComApartment::m_dwThreadID

スレッドの識別子が含まれています。

```
DWORD m_dwThreadID;
```

##  <a name="m_hthread"></a>  CComApartment::m_hThread

スレッドのハンドルが含まれています。

```
HANDLE m_hThread;
```

##  <a name="m_nlockcnt"></a>  CComApartment::m_nLockCnt

スレッドの現在のロック カウントが含まれています。

```
LONG m_nLockCnt;
```

##  <a name="unlock"></a>  CComApartment::Unlock

スレッドのロック カウントをデクリメントします。

```
LONG Unlock();
```

### <a name="return-value"></a>戻り値

テストや診断に使用する値。

### <a name="remarks"></a>Remarks

によって呼び出される[CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock)します。

スレッドのロック カウントは、統計的な目的で使用されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
