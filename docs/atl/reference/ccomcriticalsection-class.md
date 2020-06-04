---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
ms.openlocfilehash: f3991d217fbc201bd428ed2522a5c4c25e074928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327964"
---
# <a name="ccomcriticalsection-class"></a>クラス

このクラスには、クリティカル セクション オブジェクトの所有権を取得および解放するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CComCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ココムクリティカルセクション::CComクリティカルセクション](#ccomcriticalsection)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ココムクリティカルセクション::イニト](#init)|クリティカル セクション オブジェクトを作成および初期化します。|
|[ココムクリティカルセクション::ロック](#lock)|クリティカル セクション オブジェクトの所有権を取得します。|
|[ココムクリティカルセクション::用語](#term)|クリティカル セクション オブジェクトによって使用されるシステム リソースを解放します。|
|[コムクリティカルセクション::ロック解除](#unlock)|クリティカル セクション オブジェクトの所有権を解放します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ココムクリティカルセクション::m_sec](#m_sec)|CRITICAL_SECTIONオブジェクト。|

## <a name="remarks"></a>解説

`CComCriticalSection`クラス[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)に似ていますが、クリティカル セクションを明示的に初期化して解放する必要がある点が異なっています。

通常は`CComCriticalSection`**、typedef**名の[CriticalSection](ccommultithreadmodel-class.md#criticalsection)を使用します。 この名前は`CComCriticalSection`[、CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)が使用されている場合に参照されます。

このクラスを直接呼び出す`Lock`よりも安全に使用するには`Unlock`[、CComCritSecLock クラス](../../atl/reference/ccomcritseclock-class.md)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

## <a name="ccomcriticalsectionccomcriticalsection"></a><a name="ccomcriticalsection"></a>ココムクリティカルセクション::CComクリティカルセクション

コンストラクターです。

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>解説

m_secデータ[m_sec](#m_sec)メンバーを NULL に設定します。

## <a name="ccomcriticalsectioninit"></a><a name="init"></a>ココムクリティカルセクション::イニト

m_sec[データ](#m_sec)メンバーに含まれるクリティカル セクション オブジェクトを初期化する Win32 関数[InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)を呼び出します。

```
HRESULT Init() throw();
```

### <a name="return-value"></a>戻り値

成功、E_OUTOFMEMORY、または失敗時のE_FAILにS_OKを返します。

## <a name="ccomcriticalsectionlock"></a><a name="lock"></a>ココムクリティカルセクション::ロック

M_sec[データ](#m_sec)メンバーに含まれるクリティカル セクション オブジェクトの所有権をスレッドが取得できるまで待機する Win32 関数[EnterCriticalSection](/windows/win32/api/synchapi/nf-synchapi-entercriticalsection)を呼び出します。

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>戻り値

成功、E_OUTOFMEMORY、または失敗時のE_FAILにS_OKを返します。

### <a name="remarks"></a>解説

クリティカル セクション オブジェクトは、まず[Init](#init)メソッドの呼び出しで初期化する必要があります。 保護されたコードの実行が終了したら、スレッドは[ロック解除](#unlock)を呼び出してクリティカル セクションの所有権を解放する必要があります。

## <a name="ccomcriticalsectionm_sec"></a><a name="m_sec"></a>ココムクリティカルセクション::m_sec

すべての`CComCriticalSection`メソッドで使用されるクリティカル セクション オブジェクトを含みます。

```
CRITICAL_SECTION m_sec;
```

## <a name="ccomcriticalsectionterm"></a><a name="term"></a>ココムクリティカルセクション::用語

m_sec[データ](#m_sec)メンバーに含まれるクリティカル セクション オブジェクトによって使用されるすべてのリソースを解放する Win32 関数[DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)を呼び出します。

```
HRESULT Term() throw();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

いったん`Term`呼び出されると、クリティカル セクションは同期に使用できなくなります。

## <a name="ccomcriticalsectionunlock"></a><a name="unlock"></a>コムクリティカルセクション::ロック解除

m_sec[データ](#m_sec)メンバーに含まれるクリティカル セクション オブジェクトの所有権を解放する Win32 関数[LeaveCriticalSection](/windows/win32/api/synchapi/nf-synchapi-leavecriticalsection)を呼び出します。

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

所有権を取得するには、スレッドが[Lock](#lock)メソッドを呼び出す必要があります。 各呼び`Lock`出しは、クリティカル`Unlock`セクションの所有権を解放するために、対応する呼び出しが必要です。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラス](../../atl/reference/ccomcritseclock-class.md)
