---
title: クラスの自動変換クラス
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 8cbf08082fd24ef2cf0e8794e2944a799baec084
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321090"
---
# <a name="ccomautocriticalsection-class"></a>クラスの自動変換クラス

`CComAutoCriticalSection`には、クリティカル セクション オブジェクトの所有権を取得および解放するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComオートクリティカルセクション::CComオートクリティカルセクション](#ccomautocriticalsection)|コンストラクターです。|
|[CComオートクリティカルセクション::~CComオートクリティカルセクション](#dtor)|デストラクターです。|

## <a name="remarks"></a>解説

`CComAutoCriticalSection`[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)クラスに似ていますが`CComAutoCriticalSection`、コンストラクター内のクリティカル セクション オブジェクトを自動的に初期化します。

通常は`CComAutoCriticalSection`[、"自動クリティカルセクション](ccommultithreadmodel-class.md#autocriticalsection)" という名前で`typedef`使用します。 この名前は`CComAutoCriticalSection`[、CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)が使用されている場合に参照されます。

この`Init`クラス`Term`を使用する場合[、CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)の メソッドとメソッドは使用できません。

## <a name="inheritance-hierarchy"></a>継承階層

[ココムクリティカルセクション](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a>CComオートクリティカルセクション::CComオートクリティカルセクション

コンストラクターです。

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>解説

Win32 関数[InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)を呼び出し、クリティカル セクション オブジェクトを初期化します。

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a>CComオートクリティカルセクション::~CComオートクリティカルセクション

デストラクターです。

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>解説

デストラクターは、クリティカル セクション オブジェクトによって使用されるすべてのシステム リソースを解放する[DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)を呼び出します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラス](../../atl/reference/ccomcriticalsection-class.md)
