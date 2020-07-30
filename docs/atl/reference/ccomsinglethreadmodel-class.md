---
title: CComSingleThreadModel クラス
ms.date: 2/29/2020
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
ms.openlocfilehash: 05ef787764045ec7e17f5cdfdb0d4611cb2ac900
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229975"
---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel クラス

このクラスには、変数の値をインクリメントおよびデクリメントするためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CComSingleThreadModel
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)クラスを参照します。|
|[CComSingleThreadModel:: CriticalSection](#criticalsection)|参照クラス `CComFakeCriticalSection` 。|
|[CComSingleThreadModel:: ThreadModelNoCS](#threadmodelnocs)|参照 `CComSingleThreadModel` 。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComSingleThreadModel::D ecrement](#decrement)|指定した変数の値をデクリメントします。 この実装はスレッドセーフではありません。|
|[CComSingleThreadModel:: Increment](#increment)|指定した変数の値をインクリメントします。 この実装はスレッドセーフではありません。|

## <a name="remarks"></a>解説

`CComSingleThreadModel`変数の値をインクリメントおよびデクリメントするためのメソッドを提供します。 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)や[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)とは異なり、これらのメソッドはスレッドセーフではありません。

通常、を使用するに `CComSingleThreadModel` **`typedef`** は、 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)または[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)の2つの名前のいずれかを使用します。 によって参照されるクラスは、 **`typedef`** 次の表に示すように、使用されるスレッドモデルによって異なります。

|Typedef|単一スレッドモデル|アパートメントスレッドモデル|フリースレッドモデル|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel` ;M =`CComMultiThreadModel`

`CComSingleThreadModel`は、3つ **`typedef`** の名前を定義します。 `ThreadModelNoCS`参照 `CComSingleThreadModel` 。 `AutoCriticalSection`および `CriticalSection` リファレンスクラス[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)。クリティカルセクションの所有権の取得と解放に関連付けられた空のメソッドを提供します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="ccomsinglethreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComSingleThreadModel::AutoCriticalSection

を使用する場合 `CComSingleThreadModel` 、 **`typedef`** 名前は `AutoCriticalSection` クラス[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>解説

`CComFakeCriticalSection`はクリティカルセクションを提供しないため、メソッドは何も行いません。

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)には、の定義が含まれて `AutoCriticalSection` います。 次の表は、スレッドモデルクラスと、によって参照されるクリティカルセクションクラスとの関係を示してい `AutoCriticalSection` ます。

|クラスの定義|参照されるクラス|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

に加え `AutoCriticalSection` て、CriticalSection という名前を使用することもでき **`typedef`** ます。 [CriticalSection](#criticalsection) `AutoCriticalSection`CRT スタートアップコードを削除する場合は、グローバルオブジェクトまたは静的クラスメンバーにを指定しないでください。

### <a name="example"></a>例

「 [CComMultiThreadModel:: AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="ccomsinglethreadmodelcriticalsection"></a><a name="criticalsection"></a>CComSingleThreadModel:: CriticalSection

を使用する場合 `CComSingleThreadModel` 、 **`typedef`** 名前は `CriticalSection` クラス[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>解説

`CComFakeCriticalSection`はクリティカルセクションを提供しないため、メソッドは何も行いません。

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)には、の定義が含まれて `CriticalSection` います。 次の表は、スレッドモデルクラスと、によって参照されるクリティカルセクションクラスとの関係を示してい `CriticalSection` ます。

|クラスの定義|参照されるクラス|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

に加え `CriticalSection` て、AutoCriticalSection という名前を使用することもでき **`typedef`** ます。 [AutoCriticalSection](#autocriticalsection) `AutoCriticalSection`CRT スタートアップコードを削除する場合は、グローバルオブジェクトまたは静的クラスメンバーにを指定しないでください。

### <a name="example"></a>例

「 [CComMultiThreadModel:: AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="ccomsinglethreadmodeldecrement"></a><a name="decrement"></a>CComSingleThreadModel::D ecrement

この静的関数は、 *p*が指す変数の値をデクリメントします。

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
からデクリメントする変数へのポインター。

### <a name="return-value"></a>戻り値

デクリメントの結果。

## <a name="ccomsinglethreadmodelincrement"></a><a name="increment"></a>CComSingleThreadModel:: Increment

この静的関数は、 *p*が指す変数の値をインクリメントします。

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
からインクリメントする変数へのポインター。

### <a name="return-value"></a>戻り値

インクリメントの結果。

## <a name="ccomsinglethreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComSingleThreadModel:: ThreadModelNoCS

を使用する場合 `CComSingleThreadModel` 、名前は単にを **`typedef`** 参照し `ThreadModelNoCS` `CComSingleThreadModel` ます。

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>解説

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)には、の定義が含まれて `ThreadModelNoCS` います。 次の表は、スレッドモデルクラスとによって参照されるクラスの関係を示してい `ThreadModelNoCS` ます。

|クラスの定義|参照されるクラス|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>例

「 [CComMultiThreadModel:: AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
