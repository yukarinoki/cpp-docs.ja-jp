---
description: '詳細情報: CComSafeDeleteCriticalSection クラス'
title: CComSafeDeleteCriticalSection クラス
ms.date: 11/04/2016
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
ms.openlocfilehash: 73e27fb267cbfc8cde248c7ac896d29de2a91f77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142170"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection クラス

このクラスには、クリティカルセクションオブジェクトの所有権を取得および解放するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|コンストラクターです。|
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComSafeDeleteCriticalSection:: Init](#init)|クリティカルセクションオブジェクトを作成し、初期化します。|
|[CComSafeDeleteCriticalSection:: Lock](#lock)|クリティカルセクションオブジェクトの所有権を取得します。|
|[CComSafeDeleteCriticalSection:: Term](#term)|クリティカルセクションオブジェクトによって使用されているシステムリソースを解放します。|

### <a name="data-members"></a>データ メンバー

|データ メンバー|説明|
|-|-|
|[m_bInitialized](#m_binitialized)|内部オブジェクトが初期化されているかどうかを示すフラグを指定 `CRITICAL_SECTION` します。|

## <a name="remarks"></a>解説

`CComSafeDeleteCriticalSection` クラス [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)から派生します。 ただし、で `CComSafeDeleteCriticalSection` は、 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)に対する追加の安全性メカニズムが提供されます。

のインスタンスがスコープ外に `CComSafeDeleteCriticalSection` 出るか、明示的にメモリから削除されると、基になるクリティカルセクションオブジェクトが有効な場合は自動的にクリーンアップされます。 また、基になるクリティカルセクションオブジェクトがまだ割り当てられていないか、既にメモリから解放されている場合、 [CComSafeDeleteCriticalSection:: Term](#term) メソッドは正常に終了します。

クリティカルセクションのヘルパークラスの詳細については、「 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>要件

**ヘッダー:** atlcore .h

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a> CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection

コンストラクターです。

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>解説

[M_bInitialized](#m_binitialized)データメンバーを FALSE に設定します。

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a> CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection

デストラクターです。

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>解説

`CRITICAL_SECTION` [M_bInitialized](#m_binitialized)データメンバーが TRUE に設定されている場合、メモリから内部オブジェクトを解放します。

## <a name="ccomsafedeletecriticalsectioninit"></a><a name="init"></a> CComSafeDeleteCriticalSection:: Init

[Init](/visualstudio/debugger/init)の基底クラスの実装を呼び出し、成功した場合は[m_bInitialized](#m_binitialized)を TRUE に設定します。

```
HRESULT Init() throw();
```

### <a name="return-value"></a>戻り値

[CComCriticalSection:: Init](../../atl/reference/ccomcriticalsection-class.md#init)の結果を返します。

## <a name="ccomsafedeletecriticalsectionlock"></a><a name="lock"></a> CComSafeDeleteCriticalSection:: Lock

[Lock](ccomcriticalsection-class.md#lock)の基本クラスの実装を呼び出します。

```
HRESULT Lock();
```

### <a name="return-value"></a>戻り値

[CComCriticalSection:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock)の結果を返します。

### <a name="remarks"></a>解説

このメソッドは、エントリ時に [m_bInitialized](#m_binitialized) データメンバーが TRUE に設定されていることを前提としています。 この条件が満たされない場合、デバッグビルドでアサーションが生成されます。

関数の動作の詳細については、「 [CComCriticalSection:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock)」を参照してください。

## <a name="ccomsafedeletecriticalsectionm_binitialized"></a><a name="m_binitialized"></a> CComSafeDeleteCriticalSection:: m_bInitialized

内部オブジェクトが初期化されているかどうかを示すフラグを指定 `CRITICAL_SECTION` します。

```
bool m_bInitialized;
```

### <a name="remarks"></a>解説

`m_bInitialized`データメンバーは、 `CRITICAL_SECTION` [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)クラスに関連付けられている、基になるオブジェクトの有効性を追跡するために使用されます。 `CRITICAL_SECTION`このフラグが TRUE に設定されていない場合、基になるオブジェクトはメモリから解放されません。

## <a name="ccomsafedeletecriticalsectionterm"></a><a name="term"></a> CComSafeDeleteCriticalSection:: Term

内部オブジェクトが有効な場合は、 [CComCriticalSection:: Term](../../atl/reference/ccomcriticalsection-class.md#term) の基本クラスの実装を呼び出し `CRITICAL_SECTION` ます。

```
HRESULT Term() throw();
```

### <a name="return-value"></a>戻り値

[CComCriticalSection:: Term](../../atl/reference/ccomcriticalsection-class.md#term)の結果を返します。入力時に[m_bInitialized](#m_binitialized)が FALSE に設定されている場合は S_OK します。

### <a name="remarks"></a>解説

内部オブジェクトが有効でない場合でも、このメソッドを呼び出すことは安全です `CRITICAL_SECTION` 。 [M_bInitialized](#m_binitialized)データメンバーが TRUE に設定されている場合、このクラスのデストラクターはこのメソッドを呼び出します。

## <a name="see-also"></a>関連項目

[CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
