---
title: クラスを削除します。
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
ms.openlocfilehash: cb0dc440fc0e79e0023b5fbd6e4ca2345d031d3d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327365"
---
# <a name="ccomsafedeletecriticalsection-class"></a>クラスを削除します。

このクラスには、クリティカル セクション オブジェクトの所有権を取得および解放するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComセーフ削除クリティカルセクション::CComセーフ削除クリティカルセクション](#ccomsafedeletecriticalsection)|コンストラクターです。|
|[CComセーフ削除クリティカルセクション:~CComセーフ削除クリティカルセクション](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComセーフ削除クリティカルセクション::イニト](#init)|クリティカル セクション オブジェクトを作成および初期化します。|
|[CComセーフ削除クリティカルセクション::ロック](#lock)|クリティカル セクション オブジェクトの所有権を取得します。|
|[CComセーフ削除クリティカルセクション::用語](#term)|クリティカル セクション オブジェクトによって使用されるシステム リソースを解放します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_bInitialized](#m_binitialized)|内部`CRITICAL_SECTION`オブジェクトが初期化されているかどうかを示します。|

## <a name="remarks"></a>解説

`CComSafeDeleteCriticalSection`クラス[から](../../atl/reference/ccomcriticalsection-class.md)派生します。 ただし`CComSafeDeleteCriticalSection`[、CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)に対する追加の安全メカニズムを提供します。

インスタンスがスコープ外`CComSafeDeleteCriticalSection`に出るか、または明示的にメモリから削除された場合、基になるクリティカル セクション オブジェクトがまだ有効な場合は自動的にクリーンアップされます。 さらに、基になるクリティカル セクション オブジェクトがまだ割り当てられていないか、既にメモリから解放されている場合[、CComSafeDeleteCriticalSection::Term](#term)メソッドは正常に終了します。

クリティカル セクション ヘルパー クラスの詳細については[、「CComCriticalSection」](../../atl/reference/ccomcriticalsection-class.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ココムクリティカルセクション](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a>CComセーフ削除クリティカルセクション::CComセーフ削除クリティカルセクション

コンストラクターです。

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>解説

[m_bInitialized](#m_binitialized)データ メンバーを FALSE に設定します。

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a>CComセーフ削除クリティカルセクション:~CComセーフ削除クリティカルセクション

デストラクターです。

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>解説

m_bInitialized データ`CRITICAL_SECTION`メンバーが TRUE[m_bInitialized](#m_binitialized)に設定されている場合、メモリから内部オブジェクトを解放します。

## <a name="ccomsafedeletecriticalsectioninit"></a><a name="init"></a>CComセーフ削除クリティカルセクション::イニト

[Init](/visualstudio/debugger/init)の基本クラスの実装を呼び出し、成功した場合[はm_bInitialized](#m_binitialized) TRUE に設定します。

```
HRESULT Init() throw();
```

### <a name="return-value"></a>戻り値

[CComCriticalセクション](../../atl/reference/ccomcriticalsection-class.md#init)の結果を返します: Init .

## <a name="ccomsafedeletecriticalsectionlock"></a><a name="lock"></a>CComセーフ削除クリティカルセクション::ロック

[Lock](ccomcriticalsection-class.md#lock)の基本クラスの実装を呼び出します。

```
HRESULT Lock();
```

### <a name="return-value"></a>戻り値

[CComCriticalセクション::ロック](../../atl/reference/ccomcriticalsection-class.md#lock)の結果を返します。

### <a name="remarks"></a>解説

このメソッドは、入力時に[m_bInitialized](#m_binitialized)データ メンバが TRUE に設定されていることを前提としています。 この条件が満たされない場合、デバッグ ビルドでアサーションが生成されます。

関数の動作の詳細については[、「CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)」を参照してください。

## <a name="ccomsafedeletecriticalsectionm_binitialized"></a><a name="m_binitialized"></a>CComセーフ削除クリティカルセクション::m_bInitialized

内部`CRITICAL_SECTION`オブジェクトが初期化されているかどうかを示します。

```
bool m_bInitialized;
```

### <a name="remarks"></a>解説

データ`m_bInitialized`メンバーは、[クラス](../../atl/reference/ccomsafedeletecriticalsection-class.md)に関連付けられている基`CRITICAL_SECTION`になるオブジェクトの有効性を追跡するために使用されます。 このフラグ`CRITICAL_SECTION`が TRUE に設定されていない場合、基になるオブジェクトはメモリから解放されません。

## <a name="ccomsafedeletecriticalsectionterm"></a><a name="term"></a>CComセーフ削除クリティカルセクション::用語

内部`CRITICAL_SECTION`オブジェクトが有効な場合は[、CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term)の基本クラスの実装を呼び出します。

```
HRESULT Term() throw();
```

### <a name="return-value"></a>戻り値

入力時に m_bInitializedが FALSE に[設定されている場合](#m_binitialized)は[、CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term)の結果を S_OK返します。

### <a name="remarks"></a>解説

内部`CRITICAL_SECTION`オブジェクトが無効な場合でも、このメソッドを呼び出しても安全です。 このクラスのデストラクターは[、m_bInitialized](#m_binitialized)データ メンバーが TRUE に設定されている場合に、このメソッドを呼び出します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomcriticalsection-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
