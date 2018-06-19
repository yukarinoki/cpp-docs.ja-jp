---
title: CComPtr クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
dev_langs:
- C++
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5254e463050d685840ff90334ecbdb94372f27ef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358541"
---
# <a name="ccomptr-class"></a>CComPtr クラス
COM インターフェイス ポインターを管理するためのスマート ポインター クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class CComPtr
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 格納するポインターの種類を指定する COM インターフェイスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComPtr::CComPtr](#ccomptr)|コンストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComPtr::operator =](#operator_eq)|メンバーのポインターにポインターを割り当てます。|  
  
## <a name="remarks"></a>コメント  
 ATL を使用して`CComPtr`と[CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM インターフェイス ポインターを管理します。 派生されます両方[CComPtrBase](../../atl/reference/ccomptrbase-class.md)、し、両方は、自動参照カウントを実行します。  
  
 **CComPtr**と[CComQIPtr](../../atl/reference/ccomqiptr-class.md)クラスは、自動参照カウントを実行することによってメモリ リークを解決できます。  次の関数は両方が同じ論理的操作を実行します。ただし、どのように 2 番目のバージョンがありますエラーの発生を使用して、 **CComPtr**クラス。  
  
 [!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]  
  
 デバッグ ビルドで、コードのトレースの atlsd.lib をリンクします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="ccomptr"></a>  CComPtr::CComPtr  
 コンストラクターです。  
  
```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `lp`  
 インターフェイス ポインターを初期化するために使用します。  
  
 `T`  
 COM インターフェイスです。  
  
##  <a name="operator_eq"></a>  CComPtr::operator =  
 代入演算子。  
  
```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```  
  
### <a name="return-value"></a>戻り値  
 更新後にポインターを返します`CComPtr`オブジェクト  
  
### <a name="remarks"></a>コメント  
 この操作 AddRefs 新しいオブジェクトをリリース 1 つの場合、既存のオブジェクトが存在します。  
  
## <a name="see-also"></a>関連項目  
 [CComPtr::CComPtr](#ccomptr)   
 [CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)   
 [クラスの概要](../../atl/atl-class-overview.md)
