---
title: CComFakeCriticalSection クラス
ms.date: 11/04/2016
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
ms.openlocfilehash: 5ada0fbed705af34391709653dbd3638fed32bf7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226582"
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection クラス

このクラスでは、 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)と同じメソッドが提供されますが、クリティカルセクションは提供されません。

## <a name="syntax"></a>構文

```
class CComFakeCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[CComFakeCriticalSection:: Init](#init)|クリティカルセクションがないため、何も実行しません。|
|[CComFakeCriticalSection:: Lock](#lock)|クリティカルセクションがないため、何も実行しません。|
|[CComFakeCriticalSection:: Term](#term)|クリティカルセクションがないため、何も実行しません。|
|[CComFakeCriticalSection:: Unlock](#unlock)|クリティカルセクションがないため、何も実行しません。|

## <a name="remarks"></a>解説

`CComFakeCriticalSection`[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)で見つかったメソッドをミラー化します。 ただし、 `CComFakeCriticalSection` はクリティカルセクションを提供しないため、メソッドは何も行いません。

通常は、名前を使用し `CComFakeCriticalSection` て **`typedef`** 、 `AutoCriticalSection` またはを使用し `CriticalSection` ます。 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)を使用する場合、これらの両方の **`typedef`** 名前が参照 `CComFakeCriticalSection` します。 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を使用する場合は、それぞれ[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)とを参照し `CComCriticalSection` ます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore .h

## <a name="ccomfakecriticalsectioninit"></a><a name="init"></a>CComFakeCriticalSection:: Init

クリティカルセクションがないため、何も実行しません。

```
HRESULT Init() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

## <a name="ccomfakecriticalsectionlock"></a><a name="lock"></a>CComFakeCriticalSection:: Lock

クリティカルセクションがないため、何も実行しません。

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

## <a name="ccomfakecriticalsectionterm"></a><a name="term"></a>CComFakeCriticalSection:: Term

クリティカルセクションがないため、何も実行しません。

```
HRESULT Term() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

## <a name="ccomfakecriticalsectionunlock"></a><a name="unlock"></a>CComFakeCriticalSection:: Unlock

クリティカルセクションがないため、何も実行しません。

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
