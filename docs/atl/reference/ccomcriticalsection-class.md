---
title: CComCriticalSection クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4678acbe251086f3a42e3544e155a191a5847f11
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101398"
---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection クラス

このクラスは、取得およびクリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
class CComCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComCriticalSection::Init](#init)|作成し、クリティカル セクション オブジェクトを初期化します。|
|[CComCriticalSection::Lock](#lock)|クリティカル セクション オブジェクトの所有権を取得します。|
|[CComCriticalSection::Term](#term)|クリティカル セクション オブジェクトによって使用されるシステム リソースを解放します。|
|[CComCriticalSection::Unlock](#unlock)|クリティカル セクション オブジェクトの所有権を解放します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComCriticalSection::m_sec](#m_sec)|CRITICAL_SECTION オブジェクト。|

## <a name="remarks"></a>Remarks

`CComCriticalSection` クラスに似ていますが[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), 点が明示的に初期化し、クリティカル セクションを解放する必要があります。

通常、使用して`CComCriticalSection`を通じて、 **typedef**名前[CriticalSection](ccommultithreadmodel-class.md#criticalsection)します。 この名前の参照`CComCriticalSection`とき[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)が使用されています。  

参照してください[CComCritSecLock クラス](../../atl/reference/ccomcritseclock-class.md)呼び出すよりもこのクラスを使用するより安全な方法を`Lock`と`Unlock`直接します。

## <a name="requirements"></a>要件

**ヘッダー:** atlcore.h

##  <a name="ccomcriticalsection"></a>  CComCriticalSection::CComCriticalSection

コンストラクターです。

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>Remarks

セット、 [m_sec](#m_sec)データ メンバーを NULL にします。

##  <a name="init"></a>  CComCriticalSection::Init

Win32 関数を呼び出す[InitializeCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsection)に含まれるクリティカル セクション オブジェクトを初期化しますが、 [m_sec](#m_sec)データ メンバー。

```
HRESULT Init() throw();
```

### <a name="return-value"></a>戻り値

成功した場合、E_OUTOFMEMORY または E_FAIL エラー発生時に、S_OK を返します。

##  <a name="lock"></a>  CComCriticalSection::Lock

Win32 関数を呼び出す[EnterCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-entercriticalsection)、どの待機スレッドがクリティカル セクション オブジェクトに含まれているの所有権を取得できるまで、 [m_sec](#m_sec)データ メンバー。

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>戻り値

成功した場合、E_OUTOFMEMORY または E_FAIL エラー発生時に、S_OK を返します。

### <a name="remarks"></a>Remarks

呼び出して、クリティカル セクション オブジェクトを初期化まず必要があります、 [Init](#init)メソッド。 保護されたコードの実行が完了すると、スレッドで呼び出す必要があります[Unlock](#unlock)クリティカル セクションの所有権を解放します。

##  <a name="m_sec"></a>  CComCriticalSection::m_sec

すべてで使用されるクリティカル セクション オブジェクトを含む`CComCriticalSection`メソッド。

```
CRITICAL_SECTION m_sec;
```

##  <a name="term"></a>  CComCriticalSection::Term

Win32 関数を呼び出す[DeleteCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-deletecriticalsection)に含まれているクリティカル セクション オブジェクトによって使用されるすべてのリソースを解放する、 [m_sec](#m_sec)データ メンバー。

```
HRESULT Term() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>Remarks

1 回`Term`が呼び出されると、重要なセクションは、同期は使用できなくします。

##  <a name="unlock"></a>  CComCriticalSection::Unlock

Win32 関数を呼び出す[により](/windows/desktop/api/synchapi/nf-synchapi-leavecriticalsection)に含まれるクリティカル セクション オブジェクトの所有権を解放する、 [m_sec](#m_sec)データ メンバー。

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>Remarks

所有権を取得するスレッドを呼び出す必要があります、[ロック](#lock)メソッド。 呼び出しごとに`Lock`に対応する呼び出しを必要と`Unlock`クリティカル セクションの所有権を解放します。

## <a name="see-also"></a>関連項目

[CComFakeCriticalSection クラス](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComCritSecLock クラス](../../atl/reference/ccomcritseclock-class.md)
