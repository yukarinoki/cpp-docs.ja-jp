---
title: CHeapPtr クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a728f84a2eaa3f0138e2b0a95c25f8867c17432e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359944"
---
# <a name="cheapptr-class"></a>CHeapPtr クラス
ヒープのポインターを管理するためのスマート ポインター クラスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T, class Allocator=CCRTAllocator>  
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ヒープに格納されるオブジェクトの型。  
  
 `Allocator`  
 メモリの割り当ては、使用するクラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtr::CHeapPtr](#cheapptr)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtr::Allocate](#allocate)|このメソッドを呼び出してオブジェクトを格納するヒープにメモリを割り当てます。|  
|[CHeapPtr::Reallocate](#reallocate)|このメソッドを呼び出して、ヒープにメモリを再割り当てください。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtr::operator =](#operator_eq)|代入演算子です。|  
  
## <a name="remarks"></a>コメント  
 `CHeapPtr` 派生した[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) 、既定では、CRT ルーチン (で[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) を割り当てたり、メモリを解放します。 クラス[CHeapPtrList](../../atl/reference/cheapptrlist-class.md)ヒープのポインターのリストを構築するために使用することがあります。 関連項目[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)、COM メモリ割り当てルーチンを使用します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="allocate"></a>  CHeapPtr::Allocate  
 このメソッドを呼び出してオブジェクトを格納するヒープにメモリを割り当てます。  
  
```
bool Allocate(size_t nElements = 1) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nElements`  
 割り当てるメモリの量を計算するための要素の数。 既定値は 1 です。  
  
### <a name="return-value"></a>戻り値  
 失敗した場合に、メモリが正常にした場合、true を返しますが割り当てられます。  
  
### <a name="remarks"></a>コメント  
 アロケーター ルーチンを格納するヒープにメモリ不足のための予約を使用して*nElement*コンス トラクターで定義された型のオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]  
  
##  <a name="cheapptr"></a>  CHeapPtr::CHeapPtr  
 コンストラクターです。  
  
```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 既存のヒープ ポインターまたは`CHeapPtr`です。  
  
### <a name="remarks"></a>コメント  
 既存のポインターを使用して、ヒープのポインターを作成することができます必要に応じて、または`CHeapPtr`オブジェクト。 場合は、新しい`CHeapPtr`オブジェクトは、新しいポインターとリソースを管理する責任を引き継ぎます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]  
  
##  <a name="operator_eq"></a>  CHeapPtr::operator =  
 代入演算子。  
  
```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 既存の `CHeapPtr` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CHeapPtr`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]  
  
##  <a name="reallocate"></a>  CHeapPtr::Reallocate  
 このメソッドを呼び出して、ヒープにメモリを再割り当てください。  
  
```
bool Reallocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nElements`  
 新しいに割り当てるメモリの量を計算するための要素数。  
  
### <a name="return-value"></a>戻り値  
 失敗した場合に、メモリが正常にした場合、true を返しますが割り当てられます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CHeapPtrBase クラス](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator クラス](../../atl/reference/ccrtallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
