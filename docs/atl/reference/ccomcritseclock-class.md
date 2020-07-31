---
title: CComCritSecLock クラス
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
ms.openlocfilehash: fd2904f67d84db42d6b35aa4e505b063d6ea9a9f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224293"
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock クラス

このクラスには、クリティカルセクションオブジェクトをロックおよびロック解除するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>パラメーター

*TLock*<br/>
ロックおよびロック解除するオブジェクト。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[CComCritSecLock::CComCritSecLock](#ctor)|コンストラクターです。|
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[CComCritSecLock:: Lock](#lock)|クリティカルセクションオブジェクトをロックするには、このメソッドを呼び出します。|
|[CComCritSecLock:: Unlock](#unlock)|クリティカルセクションオブジェクトのロックを解除するには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

このクラスを使用して、 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)または[CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)よりも安全な方法でオブジェクトをロックおよびロック解除します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="ccomcritseclockccomcritseclock"></a><a name="ctor"></a>CComCritSecLock::CComCritSecLock

コンストラクターです。

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>パラメーター

*同時*<br/>
クリティカルセクションオブジェクト。

*bInitialLock*<br/>
初期ロック状態: ロックされている **`true`** ことを意味します。

### <a name="remarks"></a>解説

クリティカルセクションオブジェクトを初期化します。

## <a name="ccomcritseclockccomcritseclock"></a><a name="dtor"></a>CComCritSecLock:: ~ CComCritSecLock

デストラクターです。

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>解説

クリティカルセクションオブジェクトのロックを解除します。

## <a name="ccomcritseclocklock"></a><a name="lock"></a>CComCritSecLock:: Lock

クリティカルセクションオブジェクトをロックするには、このメソッドを呼び出します。

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが正常にロックされている場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

オブジェクトが既にロックされている場合は、デバッグビルドでアサートエラーが発生します。

## <a name="ccomcritseclockunlock"></a><a name="unlock"></a>CComCritSecLock:: Unlock

クリティカルセクションオブジェクトのロックを解除するには、このメソッドを呼び出します。

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>解説

オブジェクトが既にロック解除されている場合は、デバッグビルドでアサートエラーが発生します。

## <a name="see-also"></a>関連項目

[CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)<br/>
[CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)
