---
title: クラスを 1 つ追加します。
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
ms.openlocfilehash: 3d8169c999ba96049bc711033f7ba2ef53989663
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327329"
---
# <a name="ccomsinglethreadmodel-class"></a>クラスを 1 つ追加します。

このクラスには、変数の値をインクリメントおよびデクリメントするためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CComSingleThreadModel
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CComシングルスレッドモデル::オートクリティカルセクション](#autocriticalsection)|クラス[CComFake クリティカルセクションを参照します](../../atl/reference/ccomfakecriticalsection-class.md)。|
|[CComシングルスレッドモデル::クリティカルセクション](#criticalsection)|クラス`CComFakeCriticalSection`を参照します。|
|[を使用するモデル::スレッドモデルNoCS](#threadmodelnocs)|参照`CComSingleThreadModel`:|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComシングルスレッドモデル::D](#decrement)|指定した変数の値を減算します。 この実装はスレッド セーフではありません。|
|[CCom シングルスレッドモデル::インクリメント](#increment)|指定した変数の値をインクリメントします。 この実装はスレッド セーフではありません。|

## <a name="remarks"></a>解説

`CComSingleThreadModel`には、変数の値をインクリメントおよびデクリメントするためのメソッドが用意されています。 [これらのメソッドはスレッド](../../atl/reference/ccommultithreadmodel-class.md)セーフではありません[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)。

通常は`CComSingleThreadModel`[、2](atl-typedefs.md#ccomobjectthreadmodel)つの**タイプ定義**名のいずれかを[使用します。](atl-typedefs.md#ccomglobalsthreadmodel) 各**typedef**によって参照されるクラスは、次の表に示すように、使用されるスレッド モデルによって異なります。

|Typedef|シングル スレッド モデル|アパートメント スレッド モデル|フリー スレッド モデル|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S= `CComSingleThreadModel`;M=`CComMultiThreadModel`

`CComSingleThreadModel`それ自体は 3 つの**型定義名を**定義します。 `ThreadModelNoCS`参照`CComSingleThreadModel`。 `AutoCriticalSection`および`CriticalSection`参照クラス[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)は、クリティカル セクションの所有権の取得と解放に関連付けられた空のメソッドを提供します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomsinglethreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComシングルスレッドモデル::オートクリティカルセクション

を使用`CComSingleThreadModel`する場合 **、typedef**名`AutoCriticalSection`はクラス[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>解説

クリティカル`CComFakeCriticalSection`セクションを提供しないため、そのメソッドは何も実行しません。

[の定義が](../../atl/reference/ccommultithreadmodel-class.md)含まれています。 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) `AutoCriticalSection` スレッド モデル クラスと、 で参照されるクリティカル セクション クラスの関係を次`AutoCriticalSection`の表に示します。

|で定義されたクラス|参照されるクラス|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

また`AutoCriticalSection`、**タイプ定義**名の[CriticalSection](#criticalsection)を使用することもできます。 CRT スタートアップ`AutoCriticalSection`コードを削除する場合は、グローバル オブジェクトまたは静的クラス メンバーで指定しないでください。

### <a name="example"></a>例

[「CCom マルチスレッドモデル::オートクリティカルセクション](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="ccomsinglethreadmodelcriticalsection"></a><a name="criticalsection"></a>CComシングルスレッドモデル::クリティカルセクション

を使用`CComSingleThreadModel`する場合 **、typedef**名`CriticalSection`はクラス[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)を参照します。

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>解説

クリティカル`CComFakeCriticalSection`セクションを提供しないため、そのメソッドは何も実行しません。

[の定義が](../../atl/reference/ccommultithreadmodel-class.md)含まれています。 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) `CriticalSection` スレッド モデル クラスと、 で参照されるクリティカル セクション クラスの関係を次`CriticalSection`の表に示します。

|で定義されたクラス|参照されるクラス|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

また`CriticalSection`、**型定義**名[の自動臨界セクション](#autocriticalsection)を使用することもできます。 CRT スタートアップ`AutoCriticalSection`コードを削除する場合は、グローバル オブジェクトまたは静的クラス メンバーで指定しないでください。

### <a name="example"></a>例

[「CCom マルチスレッドモデル::オートクリティカルセクション](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="ccomsinglethreadmodeldecrement"></a><a name="decrement"></a>CComシングルスレッドモデル::D

この静的関数は *、p*が指す変数の値を減算します。

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]デクリメントされる変数へのポインター。

### <a name="return-value"></a>戻り値

デクリメントの結果。

## <a name="ccomsinglethreadmodelincrement"></a><a name="increment"></a>CCom シングルスレッドモデル::インクリメント

この静的関数は *、p*が指す変数の値をインクリメントします。

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]インクリメントされる変数へのポインター。

### <a name="return-value"></a>戻り値

インクリメントの結果。

## <a name="ccomsinglethreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>を使用するモデル::スレッドモデルNoCS

を使用`CComSingleThreadModel`する場合 **、typedef** `ThreadModelNoCS`名`CComSingleThreadModel`は 単に を参照します。

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>解説

[の定義が](../../atl/reference/ccommultithreadmodel-class.md)含まれています。 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) `ThreadModelNoCS` スレッド モデル クラスと によって参照されるクラスの関係を次の表に`ThreadModelNoCS`示します。

|で定義されたクラス|参照されるクラス|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>例

[「CCom マルチスレッドモデル::オートクリティカルセクション](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
