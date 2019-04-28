---
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
ms.openlocfilehash: 0269079db97e2ff91767c9c0c74a9336fce81ade
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258885"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection クラス

このクラスは、取得およびクリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|コンストラクターです。|
|[CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::Init](#init)|作成し、クリティカル セクション オブジェクトを初期化します。|
|[CComSafeDeleteCriticalSection::Lock](#lock)|クリティカル セクション オブジェクトの所有権を取得します。|
|[CComSafeDeleteCriticalSection::Term](#term)|クリティカル セクション オブジェクトによって使用されるシステム リソースを解放します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_bInitialized](#m_binitialized)|フラグかどうか、内部`CRITICAL_SECTION`オブジェクトが初期化されています。|

## <a name="remarks"></a>Remarks

`CComSafeDeleteCriticalSection` クラスから派生[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)します。 ただし、`CComSafeDeleteCriticalSection`経由で安全性強化メカニズムを提供します。 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)します。

インスタンス`CComSafeDeleteCriticalSection`がスコープ外になるかが明示的にメモリから削除されると、基になるクリティカル セクション オブジェクトは自動的にクリーンアップ有効である場合。 さらに、 [CComSafeDeleteCriticalSection::Term](#term)基になるクリティカル セクション オブジェクトが割り当てられていないか、既にメモリから解放されて場合、メソッドが正常に終了します。

参照してください[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)クリティカル セクションのヘルパー クラスの詳細についてはします。

## <a name="inheritance-hierarchy"></a>継承階層

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

##  <a name="ccomsafedeletecriticalsection"></a>  CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection

コンストラクターです。

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>Remarks

セット、 [m_bInitialized](#m_binitialized)データ メンバーを FALSE にします。

##  <a name="dtor"></a>  CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection

デストラクターです。

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>Remarks

解放、内部`CRITICAL_SECTION`メモリからオブジェクトの場合、 [m_bInitialized](#m_binitialized)データ メンバーが TRUE に設定します。

##  <a name="init"></a>  CComSafeDeleteCriticalSection::Init

基本クラス実装を呼び出して[Init](/visualstudio/debugger/init)設定と[m_bInitialized](#m_binitialized)成功した場合は TRUE に設定します。

```
HRESULT Init() throw();
```

### <a name="return-value"></a>戻り値

結果を返します[CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init)します。

##  <a name="lock"></a>  CComSafeDeleteCriticalSection::Lock

基本クラス実装を呼び出して[ロック](ccomcriticalsection-class.md#lock)します。

```
HRESULT Lock();
```

### <a name="return-value"></a>戻り値

結果を返します[CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)します。

### <a name="remarks"></a>Remarks

この方法では、 [m_bInitialized](#m_binitialized)エントリ時にデータ メンバーが TRUE に設定します。 アサーションは、この条件が満たされない場合、デバッグ ビルドで生成されます。

関数の動作の詳細についてを参照してください[CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)します。

##  <a name="m_binitialized"></a>  CComSafeDeleteCriticalSection::m_bInitialized

フラグかどうか、内部`CRITICAL_SECTION`オブジェクトが初期化されています。

```
bool m_bInitialized;
```

### <a name="remarks"></a>Remarks

`m_bInitialized`データ メンバーが、基になるの有効性を追跡するために使用される`CRITICAL_SECTION`オブジェクトに関連付けられている、 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)クラス。 基になる`CRITICAL_SECTION`オブジェクトは、このフラグが TRUE に設定されていない場合は、メモリから解放するのには試行されません。

##  <a name="term"></a>  CComSafeDeleteCriticalSection::Term

基本クラス実装を呼び出して[CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term)場合、内部`CRITICAL_SECTION`オブジェクトが無効です。

```
HRESULT Term() throw();
```

### <a name="return-value"></a>戻り値

結果を返します[CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term)、s_ok 場合[m_bInitialized](#m_binitialized)エントリ時に FALSE に設定されました。

### <a name="remarks"></a>Remarks

安全に呼び出す場合にも、このメソッドの内部が`CRITICAL_SECTION`オブジェクトが無効です。 このクラスのデストラクターが場合、このメソッドを呼び出して、 [m_bInitialized](#m_binitialized)データ メンバーが TRUE に設定します。

## <a name="see-also"></a>関連項目

[CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
