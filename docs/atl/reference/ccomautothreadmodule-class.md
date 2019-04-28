---
title: CComAutoThreadModule クラス
ms.date: 11/04/2016
f1_keywords:
- CComAutoThreadModule
- ATLBASE/ATL::CComAutoThreadModule
- ATLBASE/ATL::CreateInstance
- ATLBASE/ATL::GetDefaultThreads
- ATLBASE/ATL::Init
- ATLBASE/ATL::Lock
- ATLBASE/ATL::Unlock
- ATLBASE/ATL::dwThreadID
- ATLBASE/ATL::m_Allocator
- ATLBASE/ATL::m_nThreads
- ATLBASE/ATL::m_pApartments
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
ms.openlocfilehash: 9b0fa685bf9a7de94b158bd62b00161c1b58562d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260215"
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule クラス

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>パラメーター

*テンプレートパラ*<br/>
[in]スレッドの選択を管理するクラスです。 既定値は[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)します。

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CreateInstance](#createinstance)|スレッドを選択し、関連付けられているアパートメントでオブジェクトを作成します。|
|[GetDefaultThreads](#getdefaultthreads)|(静的)プロセッサの数に基づいて、モジュールのスレッドの数を動的に計算します。|
|[Init](#init)|モジュールのスレッドを作成します。|
|[ロック](#lock)|モジュールと、現在のスレッドのロック カウントをインクリメントします。|
|[ロックを解除します。](#unlock)|モジュールと、現在のスレッドのロックのカウントをデクリメントします。|

### <a name="data-members"></a>データ メンバー

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[dwThreadID](#dwthreadid)|現在のスレッドの識別子が含まれています。|
|[m_Allocator](#m_allocator)|スレッドの選択を管理します。|
|[m_nThreads](#m_nthreads)|モジュールのスレッドの数が含まれています。|
|[m_pApartments](#m_papartments)|モジュールのアパートメントを管理します。|

## <a name="remarks"></a>Remarks

> [!NOTE]
>  このクラスは廃止されています、置き換えられました、 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)と[CAtlModule](../../atl/reference/catlmodule-class.md)クラスを派生します。 以下の情報は、ATL の以前のリリースでの使用

`CComAutoThreadModule` 派生した[CComModule](../../atl/reference/ccommodule-class.md) Exe および Windows サービスのスレッド プール、アパートメント モデルの COM サーバーを実装します。 `CComAutoThreadModule` 使用して[CComApartment](../../atl/reference/ccomapartment-class.md)モジュール内の各スレッド アパートメントを管理します。

モジュールからの派生`CComAutoThreadModule`複数アパートメント内でオブジェクトを作成する場合。 含める必要があります、 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)を指定するオブジェクトのクラス定義でマクロ[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)クラス ファクトリとして。

既定では、ATL COM AppWizard (Visual Studio .NET で ATL プロジェクト ウィザード) のモジュールからは派生`CComModule`します。 使用する`CComAutoThreadModule`、クラス定義を変更します。 例:

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

[CComModule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

##  <a name="createinstance"></a>  CComAutoThreadModule::CreateInstance

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*pfnCreateInstance*<br/>
[in]作成者関数へのポインター。

*riid*<br/>
[in]要求されたインターフェイスの IID。

*ppvObj*<br/>
[out]によって識別されるインターフェイス ポインターへのポインター *riid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppvObj* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

スレッドを選択し、関連付けられているアパートメントでオブジェクトを作成します。

##  <a name="dwthreadid"></a>  CComAutoThreadModule::dwThreadID

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
DWORD dwThreadID;
```

### <a name="remarks"></a>Remarks

現在のスレッドの識別子が含まれています。

##  <a name="getdefaultthreads"></a>  CComAutoThreadModule::GetDefaultThreads

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>戻り値

EXE モジュール内に作成するスレッドの数。

### <a name="remarks"></a>Remarks

この静的関数は、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を動的に計算します。 既定では、この戻り値が渡される、 [Init](#init)スレッドを作成するメソッド。

##  <a name="init"></a>  CComAutoThreadModule::Init

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>パラメーター

*p*<br/>
[in]オブジェクト マップ エントリの配列へのポインター。

*h*<br/>
[in]渡される、HINSTANCE`DLLMain`または`WinMain`します。

*plibid*<br/>
[in]プロジェクトに関連付けられているタイプ ライブラリの LIBID へのポインター。

*nThreads*<br/>
[in]作成されるスレッドの数。 既定では、 *nThreads*によって返される値は、 [GetDefaultThreads](#getdefaultthreads)します。

### <a name="remarks"></a>Remarks

データ メンバーは初期化されで指定されたスレッドの数を作成します。 *nThreads*します。

##  <a name="lock"></a>  CComAutoThreadModule::Lock

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
LONG Lock();
```

### <a name="return-value"></a>戻り値

テストや診断に使用する値。

### <a name="remarks"></a>Remarks

モジュールと、現在のスレッドのロック カウントをインクリメントを実行します。 `CComAutoThreadModule` モジュールのロック カウントを使用して、すべてのクライアントは、モジュールにアクセスするかどうかを調べます。 現在のスレッドのロック カウントは、統計的な目的で使用されます。

##  <a name="m_allocator"></a>  CComAutoThreadModule::m_Allocator

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>Remarks

スレッドの選択を管理するオブジェクト。 既定で、`ThreadAllocator`クラス テンプレートのパラメーターが[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)します。

##  <a name="m_nthreads"></a>  CComAutoThreadModule::m_nThreads

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
int m_nThreads;
```

### <a name="remarks"></a>Remarks

EXE モジュール内のスレッドの数が含まれています。 ときに[Init](#init)が呼び出され、`m_nThreads`に設定されている、 *nThreads*パラメーターの値。 各スレッドの関連付けられているアパートメントがによって管理されている、 [CComApartment](../../atl/reference/ccomapartment-class.md)オブジェクト。

##  <a name="m_papartments"></a>  CComAutoThreadModule::m_pApartments

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>Remarks

配列を指す[CComApartment](../../atl/reference/ccomapartment-class.md)モジュールでアパートメントを管理のオブジェクト。 配列内の要素の数がに基づいて、 [m_nThreads](#m_nthreads)メンバー。

##  <a name="unlock"></a>  CComAutoThreadModule::Unlock

ATL 7.0 では、時点で`CComAutoThreadModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
LONG Unlock();
```

### <a name="return-value"></a>戻り値

テストや診断に使用する値。

### <a name="remarks"></a>Remarks

モジュールと、現在のスレッドのロック カウントをデクリメントを実行します。 `CComAutoThreadModule` モジュールのロック カウントを使用して、すべてのクライアントは、モジュールにアクセスするかどうかを調べます。 現在のスレッドのロック カウントは、統計的な目的で使用されます。

モジュールのロック カウントがゼロに達すると、モジュールがアンロードされることができます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)
