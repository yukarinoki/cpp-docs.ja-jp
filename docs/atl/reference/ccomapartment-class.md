---
title: コムアパートメント クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
ms.openlocfilehash: 13141d27592f6f40ea7b0529c61baba2fe83a10a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321119"
---
# <a name="ccomapartment-class"></a>コムアパートメント クラス

このクラスは、スレッド プールの EXE モジュールでアパートメントを管理するためのサポートを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CComApartment
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ココムアパートメント::ココムアパートメント](#ccomapartment)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ココムアパートメント:アパートメント](#apartment)|スレッドの開始アドレスをマークします。|
|[ココムアパートメント::ゲットロックカウント](#getlockcount)|スレッドの現在のロックカウントを返します。|
|[ココムアパートメント::ロック](#lock)|スレッドのロックカウントをインクリメントします。|
|[ココムアパートメント::ロック解除](#unlock)|スレッドのロックカウントを減算します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ココムアパートメント::m_dwThreadID](#m_dwthreadid)|スレッドの識別子を格納します。|
|[コムアパートメント::m_hThread](#m_hthread)|スレッドのハンドルを格納します。|
|[コムアパートメント:m_nLockCnt](#m_nlockcnt)|スレッドの現在のロックカウントが含まれます。|

## <a name="remarks"></a>解説

`CComApartment`は、スレッド プールの EXE モジュールでアパートメントを管理するために[使用](../../atl/reference/ccomautothreadmodule-class.md)されます。 `CComApartment`には、スレッドのロック数を増減するためのメソッドが用意されています。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomapartmentapartment"></a><a name="apartment"></a>ココムアパートメント:アパートメント

スレッドの開始アドレスをマークします。

```
DWORD Apartment();
```

### <a name="return-value"></a>戻り値

常に 0 です。

### <a name="remarks"></a>解説

[自動的](../../atl/reference/ccomautothreadmodule-class.md#init)に設定されます。

## <a name="ccomapartmentccomapartment"></a><a name="ccomapartment"></a>ココムアパートメント::ココムアパートメント

コンストラクターです。

```
CComApartment();
```

### <a name="remarks"></a>解説

データ メンバ`CComApartment`を[初期化m_nLockCnt](#m_nlockcnt)し[、](#m_hthread)m_hThread します。

## <a name="ccomapartmentgetlockcount"></a><a name="getlockcount"></a>ココムアパートメント::ゲットロックカウント

スレッドの現在のロックカウントを返します。

```
LONG GetLockCount();
```

### <a name="return-value"></a>戻り値

スレッドのロックカウント。

## <a name="ccomapartmentlock"></a><a name="lock"></a>ココムアパートメント::ロック

スレッドのロックカウントをインクリメントします。

```
LONG Lock();
```

### <a name="return-value"></a>戻り値

診断やテストに役立つ値。

### <a name="remarks"></a>解説

によって呼び出されます[。](../../atl/reference/ccomautothreadmodule-class.md#lock)

スレッドのロック・カウントは、統計目的で使用されます。

## <a name="ccomapartmentm_dwthreadid"></a><a name="m_dwthreadid"></a>ココムアパートメント::m_dwThreadID

スレッドの識別子を格納します。

```
DWORD m_dwThreadID;
```

## <a name="ccomapartmentm_hthread"></a><a name="m_hthread"></a>コムアパートメント::m_hThread

スレッドのハンドルを格納します。

```
HANDLE m_hThread;
```

## <a name="ccomapartmentm_nlockcnt"></a><a name="m_nlockcnt"></a>コムアパートメント:m_nLockCnt

スレッドの現在のロックカウントが含まれます。

```
LONG m_nLockCnt;
```

## <a name="ccomapartmentunlock"></a><a name="unlock"></a>ココムアパートメント::ロック解除

スレッドのロックカウントを減算します。

```
LONG Unlock();
```

### <a name="return-value"></a>戻り値

診断やテストに役立つ値。

### <a name="remarks"></a>解説

[によって](../../atl/reference/ccomautothreadmodule-class.md#lock)呼び出されます。

スレッドのロック・カウントは、統計目的で使用されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
