---
description: '詳細情報: CComMultiThreadModelNoCS クラス'
title: CComMultiThreadModelNoCS クラス
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
ms.openlocfilehash: 8b26c59564f9a7869bb3429ee31284925815e6ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152010"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS クラス

`CComMultiThreadModelNoCS` クリティカルセクションのロックまたはロック解除機能を使用せずに、変数の値をインクリメントおよびデクリメントするためのスレッドセーフなメソッドを提供します。

## <a name="syntax"></a>構文

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)クラスを参照します。|
|[CComMultiThreadModelNoCS:: CriticalSection](#criticalsection)|参照クラス `CComFakeCriticalSection` 。|
|[CComMultiThreadModelNoCS:: ThreadModelNoCS](#threadmodelnocs)|参照クラス `CComMultiThreadModelNoCS` 。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComMultiThreadModelNoCS::D ecrement](#decrement)|雑音指定された変数の値をスレッドセーフな方法でデクリメントします。|
|[CComMultiThreadModelNoCS:: Increment](#increment)|雑音指定された変数の値をスレッドセーフな方法でインクリメントします。|

## <a name="remarks"></a>解説

`CComMultiThreadModelNoCS` は、変数をインクリメントおよびデクリメントするためのスレッドセーフメソッドを提供するという点で、 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) に似ています。 ただし、を使用してクリティカルセクションクラスを参照する場合、 `CComMultiThreadModelNoCS` やなどのメソッド `Lock` `Unlock` は何も行いません。

通常は、と `CComMultiThreadModelNoCS` いう名前を使用し `ThreadModelNoCS` **`typedef`** ます。 これ **`typedef`** は `CComMultiThreadModelNoCS` 、、、および CComSingleThreadModel で定義されて `CComMultiThreadModel` います。 [](../../atl/reference/ccomsinglethreadmodel-class.md)

> [!NOTE]
> グローバル **`typedef`** 名 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) と [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) は参照しません `CComMultiThreadModelNoCS` 。

に加え `ThreadModelNoCS` て、は `CComMultiThreadModelNoCS` およびを定義し `AutoCriticalSection` `CriticalSection` ます。 これらの後者の2つの **`typedef`** 名前は、 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。これは、クリティカルセクションの取得と解放に関連付けられた空のメソッドを提供します。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a> CComMultiThreadModelNoCS::AutoCriticalSection

を使用する場合 `CComMultiThreadModelNoCS` 、 **`typedef`** 名前は `AutoCriticalSection` クラス [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>解説

`CComFakeCriticalSection`はクリティカルセクションを提供しないため、メソッドは何も行いません。

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) と [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) には、の定義も含まれて `AutoCriticalSection` います。 次の表は、スレッドモデルクラスと、によって参照されるクリティカルセクションクラスとの関係を示してい `AutoCriticalSection` ます。

|クラスの定義|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

に加え `AutoCriticalSection` て、CriticalSection という名前を使用することもでき **`typedef`** ます。 [](#criticalsection) `AutoCriticalSection`CRT スタートアップコードを削除する場合は、グローバルオブジェクトまたは静的クラスメンバーにを指定しないでください。

### <a name="example"></a>例

「 [CComMultiThreadModel:: AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a> CComMultiThreadModelNoCS:: CriticalSection

を使用する場合 `CComMultiThreadModelNoCS` 、 **`typedef`** 名前は `CriticalSection` クラス [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>解説

`CComFakeCriticalSection`はクリティカルセクションを提供しないため、メソッドは何も行いません。

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) と [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) には、の定義も含まれて `CriticalSection` います。 次の表は、スレッドモデルクラスと、によって参照されるクリティカルセクションクラスとの関係を示してい `CriticalSection` ます。

|クラスの定義|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

に加え `CriticalSection` て、という名前を使用することもでき **`typedef`** `AutoCriticalSection` ます。 `AutoCriticalSection`CRT スタートアップコードを削除する場合は、グローバルオブジェクトまたは静的クラスメンバーにを指定しないでください。

### <a name="example"></a>例

「 [CComMultiThreadModel:: AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a> CComMultiThreadModelNoCS::D ecrement

この静的関数は、Win32 関数 [InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)を呼び出します。これにより、 *p* が指す変数の値が減少します。

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
からデクリメントする変数へのポインター。

### <a name="return-value"></a>戻り値

デクリメントの結果が0の場合、は `Decrement` 0 を返します。 デクリメントの結果が0以外の場合、戻り値も0以外になりますが、デクリメントの結果と一致しない可能性があります。

### <a name="remarks"></a>解説

**InterlockedDecrement** を使用すると、複数のスレッドがこの変数を同時に使用することを防ぐことができます。

## <a name="ccommultithreadmodelnocsincrement"></a><a name="increment"></a> CComMultiThreadModelNoCS:: Increment

この静的関数は、Win32 関数 [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)を呼び出します。これにより、 *p* が指す変数の値がインクリメントされます。

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
からインクリメントする変数へのポインター。

### <a name="return-value"></a>戻り値

インクリメントの結果が0の場合、 **increment** は0を返します。 インクリメントの結果が0以外の場合、戻り値も0以外になりますが、インクリメントの結果と一致しない可能性があります。

### <a name="remarks"></a>解説

**InterlockedIncrement** を使用すると、複数のスレッドがこの変数を同時に使用することを防ぐことができます。

## <a name="ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a> CComMultiThreadModelNoCS:: ThreadModelNoCS

を使用する場合 `CComMultiThreadModelNoCS` 、名前は単にを **`typedef`** 参照し `ThreadModelNoCS` `CComMultiThreadModelNoCS` ます。

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>解説

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) と [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) には、の定義も含まれて `ThreadModelNoCS` います。 次の表は、スレッドモデルクラスとによって参照されるクラスの関係を示してい `ThreadModelNoCS` ます。

|クラスの定義|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

のの定義は、とと対称であることに注意して `ThreadModelNoCS` `CComMultiThreadModelNoCS` `CComMultiThreadModel` `CComSingleThreadModel` ください。 たとえば、のサンプルコードが次のように宣言されているとし `CComMultiThreadModel::AutoCriticalSection` **`typedef`** ます。

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

に対して指定されたクラス (など) に関係なく `ThreadModel` `CComMultiThreadModelNoCS` 、は `_ThreadModel` それに応じて解決します。

### <a name="example"></a>例

「 [CComMultiThreadModel:: AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
