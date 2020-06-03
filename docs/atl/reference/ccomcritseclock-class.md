---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
ms.openlocfilehash: 4b2ef093c1142b592ad2a6605a08bd8c34a643ea
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748075"
---
# <a name="ccomcritseclock-class"></a>クラス

このクラスには、クリティカル セクション オブジェクトをロックおよびロック解除するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>パラメーター

*トロック*<br/>
ロックおよびロック解除するオブジェクト。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クコムクリットセックロック::CComクリットセックロック](#ctor)|コンストラクターです。|
|[クコムクリットセックロック::~Cコムクリットセックロック](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クコムクリットセックロック::ロック](#lock)|クリティカル セクション オブジェクトをロックします。|
|[クコムクリットセックロック::ロック解除](#unlock)|クリティカル セクション オブジェクトのロックを解除します。|

## <a name="remarks"></a>解説

このクラスを使用して[、CComCriticalSection クラスまたは CComAutoCriticalSection](../../atl/reference/ccomcriticalsection-class.md)クラス[CComAutoCriticalSection Class](../../atl/reference/ccomautocriticalsection-class.md)よりも安全な方法でオブジェクトをロックおよびロック解除します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomcritseclockccomcritseclock"></a><a name="ctor"></a>クコムクリットセックロック::CComクリットセックロック

コンストラクターです。

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>パラメーター

*Cs*<br/>
クリティカル セクション オブジェクト。

*b イニシャルロック*<br/>
初期ロック状態: **true**はロックされていることを意味します。

### <a name="remarks"></a>解説

クリティカル セクション オブジェクトを初期化します。

## <a name="ccomcritseclockccomcritseclock"></a><a name="dtor"></a>クコムクリットセックロック::~Cコムクリットセックロック

デストラクターです。

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>解説

クリティカル セクション オブジェクトのロックを解除します。

## <a name="ccomcritseclocklock"></a><a name="lock"></a>クコムクリットセックロック::ロック

クリティカル セクション オブジェクトをロックします。

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが正常にロックされたかどうかS_OK、またはエラー HRESULT エラーが発生した場合に返します。

### <a name="remarks"></a>解説

オブジェクトが既にロックされている場合は、デバッグ ビルドで ASSERT エラーが発生します。

## <a name="ccomcritseclockunlock"></a><a name="unlock"></a>クコムクリットセックロック::ロック解除

クリティカル セクション オブジェクトのロックを解除します。

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>解説

オブジェクトが既にロック解除されている場合は、デバッグ ビルドで ASSERT エラーが発生します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomcriticalsection-class.md)<br/>
[クラスの自動変換クラス](../../atl/reference/ccomautocriticalsection-class.md)
