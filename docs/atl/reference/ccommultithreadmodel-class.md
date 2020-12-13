---
description: '詳細情報: CComMultiThreadModel クラス'
title: CComMultiThreadModel クラス
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
ms.openlocfilehash: 705709e18d91714cca8eb3a5cb365ac9f6a9a90b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146563"
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel クラス

`CComMultiThreadModel` 変数の値をインクリメントおよびデクリメントするためのスレッドセーフなメソッドを提供します。

## <a name="syntax"></a>構文

```
class CComMultiThreadModel
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)クラスを参照します。|
|[CComMultiThreadModel:: CriticalSection](#criticalsection)|[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)クラスを参照します。|
|[CComMultiThreadModel:: ThreadModelNoCS](#threadmodelnocs)|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)クラスを参照します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComMultiThreadModel::D ecrement](#decrement)|雑音指定された変数の値をスレッドセーフな方法でデクリメントします。|
|[CComMultiThreadModel:: Increment](#increment)|雑音指定された変数の値をスレッドセーフな方法でインクリメントします。|

## <a name="remarks"></a>解説

通常、を使用するには `CComMultiThreadModel` **`typedef`** 、[CComObjectThreadModel] (atl-typedef. md # CComObjectThreadModel または [CComGlobalsThreadModel] (atl-typedef # CComGlobalsThreadModel) のいずれかの名前を使用します。 によって参照されるクラスは、 **`typedef`** 次の表に示すように、使用されるスレッドモデルによって異なります。

|Typedef|単一スレッド|アパートメントスレッド|フリースレッド|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel` ;M = `CComMultiThreadModel`

`CComMultiThreadModel` は、3つ **`typedef`** の名前を定義します。 `AutoCriticalSection``CriticalSection`クリティカルセクションの所有権を取得および解放するためのメソッドを提供するリファレンスクラス。 `ThreadModelNoCS` references クラス [CComMultiThreadModelNoCS (CComMultiThreadModelNoCS-class.md)。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="ccommultithreadmodelautocriticalsection"></a><a name="autocriticalsection"></a> CComMultiThreadModel::AutoCriticalSection

を使用する場合 `CComMultiThreadModel` 、 **`typedef`** 名前は `AutoCriticalSection` クラス [CComAutoCriticalSection](ccomautocriticalsection-class.md)を参照します。これは、クリティカルセクションオブジェクトの所有権を取得および解放するためのメソッドを提供します。

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>解説

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) と [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) には、の定義も含まれて `AutoCriticalSection` います。 次の表は、スレッドモデルクラスと、によって参照されるクリティカルセクションクラスとの関係を示してい `AutoCriticalSection` ます。

|クラスの定義|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

に加え `AutoCriticalSection` て、CriticalSection という名前を使用することもでき **`typedef`** ます。 [](#criticalsection) `AutoCriticalSection`CRT スタートアップコードを削除する場合は、グローバルオブジェクトまたは静的クラスメンバーにを指定しないでください。

### <a name="example"></a>例

次のコードは、 [CComObjectRootEx](ccomobjectrootex-class.md)の後にモデル化されており、 `AutoCriticalSection` スレッド環境で使用されています。

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

次の表は、 `InternalAddRef` `Lock` `ThreadModel` テンプレートパラメーターと、アプリケーションで使用されるスレッドモデルに応じて、メソッドとメソッドの結果を示しています。

### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel = CComObjectThreadModel

|Method|シングルスレッドまたはアパートメントスレッド|フリースレッド|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|インクリメントはスレッドセーフではありません。|インクリメントはスレッドセーフです。|
|`Lock`|何も行いません。ロックする重要なセクションがありません。|クリティカルセクションがロックされています。|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel = CComObjectThreadModel:: ThreadModelNoCS

|Method|シングルスレッドまたはアパートメントスレッド|フリースレッド|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|インクリメントはスレッドセーフではありません。|インクリメントはスレッドセーフです。|
|`Lock`|何も行いません。ロックする重要なセクションがありません。|何も行いません。ロックする重要なセクションがありません。|

## <a name="ccommultithreadmodelcriticalsection"></a><a name="criticalsection"></a> CComMultiThreadModel:: CriticalSection

を使用する場合 `CComMultiThreadModel` 、 **`typedef`** 名前は `CriticalSection` クラス [CComCriticalSection](ccomcriticalsection-class.md)を参照します。これは、クリティカルセクションオブジェクトの所有権を取得および解放するためのメソッドを提供します。

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>解説

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) と [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) には、の定義も含まれて `CriticalSection` います。 次の表は、スレッドモデルクラスと、によって参照されるクリティカルセクションクラスとの関係を示してい `CriticalSection` ます。

|クラスの定義|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

に加え `CriticalSection` て、AutoCriticalSection という名前を使用することもでき **`typedef`** ます。 [](#autocriticalsection) `AutoCriticalSection`CRT スタートアップコードを削除する場合は、グローバルオブジェクトまたは静的クラスメンバーにを指定しないでください。

### <a name="example"></a>例

「 [CComMultiThreadModel:: AutoCriticalSection](#autocriticalsection)」を参照してください。

## <a name="ccommultithreadmodeldecrement"></a><a name="decrement"></a> CComMultiThreadModel::D ecrement

この静的関数は、Win32 関数 [InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)を呼び出します。これにより、 *p* が指す変数の値が減少します。

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
からデクリメントする変数へのポインター。

### <a name="return-value"></a>戻り値

デクリメントの結果が0の場合、は `Decrement` 0 を返します。 デクリメントの結果が0以外の場合、戻り値も0以外になりますが、デクリメントの結果と一致しない可能性があります。

### <a name="remarks"></a>解説

`InterlockedDecrement` 複数のスレッドがこの変数を同時に使用できないようにします。

## <a name="ccommultithreadmodelincrement"></a><a name="increment"></a> CComMultiThreadModel:: Increment

この静的関数は、Win32 関数 [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)を呼び出します。これにより、 *p* が指す変数の値がインクリメントされます。

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
からインクリメントする変数へのポインター。

### <a name="return-value"></a>戻り値

インクリメントの結果が0の場合、は `Increment` 0 を返します。 インクリメントの結果が0以外の場合、戻り値も0以外になりますが、インクリメントの結果と一致しない可能性があります。

### <a name="remarks"></a>解説

`InterlockedIncrement` 複数のスレッドがこの変数を同時に使用できないようにします。

## <a name="ccommultithreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a> CComMultiThreadModel:: ThreadModelNoCS

を使用する場合 `CComMultiThreadModel` 、 **`typedef`** 名前は `ThreadModelNoCS` クラス [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)を参照します。

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>解説

`CComMultiThreadModelNoCS` 変数をインクリメントおよびデクリメントするためのスレッドセーフなメソッドを提供します。ただし、クリティカルセクションは提供されません。

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) と `CComMultiThreadModelNoCS` には、の定義も含まれて `ThreadModelNoCS` います。 次の表は、スレッドモデルクラスとによって参照されるクラスの関係を示してい `ThreadModelNoCS` ます。

|クラスの定義|参照されるクラス|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>例

「 [CComMultiThreadModel:: AutoCriticalSection](#autocriticalsection)」を参照してください。

## <a name="see-also"></a>関連項目

[CComSingleThreadModel クラス](ccomsinglethreadmodel-class.md)<br/>
[CComAutoCriticalSection クラス](ccomautocriticalsection-class.md)<br/>
[CComCriticalSection クラス](ccomcriticalsection-class.md)<br/>
[クラスの概要](../atl-class-overview.md)
