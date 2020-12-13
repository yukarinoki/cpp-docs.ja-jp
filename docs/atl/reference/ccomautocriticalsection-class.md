---
description: '詳細情報: CComAutoCriticalSection クラス'
title: CComAutoCriticalSection クラス
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 2441c714b95a3bbefed4a699055d14c6915cffda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146966"
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection クラス

`CComAutoCriticalSection` クリティカルセクションオブジェクトの所有権を取得および解放するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|コンストラクターです。|
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|デストラクターです。|

## <a name="remarks"></a>解説

`CComAutoCriticalSection` はクラス [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)に似てい `CComAutoCriticalSection` ますが、コンストラクターでクリティカルセクションオブジェクトが自動的に初期化される点が異なります。

通常は、AutoCriticalSection という名前を使用し `CComAutoCriticalSection` **`typedef`** ます。 [](ccommultithreadmodel-class.md#autocriticalsection) この名前 `CComAutoCriticalSection` は、 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) が使用されている場合に参照されます。

`Init` `Term` このクラスを使用する場合、 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)のメソッドとメソッドは使用できません。

## <a name="inheritance-hierarchy"></a>継承階層

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>要件

**ヘッダー:** atlcore .h

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a> CComAutoCriticalSection::CComAutoCriticalSection

コンストラクターです。

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>解説

クリティカルセクションオブジェクトを初期化する Win32 関数 [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)を呼び出します。

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a> CComAutoCriticalSection:: ~ CComAutoCriticalSection

デストラクターです。

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>解説

このデストラクターは [DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)を呼び出します。これにより、クリティカルセクションオブジェクトによって使用されるすべてのシステムリソースが解放されます。

## <a name="see-also"></a>関連項目

[CComFakeCriticalSection クラス](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)
