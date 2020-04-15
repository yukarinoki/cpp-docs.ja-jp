---
title: クラス
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
ms.openlocfilehash: 391354c5672cf15c0286491619a13c6005493cfa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321064"
---
# <a name="ccomautothreadmodule-class"></a>クラス

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>パラメーター

*スレッドアロケーター*<br/>
[in]スレッドの選択を管理するクラス。 既定値は[、CComSimple スレッドアロケーターです](../../atl/reference/ccomsimplethreadallocator-class.md)。

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[Createinstance](#createinstance)|スレッドを選択し、関連付けられたアパートメントにオブジェクトを作成します。|
|[既定のスレッドを取得します。](#getdefaultthreads)|(静的)プロセッサの数に基づいて、モジュールのスレッド数を動的に計算します。|
|[Init](#init)|モジュールのスレッドを作成します。|
|[[Lock] (ロック)](#lock)|モジュールと現在のスレッドのロック数をインクリメントします。|
|[ロック 解除](#unlock)|モジュールと現在のスレッドのロックカウントを減算します。|

### <a name="data-members"></a>データ メンバー

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[を行う](#dwthreadid)|現在のスレッドの識別子を格納します。|
|[m_Allocator](#m_allocator)|スレッド選択を管理します。|
|[m_nThreads](#m_nthreads)|モジュール内のスレッド数を格納します。|
|[m_pApartments](#m_papartments)|モジュールのアパートメントを管理します。|

## <a name="remarks"></a>解説

> [!NOTE]
> このクラスは[、CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)および[CAtlModule](../../atl/reference/catlmodule-class.md)派生クラスに置き換えられた、廃止されました。 以下の情報は、ATL の古いリリースで使用するためのものです。

`CComAutoThreadModule`[は、ExE](../../atl/reference/ccommodule-class.md)および Windows サービス用のスレッド プールのアパートメント モデル COM サーバーを実装するために CComModule から派生します。 `CComAutoThreadModule`[では、CComApartment](../../atl/reference/ccomapartment-class.md)を使用して、モジュール内の各スレッドのアパートメントを管理します。

複数のアパートメントに`CComAutoThreadModule`オブジェクトを作成する場合からモジュールを派生します。 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)をクラス ファクトリとして指定するには、オブジェクトのクラス定義に[DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)マクロを含める必要があります。

既定では、ATL COM アプリケーション ウィザード (Visual Studio .NET の ATL プロジェクト`CComModule`ウィザード) は、モジュールを から派生します。 を使用`CComAutoThreadModule`するには、クラス定義を変更します。 次に例を示します。

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[カトルモジュール](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[カトルモジュール](../../atl/reference/catlmodulet-class.md)

[をクリックします。](../../atl/reference/catlautothreadmodulet-class.md)

[ココムモジュール](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomautothreadmodulecreateinstance"></a><a name="createinstance"></a>をインスタンス化します。

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*インスタンス*<br/>
[in]作成者関数へのポインター。

*riid*<br/>
[in]要求されたインターフェイスの IID。

*Ppvobj*<br/>
[アウト]*riid*によって識別されるインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppvObj*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

スレッドを選択し、関連付けられたアパートメントにオブジェクトを作成します。

## <a name="ccomautothreadmoduledwthreadid"></a><a name="dwthreadid"></a>を使用します :d。

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
DWORD dwThreadID;
```

### <a name="remarks"></a>解説

現在のスレッドの識別子を格納します。

## <a name="ccomautothreadmodulegetdefaultthreads"></a><a name="getdefaultthreads"></a>を取得します。

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>戻り値

EXE モジュールで作成されるスレッドの数。

### <a name="remarks"></a>解説

この静的関数は、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を動的に計算します。 既定では、この戻り値は[Init](#init)メソッドに渡され、スレッドが作成されます。

## <a name="ccomautothreadmoduleinit"></a><a name="init"></a>を使用します。

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]オブジェクト マップ エントリの配列へのポインター。

*H*<br/>
[in]HINSTANCE は`DLLMain`または`WinMain`に渡されます。

*プリビッド*<br/>
[in]プロジェクトに関連付けられているタイプ ライブラリの LIBID へのポインター。

*nスレッド*<br/>
[in]作成するスレッドの数。 既定では *、nThreads*は[GetDefaultThreads](#getdefaultthreads)によって返される値です。

### <a name="remarks"></a>解説

データ メンバーを初期化し *、nThreads*で指定されたスレッド数を作成します。

## <a name="ccomautothreadmodulelock"></a><a name="lock"></a>ロック

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
LONG Lock();
```

### <a name="return-value"></a>戻り値

診断やテストに役立つ値。

### <a name="remarks"></a>解説

モジュールと現在のスレッドのロック カウントに対してアトミック インクリメントを実行します。 `CComAutoThreadModule`は、モジュールロックカウントを使用して、どのクライアントもモジュールにアクセスしているかどうかを判断します。 現在のスレッドのロックカウントは、統計目的で使用されます。

## <a name="ccomautothreadmodulem_allocator"></a><a name="m_allocator"></a>を使用 m_Allocatorします。

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>解説

スレッド選択を管理するオブジェクト。 既定では、`ThreadAllocator`クラス テンプレート パラメーターは[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)です。

## <a name="ccomautothreadmodulem_nthreads"></a><a name="m_nthreads"></a>を使用 m_nThreadsします。

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
int m_nThreads;
```

### <a name="remarks"></a>解説

EXE モジュール内のスレッド数を格納します。 [Init](#init)が呼び`m_nThreads`出されると *、nThreads*パラメーター値に設定されます。 各スレッドの関連付けられたアパートメントは[、CComApartment](../../atl/reference/ccomapartment-class.md)オブジェクトによって管理されます。

## <a name="ccomautothreadmodulem_papartments"></a><a name="m_papartments"></a>を m_pApartments使用します。

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>解説

モジュール内のアパートメントを管理する[CComApartment](../../atl/reference/ccomapartment-class.md)オブジェクトの配列を指します。 配列内の要素の数は[、m_nThreads](#m_nthreads)メンバーに基づいています。

## <a name="ccomautothreadmoduleunlock"></a><a name="unlock"></a>クコムオートスレッドモジュール::ロック解除

ATL 7.0 では`CComAutoThreadModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
LONG Unlock();
```

### <a name="return-value"></a>戻り値

診断やテストに役立つ値。

### <a name="remarks"></a>解説

モジュールと現在のスレッドのロック カウントに対して、アトミックデクリメントを実行します。 `CComAutoThreadModule`は、モジュールロックカウントを使用して、どのクライアントもモジュールにアクセスしているかどうかを判断します。 現在のスレッドのロックカウントは、統計目的で使用されます。

モジュールのロックカウントがゼロになると、モジュールをアンロードできます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)
