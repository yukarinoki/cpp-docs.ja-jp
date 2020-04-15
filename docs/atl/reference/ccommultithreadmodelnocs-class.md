---
title: クラスを構成します。
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
ms.openlocfilehash: 4d41ffcfccbd7ef65ed86df79bffec1209a88cd3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327649"
---
# <a name="ccommultithreadmodelnocs-class"></a>クラスを構成します。

`CComMultiThreadModelNoCS`には、クリティカル セクションのロックやロック解除機能を使用せずに、変数の値をインクリメントおよびデクリメントするためのスレッド セーフなメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CCom マルチスレッドモデルNoCS::オートクリティカルセクション](#autocriticalsection)|クラス[CComFake クリティカルセクションを参照します](../../atl/reference/ccomfakecriticalsection-class.md)。|
|[CCom マルチスレッドモデルNoCS::クリティカルセクション](#criticalsection)|クラス`CComFakeCriticalSection`を参照します。|
|[を使用します。](#threadmodelnocs)|クラス`CComMultiThreadModelNoCS`を参照します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCom マルチスレッドモデルNoCS::D](#decrement)|(静的)指定した変数の値をスレッド セーフな方法でデクリメントします。|
|[CCom マルチスレッドモデルNoCS::インクリメント](#increment)|(静的)スレッド セーフな方法で、指定した変数の値をインクリメントします。|

## <a name="remarks"></a>解説

`CComMultiThreadModelNoCS`は、変数をインクリメントおよびデクリメントするためのスレッド セーフメソッドを提供するという点で[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)に似ています。 ただし、 を使用してクリティカル セクション`CComMultiThreadModelNoCS`クラスを参照すると`Lock`、`Unlock`メソッドは何も実行しません。

通常は`CComMultiThreadModelNoCS``ThreadModelNoCS`**、typedef**名を使用します。 この**タイプ定義**は、 `CComMultiThreadModelNoCS`、`CComMultiThreadModel`および[CCom シングルスレッドモデル](../../atl/reference/ccomsinglethreadmodel-class.md)で定義されています。

> [!NOTE]
> グローバル**な型定義**名[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)および[CComGlobals スレッドモデルは](atl-typedefs.md#ccomglobalsthreadmodel)参照`CComMultiThreadModelNoCS`しません。

に加えて`ThreadModelNoCS`、 `CComMultiThreadModelNoCS` `AutoCriticalSection`および`CriticalSection`を定義します。 これらの後者の 2 つの**typedef**名は、クリティカル セクションの取得と解放に関連付けられた空のメソッドを提供する[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a>CCom マルチスレッドモデルNoCS::オートクリティカルセクション

を使用`CComMultiThreadModelNoCS`する場合 **、typedef**名`AutoCriticalSection`はクラス[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>解説

クリティカル`CComFakeCriticalSection`セクションを提供しないため、そのメソッドは何も実行しません。

[の](../../atl/reference/ccommultithreadmodel-class.md)[定義も含](../../atl/reference/ccomsinglethreadmodel-class.md)まれています`AutoCriticalSection`。 スレッド モデル クラスと、 で参照されるクリティカル セクション クラスの関係を次`AutoCriticalSection`の表に示します。

|で定義されたクラス|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

また`AutoCriticalSection`、**タイプ定義**名の[CriticalSection](#criticalsection)を使用することもできます。 CRT スタートアップ`AutoCriticalSection`コードを削除する場合は、グローバル オブジェクトまたは静的クラス メンバーで指定しないでください。

### <a name="example"></a>例

[「CCom マルチスレッドモデル::オートクリティカルセクション](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a>CCom マルチスレッドモデルNoCS::クリティカルセクション

を使用`CComMultiThreadModelNoCS`する場合 **、typedef**名`CriticalSection`はクラス[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>解説

クリティカル`CComFakeCriticalSection`セクションを提供しないため、そのメソッドは何も実行しません。

[の](../../atl/reference/ccommultithreadmodel-class.md)[定義も含](../../atl/reference/ccomsinglethreadmodel-class.md)まれています`CriticalSection`。 スレッド モデル クラスと、 で参照されるクリティカル セクション クラスの関係を次`CriticalSection`の表に示します。

|で定義されたクラス|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

に加えて`CriticalSection`、 **typedef**名`AutoCriticalSection`を使用できます。 CRT スタートアップ`AutoCriticalSection`コードを削除する場合は、グローバル オブジェクトまたは静的クラス メンバーで指定しないでください。

### <a name="example"></a>例

[「CCom マルチスレッドモデル::オートクリティカルセクション](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a>CCom マルチスレッドモデルNoCS::D

この静的関数は *、Win32*関数[InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)を呼び出し、p が指す変数の値をデクリメントします。

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]デクリメントされる変数へのポインター。

### <a name="return-value"></a>戻り値

デクリメントの結果が 0 の場合は`Decrement`、0 を返します。 デクリメントの結果が 0 以外の場合、戻り値も 0 以外ですが、減分の結果と等しくない可能性があります。

### <a name="remarks"></a>解説

**InterlockedDecrement**は、複数のスレッドがこの変数を同時に使用するのを防ぎます。

## <a name="ccommultithreadmodelnocsincrement"></a><a name="increment"></a>CCom マルチスレッドモデルNoCS::インクリメント

この静的関数は *、Win32*関数[InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)を呼び出し、p が指す変数の値をインクリメントします。

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]インクリメントされる変数へのポインター。

### <a name="return-value"></a>戻り値

増分の結果が 0 の場合 **、Increment**は 0 を返します。 増分の結果が 0 以外の場合、戻り値も 0 以外の値になりますが、増分の結果と等しくない可能性があります。

### <a name="remarks"></a>解説

**InterlockedIncrement**は、複数のスレッドがこの変数を同時に使用できないようにします。

## <a name="ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a>を使用します。

を使用`CComMultiThreadModelNoCS`する場合 **、typedef** `ThreadModelNoCS`名`CComMultiThreadModelNoCS`は 単に を参照します。

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>解説

[の](../../atl/reference/ccommultithreadmodel-class.md)[定義も含](../../atl/reference/ccomsinglethreadmodel-class.md)まれています`ThreadModelNoCS`。 スレッド モデル クラスと によって参照されるクラスの関係を次の表に`ThreadModelNoCS`示します。

|で定義されたクラス|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

`ThreadModelNoCS`の`CComMultiThreadModelNoCS`定義は、 と と`CComMultiThreadModel``CComSingleThreadModel`の対称性を提供します。 たとえば、次の**typedef**`CComMultiThreadModel::AutoCriticalSection`を宣言したサンプル コードを考えます。

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

に指定されたクラス`ThreadModel`(など`CComMultiThreadModelNoCS`) に`_ThreadModel`関係なく、それに応じて解決されます。

### <a name="example"></a>例

[「CCom マルチスレッドモデル::オートクリティカルセクション](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
