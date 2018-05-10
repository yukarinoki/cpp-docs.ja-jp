---
title: CHeapPtrBase クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ca18054509ab069722e632308b4d8f57706e548
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase クラス
このクラスは、いくつかのヒープのスマート ポインター クラスの基礎を形成します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class Allocator = CCRTAllocator>  
class CHeapPtrBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ヒープに格納されるオブジェクトの型。  
  
 `Allocator`  
 メモリの割り当ては、使用するクラス。 既定では、CRT ルーチンは、解放し、メモリに使用されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|メモリを割り当てるには、このメソッドを呼び出します。|  
|[CHeapPtrBase::Attach](#attach)|このメソッドを呼び出して既存のポインターの所有権を取得します。|  
|[CHeapPtrBase::Detach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|  
|[CHeapPtrBase::Free](#free)|指すオブジェクトを削除するには、このメソッドを呼び出して、`CHeapPtrBase`です。|  
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|このメソッドを呼び出してメモリを再割り当てください。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrBase::operator T *](#operator_t_star)|キャスト演算子です。|  
|[CHeapPtrBase::operator (& a)](#operator_amp)|(& A) 演算子。|  
|[CHeapPtrBase::operator -> します。](#operator_ptr)|メンバーへのポインター演算子です。|  

  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrBase::m_pData](#m_pdata)|ポインターのデータ メンバー変数です。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、いくつかのヒープのスマート ポインター クラスの基礎を形成します。 たとえば、派生クラス[CHeapPtr](../../atl/reference/cheapptr-class.md)と[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)、コンス トラクターと演算子を追加します。 これらのクラスの実装例を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="allocatebytes"></a>  CHeapPtrBase::AllocateBytes  
 メモリを割り当てるには、このメソッドを呼び出します。  
  
```
bool AllocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 割り当てるメモリのバイト数。  
  
### <a name="return-value"></a>戻り値  
 True を返しますが、正常にメモリ割り当て、false それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、アサーション場合にエラーが発生、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数は、現在、既存の値を指します。 つまり、null はありません。  
  
##  <a name="attach"></a>  CHeapPtrBase::Attach  
 このメソッドを呼び出して既存のポインターの所有権を取得します。  
  
```
void Attach(T* pData) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pData`  
 `CHeapPtrBase` This ポインターの所有権を持つオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ときに、`CHeapPtrBase`オブジェクト ポインターの所有権は自動的に削除ポインターと、割り当てられているデータ スコープ外になったときにします。  
  
 デバッグ ビルドで、アサーション場合にエラーが発生、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数は、現在、既存の値を指します。 つまり、null はありません。  
  
##  <a name="dtor"></a>  CHeapPtrBase:: ~ CHeapPtrBase  
 デストラクターです。  
  
```
~CHeapPtrBase() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="detach"></a>  CHeapPtrBase::Detach  
 ポインターの所有権を解放するには、このメソッドを呼び出します。  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターのコピーを返します。  
  
### <a name="remarks"></a>コメント  
 ポインターの所有権を解放、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数に NULL の場合、ポインターのコピーを返します。  
  
##  <a name="free"></a>  CHeapPtrBase::Free  
 指すオブジェクトを削除するには、このメソッドを呼び出して、`CHeapPtrBase`です。  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>コメント  
 によって指されるオブジェクト、`CHeapPtrBase`が解放され、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数が NULL に設定します。  
  
##  <a name="m_pdata"></a>  CHeapPtrBase::m_pData  
 ポインターのデータ メンバー変数です。  
  
```
T* m_pData;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー変数は、ポインターの情報を保持します。  
  
##  <a name="operator_amp"></a>  CHeapPtrBase::operator &amp;  
 (& A) 演算子。  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>戻り値  
 によって指されるオブジェクトのアドレスを返します、`CHeapPtrBase`オブジェクト。  
  

##  <a name="operator_ptr"></a>  CHeapPtrBase::operator-&gt;  

 メンバーへのポインター演算子です。  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 値を返します、 [CHeapPtrBase::m_pData](#m_pdata)メンバー変数。  
  
### <a name="remarks"></a>コメント  
 この演算子によって示されるクラスのメソッドを呼び出すを使用して、`CHeapPtrBase`オブジェクト。 デバッグ ビルドで、アサーション場合にエラーが発生、 `CHeapPtrBase` NULL を指します。  
  
##  <a name="operator_t_star"></a>  CHeapPtrBase::operator T *  
 キャスト演算子です。  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します[CHeapPtrBase::m_pData](#m_pdata)です。  
  
##  <a name="reallocatebytes"></a>  CHeapPtrBase::ReallocateBytes  
 このメソッドを呼び出してメモリを再割り当てください。  
  
```
bool ReallocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 新しいメモリ量割り当てるには、(バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 True を返しますが、正常にメモリ割り当て、false それ以外の場合。  
  
## <a name="see-also"></a>関連項目  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr クラス](../../atl/reference/ccomheapptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
