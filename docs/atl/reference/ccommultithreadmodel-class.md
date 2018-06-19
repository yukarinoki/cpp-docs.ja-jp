---
title: CComMultiThreadModel クラス |Microsoft ドキュメント
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
ms.openlocfilehash: a89af8507150ee708ad381be2d47201c9266f763
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364550"
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel クラス
`CComMultiThreadModel` インクリメントおよびデクリメントするため、変数の値に対応するスレッド セーフであるメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComMultiThreadModel
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|クラスを参照[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)です。|  
|[CComMultiThreadModel::CriticalSection](#criticalsection)|クラスを参照[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)です。|  
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|クラスを参照[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)です。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModel::Decrement](#decrement)|(静的)デクリメント、スレッド セーフな方法で指定された変数の値。|  
|[CComMultiThreadModel::Increment](#increment)|(静的)スレッド セーフな方法で指定された変数の値をインクリメントします。|  
  
## <a name="remarks"></a>コメント  
 通常、使用して`CComMultiThreadModel`2 つのいずれかで`typedef`[CComObjectThreadModel] の名前 (atl typedefs.md #ccomobjectthreadmodel または [CComGlobalsThreadModel] (atl typedefs.md #ccomglobalsthreadmodel です。 各によって参照されるクラス`typedef`次の表に示すように使用される、スレッド処理モデルによって異なります。  
  
|Typedef|シングル スレッド|アパートメント スレッド|フリー スレッド|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S =`CComSingleThreadModel`です。M = `CComMultiThreadModel`  
  
 `CComMultiThreadModel` 3 つの定義自体`typedef`名。 `AutoCriticalSection` および`CriticalSection`を取得し、クリティカル セクションの所有権を解放するためのメソッドを提供するクラスを参照します。 `ThreadModelNoCS` 参照クラス [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md) です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="autocriticalsection"></a>  CComMultiThreadModel::AutoCriticalSection  
 使用する場合`CComMultiThreadModel`、`typedef`名前`AutoCriticalSection`クラスを参照[CComAutoCriticalSection](ccomautocriticalsection-class.md)の取得と、クリティカル セクション オブジェクトの所有権を解放するメソッドを提供します。  
  
```
typedef CComAutoCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md)と[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)もの定義を含む`AutoCriticalSection`です。 次の表は、スレッド処理モデル クラスと、クリティカル セクションによって参照される間のリレーションシップ`AutoCriticalSection`:  
  
|定義されたクラス|参照クラス|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 加え`AutoCriticalSection`、使用することができます、`typedef`名前[CriticalSection](#criticalsection)です。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを除去したい場合に、静的クラス メンバーにします。  
  
### <a name="example"></a>例  
 次のコードは、後にモデル化されて[CComObjectRootEx](ccomobjectrootex-class.md)、および例示します`AutoCriticalSection`スレッド環境で使用されています。  
  

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
  
 次の表の結果を表示する、`InternalAddRef`と`Lock`メソッド、に応じて、**表**テンプレート パラメーターと、アプリケーションで使用されるスレッド モデル。  
  
### <a name="threadmodel--ccomobjectthreadmodel"></a>表 CComObjectThreadModel を =  
  
|メソッド|1 つまたはアパートメント スレッド|フリー スレッド|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|増分値がスレッド セーフです。|増分値は、スレッド セーフです。|  
|`Lock`|何も実行します。クリティカル セクションをロックすることはありません。|クリティカル セクションがロックされています。|  
  
### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>表 CComObjectThreadModel::ThreadModelNoCS を =  
  
|メソッド|1 つまたはアパートメント スレッド|フリー スレッド|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|増分値がスレッド セーフです。|増分値は、スレッド セーフです。|  
|`Lock`|何も実行します。クリティカル セクションをロックすることはありません。|何も実行します。クリティカル セクションをロックすることはありません。|  
  
##  <a name="criticalsection"></a>  CComMultiThreadModel::CriticalSection  
 使用する場合`CComMultiThreadModel`、`typedef`名前`CriticalSection`クラスを参照[CComCriticalSection](ccomcriticalsection-class.md)の取得と、クリティカル セクション オブジェクトの所有権を解放するメソッドを提供します。  
  
```
typedef CComCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md)と[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)もの定義を含む`CriticalSection`です。 次の表は、スレッド処理モデル クラスと、クリティカル セクションによって参照される間のリレーションシップ`CriticalSection`:  
  
|定義されたクラス|参照クラス|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 加え`CriticalSection`、使用することができます、`typedef`名前[AutoCriticalSection](#autocriticalsection)です。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを除去したい場合に、静的クラス メンバーにします。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)です。  
  
##  <a name="decrement"></a>  CComMultiThreadModel::Decrement  
 この静的関数は、Win32 関数を呼び出す[InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580)、変数の値を指すどのデクリメント`p`です。  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]デクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 減算の結果が 0 の場合、 `Decrement` 0 を返します。 減算の結果が 0 以外の場合、戻り値も 0 以外の値が減算の結果が等しくない場合があります。  
  
### <a name="remarks"></a>コメント  
 **InterlockedDecrement**複数のスレッドが同時にこの変数を使用することを防止します。  
  
##  <a name="increment"></a>  CComMultiThreadModel::Increment  
 この静的関数は、Win32 関数を呼び出す[InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614)が指す変数の値をインクリメントする`p`です。  
  
```
static ULONG WINAPI Increment(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]インクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 かどうか、増分の結果は 0、し**インクリメント**0 を返します。 増分値の結果が 0 以外の場合、戻り値も 0 以外の値がインクリメントの結果が等しくない場合があります。  
  
### <a name="remarks"></a>コメント  
 **InterlockedIncrement**複数のスレッドが同時にこの変数を使用することを防止します。  
  
##  <a name="threadmodelnocs"></a>  CComMultiThreadModel::ThreadModelNoCS  
 使用する場合`CComMultiThreadModel`、`typedef`名前`ThreadModelNoCS`クラスを参照[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)です。  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>コメント  
 `CComMultiThreadModelNoCS` スレッド セーフであるメソッドを提供インクリメントおよびデクリメント変数です。ただし、クリティカル セクションは行いません。  
  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md)と`CComMultiThreadModelNoCS`もの定義を含む`ThreadModelNoCS`です。 次の表は、スレッド処理モデル クラスとによって参照されるクラスの関係を示しています`ThreadModelNoCS`:。  
  
|定義されたクラス|参照クラス|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)です。  
  
## <a name="see-also"></a>関連項目  
 [CComSingleThreadModel クラス](ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection クラス](ccomautocriticalsection-class.md)   
 [CComCriticalSection クラス](ccomcriticalsection-class.md)   
 [クラスの概要](../atl-class-overview.md)
