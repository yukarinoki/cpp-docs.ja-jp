---
title: CComMultiThreadModelNoCS クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 758811b10757cd7903b4f1d6218a5f34f8a98462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS クラス
`CComMultiThreadModelNoCS` クリティカル セクションをロックまたはロック解除機能せず、スレッド セーフであるメソッドを変数の値インクリメントおよびデクリメントするために提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComMultiThreadModelNoCS
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)です。|  
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|クラスを参照`CComFakeCriticalSection`です。|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|クラスを参照`CComMultiThreadModelNoCS`です。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(静的)デクリメント、スレッド セーフな方法で指定された変数の値。|  
|[CComMultiThreadModelNoCS::Increment](#increment)|(静的)スレッド セーフな方法で指定された変数の値をインクリメントします。|  
  
## <a name="remarks"></a>コメント  
 `CComMultiThreadModelNoCS` ような[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を提供するスレッド セーフであるメソッド インクリメントおよびデクリメントの変数です。 ただし、を通じてクリティカル セクション クラスを参照する`CComMultiThreadModelNoCS`などのメソッド`Lock`と`Unlock`何も実行されません。  
  
 通常、使用して`CComMultiThreadModelNoCS`を通じて、 `ThreadModelNoCS` `typedef`名。 これは、`typedef`で定義された`CComMultiThreadModelNoCS`、 `CComMultiThreadModel`、および[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)です。  
  
> [!NOTE]
>  グローバル`typedef`名[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)と[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)参照しない`CComMultiThreadModelNoCS`です。  
  
 加え`ThreadModelNoCS`、`CComMultiThreadModelNoCS`定義`AutoCriticalSection`と`CriticalSection`です。 この後者の 2 つ`typedef`名前参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)、取得と解放する、クリティカル セクションに関連付けられている空のメソッドを提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="autocriticalsection"></a>  CComMultiThreadModelNoCS::AutoCriticalSection  
 使用する場合`CComMultiThreadModelNoCS`、`typedef`名前`AutoCriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)です。  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 `CComFakeCriticalSection`クリティカル セクションの管轄外のメソッドは何も行われません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)もの定義を含む`AutoCriticalSection`です。 次の表は、スレッド処理モデル クラスと、クリティカル セクションによって参照される間のリレーションシップ`AutoCriticalSection`:  
  
|定義されたクラス|参照クラス|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 加え`AutoCriticalSection`、使用することができます、`typedef`名前[CriticalSection](#criticalsection)です。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを除去したい場合に、静的クラス メンバーにします。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)です。  
  
##  <a name="criticalsection"></a>  CComMultiThreadModelNoCS::CriticalSection  
 使用する場合`CComMultiThreadModelNoCS`、`typedef`名前`CriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)です。  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 `CComFakeCriticalSection`クリティカル セクションの管轄外のメソッドは何も行われません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)もの定義を含む`CriticalSection`です。 次の表は、スレッド処理モデル クラスと、クリティカル セクションによって参照される間のリレーションシップ`CriticalSection`:  
  
|定義されたクラス|参照クラス|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 加え`CriticalSection`、使用することができます、`typedef`名前`AutoCriticalSection`です。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを除去したい場合に、静的クラス メンバーにします。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)です。  
  
##  <a name="decrement"></a>  CComMultiThreadModelNoCS::Decrement  
 この静的関数は、Win32 関数を呼び出す[InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580)、変数の値を指すどのデクリメント`p`です。  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]デクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 減算の結果が 0 の場合、 `Decrement` 0 を返します。 減算の結果が 0 以外の場合、戻り値も 0 以外の値が減算の結果が等しくない場合があります。  
  
### <a name="remarks"></a>コメント  
 **InterlockedDecrement**複数のスレッドが同時にこの変数を使用することを防止します。  
  
##  <a name="increment"></a>  CComMultiThreadModelNoCS::Increment  
 この静的関数は、Win32 関数を呼び出す[InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614)が指す変数の値をインクリメントする`p`です。  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]インクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 かどうか、増分の結果は 0、し**インクリメント**0 を返します。 増分値の結果が 0 以外の場合、戻り値も 0 以外の値がインクリメントの結果が等しくない場合があります。  
  
### <a name="remarks"></a>コメント  
 **InterlockedIncrement**複数のスレッドが同時にこの変数を使用することを防止します。  
  
##  <a name="threadmodelnocs"></a>  CComMultiThreadModelNoCS::ThreadModelNoCS  
 使用する場合`CComMultiThreadModelNoCS`、`typedef`名前`ThreadModelNoCS`単に参照`CComMultiThreadModelNoCS`です。  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>コメント  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)もの定義を含む`ThreadModelNoCS`です。 次の表は、スレッド処理モデル クラスとによって参照されるクラスの関係を示しています`ThreadModelNoCS`:。  
  
|定義されたクラス|参照クラス|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 なおの定義`ThreadModelNoCS`で`CComMultiThreadModelNoCS`との対称性を提供`CComMultiThreadModel`と`CComSingleThreadModel`です。 たとえば、サンプル コードに`CComMultiThreadModel::AutoCriticalSection`、次の宣言`typedef`:  
  
 [!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 指定されたクラスに関係なく`ThreadModel`(など`CComMultiThreadModelNoCS`)、`_ThreadModel`それに応じて解決します。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)