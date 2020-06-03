---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
ms.openlocfilehash: 7ef803439d2d683633e8f9c00810542dd787541e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327670"
---
# <a name="ccommultithreadmodel-class"></a>クラス

`CComMultiThreadModel`には、変数の値をインクリメントおよびデクリメントするためのスレッド セーフなメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CComMultiThreadModel
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CComマルチスレッドモデル::オートクリティカルセクション](#autocriticalsection)|クラス[CCom オートクリティカルセクション を参照します](../../atl/reference/ccomautocriticalsection-class.md)。|
|[CComマルチスレッドモデル::クリティカルセクション](#criticalsection)|クラス[CCom クリティカルセクション を参照](../../atl/reference/ccomcriticalsection-class.md)します。|
|[::スレッドモデルNoCS](#threadmodelnocs)|クラス[を](../../atl/reference/ccommultithreadmodelnocs-class.md)参照します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コムマルチスレッドモデル::D](#decrement)|(静的)指定した変数の値をスレッド セーフな方法でデクリメントします。|
|[CCom マルチスレッドモデル::インクリメント](#increment)|(静的)スレッド セーフな方法で、指定した変数の値をインクリメントします。|

## <a name="remarks"></a>解説

通常、2`CComMultiThreadModel`つの**タイプ定義**名のいずれかを使用します。 各**typedef**によって参照されるクラスは、次の表に示すように、使用されるスレッド モデルによって異なります。

|Typedef|シングル スレッド|アパートメントスレッド|フリー スレッド|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S= `CComSingleThreadModel`;M=`CComMultiThreadModel`

`CComMultiThreadModel`それ自体は 3 つの**型定義名を**定義します。 `AutoCriticalSection`クリティカル`CriticalSection`セクションの所有権を取得および解放するためのメソッドを提供するクラスを参照します。 `ThreadModelNoCS`クラスを参照します 。[Ccom マルチスレッドモデルノク-class.md)。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccommultithreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComマルチスレッドモデル::オートクリティカルセクション

を使用`CComMultiThreadModel`する場合 **、typedef**名`AutoCriticalSection`はクラス[CComAutoCriticalSection](ccomautocriticalsection-class.md)を参照します。

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>解説

[CCom シングルスレッドモデル](ccomsinglethreadmodel-class.md)と[CCom マルチスレッドモデルNoCS](ccommultithreadmodelnocs-class.md) `AutoCriticalSection`には、 の定義も含まれています。 スレッド モデル クラスと、 で参照されるクリティカル セクション クラスの関係を次`AutoCriticalSection`の表に示します。

|で定義されたクラス|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

また`AutoCriticalSection`、**タイプ定義**名の[CriticalSection](#criticalsection)を使用することもできます。 CRT スタートアップ`AutoCriticalSection`コードを削除する場合は、グローバル オブジェクトまたは静的クラス メンバーで指定しないでください。

### <a name="example"></a>例

次のコードは[、CComObjectRootEx](ccomobjectrootex-class.md)をモデル化し、`AutoCriticalSection`スレッド処理環境で使用される例を示しています。

```cpp
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```

次の表は`InternalAddRef`、`Lock``ThreadModel`テンプレート パラメーターとアプリケーションで使用されるスレッド モデルに応じて、メソッドとメソッドの結果を示しています。

### <a name="threadmodel--ccomobjectthreadmodel"></a>スレッドモデル = CComオブジェクトスレッドモデル

|Method|シングルまたはアパートメント スレッド|フリー スレッド|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|インクリメントはスレッド セーフではありません。|インクリメントはスレッド セーフです。|
|`Lock`|何もしません。ロックするクリティカル セクションはありません。|クリティカル セクションがロックされています。|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>スレッドモデル = CComオブジェクトスレッドモデル::スレッドモデルNoCS

|Method|シングルまたはアパートメント スレッド|フリー スレッド|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|インクリメントはスレッド セーフではありません。|インクリメントはスレッド セーフです。|
|`Lock`|何もしません。ロックするクリティカル セクションはありません。|何もしません。ロックするクリティカル セクションはありません。|

## <a name="ccommultithreadmodelcriticalsection"></a><a name="criticalsection"></a>CComマルチスレッドモデル::クリティカルセクション

を使用`CComMultiThreadModel`する場合 **、typedef**名`CriticalSection`はクラス[CComCriticalSection](ccomcriticalsection-class.md)を参照します。

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>解説

[CCom シングルスレッドモデル](ccomsinglethreadmodel-class.md)と[CCom マルチスレッドモデルNoCS](ccommultithreadmodelnocs-class.md) `CriticalSection`には、 の定義も含まれています。 スレッド モデル クラスと、 で参照されるクリティカル セクション クラスの関係を次`CriticalSection`の表に示します。

|で定義されたクラス|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

また`CriticalSection`、**型定義**名[の自動臨界セクション](#autocriticalsection)を使用することもできます。 CRT スタートアップ`AutoCriticalSection`コードを削除する場合は、グローバル オブジェクトまたは静的クラス メンバーで指定しないでください。

### <a name="example"></a>例

[「CCom マルチスレッドモデル::オートクリティカルセクション](#autocriticalsection)」を参照してください。

## <a name="ccommultithreadmodeldecrement"></a><a name="decrement"></a>コムマルチスレッドモデル::D

この静的関数は *、Win32*関数[InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)を呼び出し、p が指す変数の値をデクリメントします。

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]デクリメントされる変数へのポインター。

### <a name="return-value"></a>戻り値

デクリメントの結果が 0 の場合は`Decrement`、0 を返します。 デクリメントの結果が 0 以外の場合、戻り値も 0 以外ですが、減分の結果と等しくない可能性があります。

### <a name="remarks"></a>解説

`InterlockedDecrement`複数のスレッドがこの変数を同時に使用するのを防ぎます。

## <a name="ccommultithreadmodelincrement"></a><a name="increment"></a>CCom マルチスレッドモデル::インクリメント

この静的関数は *、Win32*関数[InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)を呼び出し、p が指す変数の値をインクリメントします。

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]インクリメントされる変数へのポインター。

### <a name="return-value"></a>戻り値

増分の結果が 0 の場合は`Increment`、0 を返します。 増分の結果が 0 以外の場合、戻り値も 0 以外の値になりますが、増分の結果と等しくない可能性があります。

### <a name="remarks"></a>解説

`InterlockedIncrement`複数のスレッドがこの変数を同時に使用するのを防ぎます。

## <a name="ccommultithreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>::スレッドモデルNoCS

を使用`CComMultiThreadModel`する場合、**型定義**名`ThreadModelNoCS`はクラス[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)を参照します。

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>解説

`CComMultiThreadModelNoCS`変数をインクリメントおよびデクリメントするためのスレッド セーフメソッドを提供します。ただし、クリティカル セクションは提供されません。

[の](ccomsinglethreadmodel-class.md)定義`CComMultiThreadModelNoCS`も含まれています`ThreadModelNoCS`。 スレッド モデル クラスと によって参照されるクラスの関係を次の表に`ThreadModelNoCS`示します。

|で定義されたクラス|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>例

[「CCom マルチスレッドモデル::オートクリティカルセクション](#autocriticalsection)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスを 1 つ追加します。](ccomsinglethreadmodel-class.md)<br/>
[クラスの自動変換クラス](ccomautocriticalsection-class.md)<br/>
[クラス](ccomcriticalsection-class.md)<br/>
[クラスの概要](../atl-class-overview.md)
