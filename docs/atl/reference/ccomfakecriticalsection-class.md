---
title: クラス
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
ms.openlocfilehash: 4a5b9ba3551397a9c3d59a343e9c6b55b1c1207e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327854"
---
# <a name="ccomfakecriticalsection-class"></a>クラス

このクラスは[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)と同じメソッドを提供しますが、クリティカル セクションは提供しません。

## <a name="syntax"></a>構文

```
class CComFakeCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ココムフェイククリティカルセクション::イニト](#init)|クリティカルセクションがないので何もしません。|
|[CComフェイククリティカルセクション::ロック](#lock)|クリティカルセクションがないので何もしません。|
|[CComフェイククリティカルセクション::用語](#term)|クリティカルセクションがないので何もしません。|
|[CComフェイククリティカルセクション::ロック解除](#unlock)|クリティカルセクションがないので何もしません。|

## <a name="remarks"></a>解説

`CComFakeCriticalSection`[は、CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)で見つかったメソッドをミラー化します。 ただし、`CComFakeCriticalSection`クリティカル セクションは提供されません。したがって、そのメソッドは何もしません。

通常`CComFakeCriticalSection`は、`typedef`名前`AutoCriticalSection`または を使用`CriticalSection`します。 [CCom シングルスレッドモデル](../../atl/reference/ccomsinglethreadmodel-class.md)または[CCom マルチスレッドモデルNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)を使用`typedef`する場合`CComFakeCriticalSection`、これらの名前の両方が参照されます。 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を使用する場合、それぞれ[CCom オートクリティカルセクション](../../atl/reference/ccomautocriticalsection-class.md)と`CComCriticalSection`を参照します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

## <a name="ccomfakecriticalsectioninit"></a><a name="init"></a>ココムフェイククリティカルセクション::イニト

クリティカルセクションがないので何もしません。

```
HRESULT Init() throw();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="ccomfakecriticalsectionlock"></a><a name="lock"></a>CComフェイククリティカルセクション::ロック

クリティカルセクションがないので何もしません。

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="ccomfakecriticalsectionterm"></a><a name="term"></a>CComフェイククリティカルセクション::用語

クリティカルセクションがないので何もしません。

```
HRESULT Term() throw();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="ccomfakecriticalsectionunlock"></a><a name="unlock"></a>CComフェイククリティカルセクション::ロック解除

クリティカルセクションがないので何もしません。

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
