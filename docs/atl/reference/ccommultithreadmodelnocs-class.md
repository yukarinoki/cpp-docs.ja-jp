---
title: CComMultiThreadModelNoCS クラス |Microsoft Docs
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
ms.openlocfilehash: 09e209a7b3e81ac232d2c0441a84e55ded8faecf
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212858"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS クラス
`CComMultiThreadModelNoCS` クリティカル セクションをロックまたはロック解除機能せず、スレッド セーフな方法を変数の値のインクリメントおよびデクリメントに提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComMultiThreadModelNoCS
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。|  
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|クラスを参照`CComFakeCriticalSection`します。|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|クラスを参照`CComMultiThreadModelNoCS`します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(静的)デクリメントをスレッド セーフ方式で指定された変数の値。|  
|[CComMultiThreadModelNoCS::Increment](#increment)|(静的)スレッド セーフな方法で指定された変数の値をインクリメントします。|  
  
## <a name="remarks"></a>Remarks  
 `CComMultiThreadModelNoCS` ような[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を提供するスレッド セーフなメソッドのインクリメントおよびデクリメント変数。 ただし、クリティカル セクションを通じてクラスを参照する`CComMultiThreadModelNoCS`などのメソッド`Lock`と`Unlock`は何も実行します。  
  
 通常、使用して`CComMultiThreadModelNoCS`を通じて、 `ThreadModelNoCS` **typedef**名。 これは、 **typedef**で定義されている`CComMultiThreadModelNoCS`、 `CComMultiThreadModel`、および[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)します。  
  
> [!NOTE]
>  グローバル**typedef**名[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)と[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)参照しない`CComMultiThreadModelNoCS`します。  
  
 ほかに`ThreadModelNoCS`、`CComMultiThreadModelNoCS`定義`AutoCriticalSection`と`CriticalSection`します。 これら後者の 2 つ**typedef**名前参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)、取得およびクリティカル セクションを解放するに関連付けられている空のメソッドを提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="autocriticalsection"></a>  CComMultiThreadModelNoCS::AutoCriticalSection  
 使用する場合`CComMultiThreadModelNoCS`、 **typedef**名前`AutoCriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Remarks  
 `CComFakeCriticalSection` 、クリティカル セクションを行いませんそのメソッドは、何もしません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)の定義を含めることも`AutoCriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクションのクラス間のリレーションシップ`AutoCriticalSection`:  
  
|クラスで定義されています。|参照クラス|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 ほかに`AutoCriticalSection`、使用することができます、 **typedef**名前[CriticalSection](#criticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを削除する場合、静的クラス メンバー。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。  
  
##  <a name="criticalsection"></a>  CComMultiThreadModelNoCS::CriticalSection  
 使用する場合`CComMultiThreadModelNoCS`、 **typedef**名前`CriticalSection`クラスを参照[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)します。  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Remarks  
 `CComFakeCriticalSection` 、クリティカル セクションを行いませんそのメソッドは、何もしません。  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)の定義を含めることも`CriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクションのクラス間のリレーションシップ`CriticalSection`:  
  
|クラスで定義されています。|参照クラス|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 ほかに`CriticalSection`、使用することができます、 **typedef**名前`AutoCriticalSection`します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは CRT スタートアップ コードを削除する場合、静的クラス メンバー。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。  
  
##  <a name="decrement"></a>  CComMultiThreadModelNoCS::Decrement  
 この静的関数は、Win32 関数を呼び出す[InterlockedDecrement](/windows/desktop/api/winbase/nf-winbase-interlockeddecrement)を指す変数の値をデクリメント*p*します。  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *p*  
 [in]デクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 減算の結果、0 の場合は、かどうか`Decrement`0 を返します。 減算の結果が 0 以外の場合、戻り値が 0 以外にもがデクリメントの結果が等しくない場合があります。  
  
### <a name="remarks"></a>Remarks  
 **InterlockedDecrement** 1 つ以上のスレッドが同時にこの変数を使用するを防ぎます。  
  
##  <a name="increment"></a>  CComMultiThreadModelNoCS::Increment  
 この静的関数は、Win32 関数を呼び出す[InterlockedIncrement](/windows/desktop/api/winbase/nf-winbase-interlockedincrement)を指す変数の値をインクリメントする*p*します。  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *p*  
 [in]インクリメントされる変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 かどうか、増分の結果は 0、し**インクリメント**0 を返します。 インクリメントの結果が 0 以外の場合、戻り値が 0 以外にもが増分の結果が等しくない場合があります。  
  
### <a name="remarks"></a>Remarks  
 **InterlockedIncrement** 1 つ以上のスレッドが同時にこの変数を使用するを防ぎます。  
  
##  <a name="threadmodelnocs"></a>  CComMultiThreadModelNoCS::ThreadModelNoCS  
 使用する場合`CComMultiThreadModelNoCS`、 **typedef**名前`ThreadModelNoCS`だけ参照`CComMultiThreadModelNoCS`します。  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Remarks  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)と[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)の定義を含めることも`ThreadModelNoCS`します。 次の表は、スレッド処理モデル クラスとによって参照されるクラス間のリレーションシップ`ThreadModelNoCS`:  
  
|クラスで定義されています。|参照クラス|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 注意の定義`ThreadModelNoCS`で`CComMultiThreadModelNoCS`対称性を提供します。`CComMultiThreadModel`と`CComSingleThreadModel`します。 たとえば、サンプル コードを`CComMultiThreadModel::AutoCriticalSection`、次の宣言**typedef**:  
  
 [!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 指定されたクラスに関係なく`ThreadModel`(など`CComMultiThreadModelNoCS`)、`_ThreadModel`それに応じて解決します。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)