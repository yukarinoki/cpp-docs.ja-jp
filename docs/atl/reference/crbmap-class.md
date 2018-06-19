---
title: CRBMap クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b32b21c8785bb5e28058c51f2345c5ffcb6de1f3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364938"
---
# <a name="crbmap-class"></a>CRBMap クラス
このクラスは、赤、黒のバイナリ ツリーを使用して、マッピング構造体を表します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
```    
  
#### <a name="parameters"></a>パラメーター  
 `K`  
 キーの要素の型。  
  
 *V*  
 値の要素型。  
  
 `KTraits`  
 コピーまたは主要な要素を移動するために使用するコードです。 参照してください[CElementTraits クラス](../../atl/reference/celementtraits-class.md)詳細についてはします。  
  
 `VTraits`  
 コピーまたは値の要素を移動するために使用するコードです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRBMap::CRBMap](#crbmap)|コンストラクターです。|  
|[CRBMap:: ~ CRBMap](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRBMap::Lookup](#lookup)|キーまたは値を検索するには、このメソッドを呼び出して、`CRBMap`オブジェクト。|  
|[CRBMap::RemoveKey](#removekey)|要素を削除するには、このメソッドを呼び出して、`CRBMap`キーが指定されたオブジェクト。|  
|[CRBMap::SetAt](#setat)|Map に要素のペアを挿入するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 `CRBMap` 主要な要素とその関連値の順序付けられた配列を管理する、指定された型のマッピングの配列のサポートを提供します。 各キーに関連付けられている値の 1 つだけことができます。 バイナリ ツリーに要素 (キーおよび値で構成される) が格納されている構造体を使用して、 [CRBMap::SetAt](#setat)メソッドです。 使用して要素を削除することができます、 [CRBMap::RemoveKey](#removekey)メソッドで、指定したキー値を持つ要素を削除します。  
  
 ツリーを走査することが可能なメソッドで行ったなど[CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition)、 [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext)、および[CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)です。  
  
 `KTraits`と`VTraits`パラメーターは次の特徴 (traits) クラスをコピーまたは要素を移動するために必要な補足コードが含まれています。  
  
 `CRBMap` 派生した[CRBTree](../../atl/reference/crbtree-class.md)赤、黒のアルゴリズムを使用してバイナリ ツリーを実装します。 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)はそれぞれのキーに対して複数の値を許可するバリエーションです。 派生すぎる`CRBTree`、そのために多くの機能を共有し、`CRBMap`です。  
  
 代わりに両方`CRBMap`と`CRBMultiMap`によって提供される、 [CAtlMap](../../atl/reference/catlmap-class.md)クラスです。 少数の要素のみを格納する必要があります、ときに、使用を検討して、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラスの代わりにします。  
  
 さまざまなコレクション クラスとその機能とパフォーマンス特性の詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="crbmap"></a>  CRBMap::CRBMap  
 コンストラクターです。  
  
```
explicit CRBMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 ブロック サイズ。  
  
### <a name="remarks"></a>コメント  
 `nBlockSize`パラメーターは、新しい要素が必要な場合に割り当てられたメモリの量の測定結果。 ブロック サイズを大きくはメモリ割り当てルーチンに呼び出しを減らすことより多くのリソースを使用します。 既定値は、一度に 10 個の要素の領域を割り当てられます。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用可能な他の方法についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]  
  
##  <a name="dtor"></a>  CRBMap:: ~ CRBMap  
 デストラクターです。  
  
```
~CRBMap() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたリソースを解放します。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用可能な他の方法についてはします。  
  
##  <a name="lookup"></a>  CRBMap::Lookup  
 キーまたは値を検索するには、このメソッドを呼び出して、`CRBMap`オブジェクト。  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 検索する要素を識別するキーを指定します。  
  
 *値*  
 検索された値を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 メソッドの最初の形式は、キーが見つかった場合は true を返します。 2 番目と 3 番目のフォームへのポインターを返す、 [CPair](crbtree-class.md#cpair_class)です。  
  
### <a name="remarks"></a>コメント  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用可能な他の方法についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]  
  
##  <a name="removekey"></a>  CRBMap::RemoveKey  
 要素を削除するには、このメソッドを呼び出して、`CRBMap`キーが指定されたオブジェクト。  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 削除する要素のペアに対応するキー。  
  
### <a name="return-value"></a>戻り値  
 キーが見つかったおよび削除された、失敗した場合に false の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用可能な他の方法についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]  
  
##  <a name="setat"></a>  CRBMap::SetAt  
 Map に要素のペアを挿入するには、このメソッドを呼び出します。  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 追加するキー値、`CRBMap`オブジェクト。  
  
 *値*  
 追加する値、`CRBMap`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 キー/値要素ペアでの位置を返します、`CRBMap`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `SetAt` 一致するキーが見つかった場合は、既存の要素を置換します。 キーが見つからない場合は、新しいキー/値ペアが作成されます。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用可能な他の方法についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CRBTree クラス](../../atl/reference/crbtree-class.md)   
 [CAtlMap クラス](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap クラス](../../atl/reference/crbmultimap-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
