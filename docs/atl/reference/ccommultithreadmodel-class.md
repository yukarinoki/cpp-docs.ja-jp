---
title: CComMultiThreadModel クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33eac78dc871dd2a9869452bc829150c3356fd0a
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754944"
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel クラス

`CComMultiThreadModel` インクリメントおよびデクリメントの変数の値に対応するスレッド セーフなメソッドを提供します。

## <a name="syntax"></a>構文

```
class CComMultiThreadModel
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|クラスを参照[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)します。|
|[CComMultiThreadModel::CriticalSection](#criticalsection)|クラスを参照[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)します。|
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|クラスを参照[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComMultiThreadModel::Decrement](#decrement)|(静的)デクリメントをスレッド セーフ方式で指定された変数の値。|
|[CComMultiThreadModel::Increment](#increment)|(静的)スレッド セーフな方法で指定された変数の値をインクリメントします。|

## <a name="remarks"></a>Remarks

通常、使用して`CComMultiThreadModel`2 つのいずれかで**typedef**名、[CComObjectThreadModel] (atl typedefs.md #ccomobjectthreadmodel または [CComGlobalsThreadModel] (atl typedefs.md #ccomglobalsthreadmodel します。 各によって参照されるクラス**typedef**次の表に示すように使用すると、スレッド処理モデルによって異なります。

|Typedef|1 つのスレッド処理|アパートメント スレッド|フリー スレッド|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`;M = `CComMultiThreadModel`

`CComMultiThreadModel` 3 つの定義自体**typedef**名。 `AutoCriticalSection` `CriticalSection`の取得と、クリティカル セクションの所有権を解放するメソッドを提供するクラスを参照します。 `ThreadModelNoCS` 参照クラス [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md) します。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase.h

##  <a name="autocriticalsection"></a>  CComMultiThreadModel::AutoCriticalSection

使用する場合`CComMultiThreadModel`、 **typedef**名前`AutoCriticalSection`クラスを参照[CComAutoCriticalSection](ccomautocriticalsection-class.md)、取得すると、クリティカル セクションの所有権を解放するメソッドを提供しますオブジェクト。

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Remarks

[CComSingleThreadModel](ccomsinglethreadmodel-class.md)と[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)の定義を含めることも`AutoCriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクションのクラス間のリレーションシップ`AutoCriticalSection`:

|クラスで定義されています。|参照クラス|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

ほかに`AutoCriticalSection`、使用することができます、 **typedef**名前[CriticalSection](#criticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを削除する場合、静的クラス メンバー。

### <a name="example"></a>例

次のコードは裏付け[CComObjectRootEx](ccomobjectrootex-class.md)、および例示します`AutoCriticalSection`スレッド環境で使用されています。

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

次の表の結果を表示する、`InternalAddRef`と`Lock`メソッド、に応じて、`ThreadModel`テンプレート パラメーターと、アプリケーションで使用されるスレッド モデル。

### <a name="threadmodel--ccomobjectthreadmodel"></a>表 CComObjectThreadModel を =

|メソッド|1 つまたはアパートメント スレッド|フリー スレッド|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|増分値はスレッド セーフではありません。|増分値は、スレッド セーフです。|
|`Lock`|何もありません。クリティカル セクションをロックすることはありません。|クリティカル セクションがロックされています。|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>表 CComObjectThreadModel::ThreadModelNoCS を =

|メソッド|1 つまたはアパートメント スレッド|フリー スレッド|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|増分値はスレッド セーフではありません。|増分値は、スレッド セーフです。|
|`Lock`|何もありません。クリティカル セクションをロックすることはありません。|何もありません。クリティカル セクションをロックすることはありません。|

##  <a name="criticalsection"></a>  CComMultiThreadModel::CriticalSection

使用する場合`CComMultiThreadModel`、 **typedef**名前`CriticalSection`クラスを参照[CComCriticalSection](ccomcriticalsection-class.md)、取得とクリティカル セクション オブジェクトの所有権を解放するメソッドを提供します。

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>Remarks

[CComSingleThreadModel](ccomsinglethreadmodel-class.md)と[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)の定義を含めることも`CriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクションのクラス間のリレーションシップ`CriticalSection`:

|クラスで定義されています。|参照クラス|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

ほかに`CriticalSection`、使用することができます、 **typedef**名前[AutoCriticalSection](#autocriticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを削除する場合、静的クラス メンバー。

### <a name="example"></a>例

参照してください[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)します。

##  <a name="decrement"></a>  CComMultiThreadModel::Decrement

この静的関数は、Win32 関数を呼び出す[InterlockedDecrement](/windows/desktop/api/winbase/nf-winbase-interlockeddecrement)を指す変数の値をデクリメント*p*します。

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>パラメーター

*p*  
[in]デクリメントする変数へのポインター。

### <a name="return-value"></a>戻り値

減算の結果、0 の場合は、かどうか`Decrement`0 を返します。 減算の結果が 0 以外の場合、戻り値が 0 以外にもがデクリメントの結果が等しくない場合があります。

### <a name="remarks"></a>Remarks

`InterlockedDecrement` 複数のスレッドが同時にこの変数を使用するを防ぎます。

##  <a name="increment"></a>  CComMultiThreadModel::Increment

この静的関数は、Win32 関数を呼び出す[InterlockedIncrement](/windows/desktop/api/winbase/nf-winbase-interlockedincrement)を指す変数の値をインクリメントする*p*します。

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>パラメーター

*p*  
[in]インクリメントされる変数へのポインター。

### <a name="return-value"></a>戻り値

かどうか、増分の結果は 0、し`Increment`0 を返します。 インクリメントの結果が 0 以外の場合、戻り値が 0 以外にもが増分の結果が等しくない場合があります。

### <a name="remarks"></a>Remarks

`InterlockedIncrement` 複数のスレッドが同時にこの変数を使用するを防ぎます。

##  <a name="threadmodelnocs"></a>  CComMultiThreadModel::ThreadModelNoCS

使用する場合`CComMultiThreadModel`、 **typedef**名前`ThreadModelNoCS`クラスを参照[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)します。

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Remarks

`CComMultiThreadModelNoCS` インクリメントおよびデクリメント; 変数のスレッド セーフであるメソッドを提供します。ただし、クリティカル セクションは行いません。

[CComSingleThreadModel](ccomsinglethreadmodel-class.md)と`CComMultiThreadModelNoCS`の定義を含めることも`ThreadModelNoCS`します。 次の表は、スレッド処理モデル クラスとによって参照されるクラス間のリレーションシップ`ThreadModelNoCS`:

|クラスで定義されています。|参照クラス|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>例

参照してください[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)します。

## <a name="see-also"></a>関連項目

[CComSingleThreadModel クラス](ccomsinglethreadmodel-class.md)   
[CComAutoCriticalSection クラス](ccomautocriticalsection-class.md)   
[CComCriticalSection クラス](ccomcriticalsection-class.md)   
[クラスの概要](../atl-class-overview.md)
