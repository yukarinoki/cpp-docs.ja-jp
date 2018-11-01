---
title: CComSingleThreadModel クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 2b0e19c94c16de936758ed4e547d731aed40cb26
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565361"
---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel クラス

このクラスは、変数の値、インクリメントおよびデクリメントするためのメソッドを提供します。

## <a name="syntax"></a>構文

```
class CComSingleThreadModel
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。|
|[CComSingleThreadModel::CriticalSection](#criticalsection)|クラスを参照`CComFakeCriticalSection`します。|
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|参照`CComSingleThreadModel`します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComSingleThreadModel::Decrement](#decrement)|デクリメント、指定した変数の値。 この実装はスレッド セーフではありません。|
|[CComSingleThreadModel::Increment](#increment)|指定された変数の値をインクリメントします。 この実装はスレッド セーフではありません。|

## <a name="remarks"></a>Remarks

`CComSingleThreadModel` インクリメントおよびデクリメントするため、変数の値に対応するメソッドを提供します。 異なり[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)、これらのメソッドはスレッド セーフではありません。

通常、使用して`CComSingleThreadModel`2 つのいずれかで**typedef**名か[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)または[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)します。 各によって参照されるクラス**typedef**次の表に示すように使用すると、スレッド処理モデルによって異なります。

|Typedef|シングル スレッド モデル|アパートメント スレッド モデル|フリー スレッド モデル|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`;M = `CComMultiThreadModel`

`CComSingleThreadModel` 3 つの定義自体**typedef**名。 `ThreadModelNoCS` 参照`CComSingleThreadModel`します。 `AutoCriticalSection` `CriticalSection`クラスを参照する[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)、取得およびクリティカル セクションの所有権を解放するに関連付けられている空のメソッドを提供します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

##  <a name="autocriticalsection"></a>  CComSingleThreadModel::AutoCriticalSection

使用する場合`CComSingleThreadModel`、 **typedef**名前`AutoCriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Remarks

`CComFakeCriticalSection` 、クリティカル セクションを行いませんそのメソッドは、何もしません。

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)の定義を含む`AutoCriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクションのクラス間のリレーションシップ`AutoCriticalSection`:

|クラスで定義されています。|参照クラス|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

ほかに`AutoCriticalSection`、使用することができます、 **typedef**名前[CriticalSection](#criticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを削除する場合、静的クラス メンバー。

### <a name="example"></a>例

参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。

##  <a name="criticalsection"></a>  CComSingleThreadModel::CriticalSection

使用する場合`CComSingleThreadModel`、 **typedef**名前`CriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Remarks

`CComFakeCriticalSection` 、クリティカル セクションを行いませんそのメソッドは、何もしません。

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)の定義を含む`CriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクションのクラス間のリレーションシップ`CriticalSection`:

|クラスで定義されています。|参照クラス|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

ほかに`CriticalSection`、使用することができます、 **typedef**名前[AutoCriticalSection](#autocriticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを削除する場合、静的クラス メンバー。

### <a name="example"></a>例

参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。

##  <a name="decrement"></a>  CComSingleThreadModel::Decrement

この静的関数デクリメント、変数の値によって示される*p*します。

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
[in]デクリメントする変数へのポインター。

### <a name="return-value"></a>戻り値

減算の結果。

##  <a name="increment"></a>  CComSingleThreadModel::Increment

この静的関数デクリメント、変数の値によって示される*p*します。

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
[in]インクリメントされる変数へのポインター。

### <a name="return-value"></a>戻り値

増分の結果。

##  <a name="threadmodelnocs"></a>  CComSingleThreadModel::ThreadModelNoCS

使用する場合`CComSingleThreadModel`、 **typedef**名前`ThreadModelNoCS`だけ参照`CComSingleThreadModel`します。

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>Remarks

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)の定義を含む`ThreadModelNoCS`します。 次の表は、スレッド処理モデル クラスとによって参照されるクラス間のリレーションシップ`ThreadModelNoCS`:

|クラスで定義されています。|参照クラス|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>例

参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
