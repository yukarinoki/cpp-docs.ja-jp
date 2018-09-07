---
title: CComFakeCriticalSection クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48b120b7be3e605b6ed2619cbd71011b0a693bdc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757277"
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection クラス

このクラスと同じメソッドを提供する[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)クリティカル セクションは提供されません。

## <a name="syntax"></a>構文

```
class CComFakeCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComFakeCriticalSection::Init](#init)|クリティカル セクションがないためには何も行いません。|
|[CComFakeCriticalSection::Lock](#lock)|クリティカル セクションがないためには何も行いません。|
|[CComFakeCriticalSection::Term](#term)|クリティカル セクションがないためには何も行いません。|
|[CComFakeCriticalSection::Unlock](#unlock)|クリティカル セクションがないためには何も行いません。|

## <a name="remarks"></a>Remarks

`CComFakeCriticalSection` 内のメソッドをミラー化[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)します。 ただし、`CComFakeCriticalSection`に重要なセクションは示しません。 そのため、そのメソッドが何もしません。

通常、使用して`CComFakeCriticalSection`を通じて、`typedef`名か、`AutoCriticalSection`または`CriticalSection`します。 使用する場合[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)、これらの両方の`typedef`名前参照`CComFakeCriticalSection`します。 使用する場合[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を参照する[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)と`CComCriticalSection`、それぞれします。

## <a name="requirements"></a>要件

**ヘッダー:** atlcore.h

##  <a name="init"></a>  CComFakeCriticalSection::Init

クリティカル セクションがないためには何も行いません。

```
HRESULT Init() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

##  <a name="lock"></a>  CComFakeCriticalSection::Lock

クリティカル セクションがないためには何も行いません。

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

##  <a name="term"></a>  CComFakeCriticalSection::Term

クリティカル セクションがないためには何も行いません。

```
HRESULT Term() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

##  <a name="unlock"></a>  CComFakeCriticalSection::Unlock

クリティカル セクションがないためには何も行いません。

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>戻り値

S_OK を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
