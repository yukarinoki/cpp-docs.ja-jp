---
title: CComSingleThreadModel クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 175cc1b867356949ca861f7015dedb6d64c4282f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365101"
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
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)です。|  
|[CComSingleThreadModel::CriticalSection](#criticalsection)|クラスを参照`CComFakeCriticalSection`です。|  
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|参照`CComSingleThreadModel`です。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](#decrement)|デクリメント、指定した変数の値。 この実装は、スレッド セーフではありません。|  
|[CComSingleThreadModel::Increment](#increment)|指定された変数の値をインクリメントします。 この実装は、スレッド セーフではありません。|  
  
## <a name="remarks"></a>コメント  
 `CComSingleThreadModel` インクリメントおよびデクリメントするため、変数の値に対応するメソッドを提供します。 異なり[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)、これらのメソッドはスレッド セーフではありません。  

 通常、使用して`CComSingleThreadModel`2 つのいずれかで`typedef`名か、 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)または[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)です。 各によって参照されるクラス`typedef`次の表に示すように使用される、スレッド処理モデルによって異なります。  

  
|Typedef|1 つのスレッド モデル|アパートメント スレッド モデル|フリー スレッド モデル|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S =`CComSingleThreadModel`です。M = `CComMultiThreadModel`  
  
 `CComSingleThreadModel` 3 つの定義自体`typedef`名。 `ThreadModelNoCS` 参照`CComSingleThreadModel`です。 `AutoCriticalSection` および`CriticalSection`クラスを参照して[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)、取得する、クリティカル セクションの所有権を解放すると関連付けられている空のメソッドを提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="autocriticalsection"></a>  CComSingleThreadModel::AutoCriticalSection  
 使用する場合`CComSingleThreadModel`、`typedef`名前`AutoCriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)です。  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 `CComFakeCriticalSection`クリティカル セクションの管轄外のメソッドは何も行われません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)の定義を含む`AutoCriticalSection`です。 次の表は、スレッド処理モデル クラスと、クリティカル セクションによって参照される間のリレーションシップ`AutoCriticalSection`:  
  
|定義されたクラス|参照クラス|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 加え`AutoCriticalSection`、使用することができます、`typedef`名前[CriticalSection](#criticalsection)です。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを除去したい場合に、静的クラス メンバーにします。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)です。  
  
##  <a name="criticalsection"></a>  CComSingleThreadModel::CriticalSection  
 使用する場合`CComSingleThreadModel`、`typedef`名前`CriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)です。  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 `CComFakeCriticalSection`クリティカル セクションの管轄外のメソッドは何も行われません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)の定義を含む`CriticalSection`です。 次の表は、スレッド処理モデル クラスと、クリティカル セクションによって参照される間のリレーションシップ`CriticalSection`:  
  
|定義されたクラス|参照クラス|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 加え`CriticalSection`、使用することができます、`typedef`名前[AutoCriticalSection](#autocriticalsection)です。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを除去したい場合に、静的クラス メンバーにします。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)です。  
  
##  <a name="decrement"></a>  CComSingleThreadModel::Decrement  
 この静的関数デクリメント、変数の値によって示される`p`です。  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]デクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 減算の結果。  
  
##  <a name="increment"></a>  CComSingleThreadModel::Increment  
 この静的関数デクリメント、変数の値によって示される`p`です。  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]インクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 増分値の結果。  
  
##  <a name="threadmodelnocs"></a>  CComSingleThreadModel::ThreadModelNoCS  
 使用する場合`CComSingleThreadModel`、`typedef`名前`ThreadModelNoCS`単に参照`CComSingleThreadModel`です。  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>コメント  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)の定義を含む`ThreadModelNoCS`です。 次の表は、スレッド処理モデル クラスとによって参照されるクラスの関係を示しています`ThreadModelNoCS`:。  
  
|定義されたクラス|参照クラス|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
