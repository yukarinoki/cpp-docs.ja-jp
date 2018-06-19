---
title: CHeapPtrList クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc5b164fda27775a7b3fb272d8718c31815cb1ca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358816"
---
# <a name="cheapptrlist-class"></a>CHeapPtrList クラス
このクラスは、ヒープのポインターのリストを構築するときに役立つメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<typename E, class Allocator = ATL::CCRTAllocator>  
class CHeapPtrList 
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```  
  
#### <a name="parameters"></a>パラメーター  
 `E`  
 コレクション クラスに格納されるオブジェクトの型。  
  
 `Allocator`  
 メモリの割り当ては、使用するクラス。 既定値は[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|コンストラクターです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、コンス トラクターを提供し、メソッドからの派生[CAtlList](../../atl/reference/catllist-class.md)と[CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)ヒープ ポインターを格納するコレクション クラスのオブジェクトの作成を支援するためにします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CHeapPtrList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="cheapptrlist"></a>  CHeapPtrList::CHeapPtrList  
 コンストラクターです。  
  
```
CHeapPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 ブロック サイズ。  
  
### <a name="remarks"></a>コメント  
 ブロック サイズは、新しい要素が必要な場合に割り当てられたメモリの量の測定です。 ブロック サイズを大きくはメモリ割り当てルーチンに呼び出しを減らすことより多くのリソースを使用します。  
  
## <a name="see-also"></a>関連項目  
 [CAtlList クラス](../../atl/reference/catllist-class.md)   
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits クラス](../../atl/reference/cheapptrelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
