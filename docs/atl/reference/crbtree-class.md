---
title: CRBTree クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
dev_langs:
- C++
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b15ddf62545d5926faf75af760ed52219f1cb03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365586"
---
# <a name="crbtree-class"></a>CRBTree クラス
このクラスは、作成および赤、黒のツリーを利用するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBTree
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
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CRBTree::KINARGTYPE](#kinargtype)|キーが入力引数として渡されるときに使用される型。|  
|[CRBTree::KOUTARGTYPE](#koutargtype)|キーが出力引数として返されるときに使用される型。|  
|[CRBTree::VINARGTYPE](#vinargtype)|値が入力引数として渡されるときに使用される型。|  
|[CRBTree::VOUTARGTYPE](#voutargtype)|値が出力引数として渡されるときに使用される型。|  
  
### <a name="public-classes"></a>パブリック クラス  
  
|名前|説明|  
|----------|-----------------|  
|[CRBTree::CPair クラス](#cpair_class)|キーと値の要素を含むクラスです。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRBTree:: ~ CRBTree](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|次の利用可能なキーを使用する要素の位置を検索するには、このメソッドを呼び出します。|  
|[CRBTree::GetAt](#getat)|このメソッドを呼び出して、ツリー内の指定位置の要素を取得します。|  
|[CRBTree::GetCount](#getcount)|このメソッドを呼び出して、ツリー内の要素の数を取得します。|  
|[CRBTree::GetHeadPosition](#getheadposition)|ツリーの先頭にある要素の位置を表す値を取得するには、このメソッドを呼び出します。|  
|[CRBTree::GetKeyAt](#getkeyat)|このメソッドを呼び出して、ツリー内の指定位置からキーを取得します。|  
|[CRBTree::GetNext](#getnext)|格納されている要素へのポインターを取得するには、このメソッドを呼び出して、`CRBTree`オブジェクト、および位置を次の要素に進めます。|  
|[CRBTree::GetNextAssoc](#getnextassoc)|キーと、マップに格納されている要素の値を取得するには、このメソッドを呼び出すし、次の要素に位置を進めます。|  
|[CRBTree::GetNextKey](#getnextkey)|ツリー内の要素のキーを取得するには、このメソッドを呼び出すし、次の要素に位置を進めます。|  
|[CRBTree::GetNextValue](#getnextvalue)|ツリー内の要素の値を取得するには、このメソッドを呼び出すし、次の要素に位置を進めます。|  
|[CRBTree::GetPrev](#getprev)|格納されている要素へのポインターを取得するには、このメソッドを呼び出して、`CRBTree`オブジェクト、およびその直前の要素に位置を更新します。|  
|[CRBTree::GetTailPosition](#gettailposition)|ツリーの末尾にある要素の位置を表す値を取得するには、このメソッドを呼び出します。|  
|[CRBTree::GetValueAt](#getvalueat)|内の指定位置に格納された値を取得するには、このメソッドを呼び出して、`CRBTree`オブジェクト。|  
|[CRBTree::IsEmpty](#isempty)|空のツリーのオブジェクトをテストするには、このメソッドを呼び出します。|  
|[CRBTree::RemoveAll](#removeall)|すべての要素を削除するには、このメソッドを呼び出す、 **CRBTree**オブジェクト。|  
|[CRBTree::RemoveAt](#removeat)|指定された位置に要素を削除するには、このメソッドを呼び出す、 **CRBTree**オブジェクト。|  
|[CRBTree::SetValueAt](#setvalueat)|指定された位置に格納されている値を変更するには、このメソッドを呼び出して、`CRBTree`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 赤、黒ツリーは余分なを使用するバイナリ サーチ ツリーを確保するノードごとに情報のビットを「バランス、」である、ツリーの高さが過度に大きく、パフォーマンスに影響します。  
  
 このテンプレート クラスで使用するものでは[CRBMap](../../atl/reference/crbmap-class.md)と[CRBMultiMap](../../atl/reference/crbmultimap-class.md)です。 これらの派生クラスを作成するメソッドの大部分は、によって提供される`CRBTree`です。  
  
 さまざまなコレクション クラスとその機能とパフォーマンス特性の詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="cpair_class"></a>  CRBTree::CPair クラス  
 キーと値の要素を含むクラスです。  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>コメント  
 このクラスは、メソッドによって使用[CRBTree::GetAt](#getat)、 [CRBTree::GetNext](#getnext)、および[CRBTree::GetPrev](#getprev)ツリー構造に格納されているキーと値の要素にアクセスします。  
  
 メンバーは次のとおりです。  
  
|||  
|-|-|  
|`m_key`|キーの要素を格納するデータ メンバーです。|  
|`m_value`|データ メンバーは、値の要素を格納します。|  
  
##  <a name="dtor"></a>  CRBTree:: ~ CRBTree  
 デストラクターです。  
  
```
~CRBTree() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたリソースを解放します。 呼び出し[CRBTree::RemoveAll](#removeall)をすべての要素を削除します。  
  
##  <a name="findfirstkeyafter"></a>  CRBTree::FindFirstKeyAfter  
 次の利用可能なキーを使用する要素の位置を検索するには、このメソッドを呼び出します。  
  
```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 キーの値。  
  
### <a name="return-value"></a>戻り値  
 次の利用可能なキーを使用する要素の位置の値を返します。 複数の要素ではありませんがある場合は、NULL が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドによりしやすくなります位置の値を事前に計算することがなく、ツリーを走査します。  
  
##  <a name="getat"></a>  CRBTree::GetAt  
 このメソッドを呼び出して、ツリー内の指定位置の要素を取得します。  
  
```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 位置の値。  
  
 `key`  
 キーを受け取る変数。  
  
 *値*  
 値を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 最初の 2 つのフォームへのポインターを返す、 [CPair](#cpair_class)です。 3 番目の形式は、キーと指定した位置の値を取得します。  
  
### <a name="remarks"></a>コメント  
 位置の値以前で判断できますメソッドへの呼び出しなど[CRBTree::GetHeadPosition](#getheadposition)または[CRBTree::GetTailPosition](#gettailposition)です。  
  
 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
##  <a name="getcount"></a>  CRBTree::GetCount  
 このメソッドを呼び出して、ツリー内の要素の数を取得します。  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ツリーに格納されている (各キーと値のペアは 1 つの要素) の要素の数を返します。  
  
##  <a name="getheadposition"></a>  CRBTree::GetHeadPosition  
 ツリーの先頭にある要素の位置を表す値を取得するには、このメソッドを呼び出します。  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ツリーの先頭にある要素の位置を表す値を返します。  
  
### <a name="remarks"></a>コメント  
 によって返される値`GetHeadPosition`などのメソッドで使用できる[CRBTree::GetKeyAt](#getkeyat)または[CRBTree::GetNext](#getnext)ツリーを走査し、値を取得します。  
  
##  <a name="getkeyat"></a>  CRBTree::GetKeyAt  
 このメソッドを呼び出して、ツリー内の指定位置からキーを取得します。  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 位置の値。  
  
### <a name="return-value"></a>戻り値  
 位置に格納されているキーを返します`pos`ツリー。  
  
### <a name="remarks"></a>コメント  
 場合`pos`が有効な位置の値では、結果は予測できません。 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
##  <a name="getnext"></a>  CRBTree::GetNext  
 格納されている要素へのポインターを取得するには、このメソッドを呼び出して、`CRBTree`オブジェクト、および位置を次の要素に進めます。  
  
```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 などのメソッドに以前の呼び出しによって返される位置カウンター [CRBTree::GetHeadPosition](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)です。  
  
### <a name="return-value"></a>戻り値  
 ポインターを返します[CPair](#cpair_class)ツリー内の値。  
  
### <a name="remarks"></a>コメント  
 `pos`位置カウンターは各呼び出しの後に更新します。 取得した要素が、ツリー内の最後の場合は`pos`は NULL に設定します。  
  
##  <a name="getnextassoc"></a>  CRBTree::GetNextAssoc  
 キーと、マップに格納されている要素の値を取得するには、このメソッドを呼び出すし、次の要素に位置を進めます。  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 などのメソッドに以前の呼び出しによって返される位置カウンター [CRBTree::GetHeadPosition](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)です。  
  
 `key`  
 ツリーのキーの種類を指定するテンプレート パラメーター。  
  
 *値*  
 ツリーの値の型を指定するテンプレート パラメーター。  
  
### <a name="remarks"></a>コメント  
 `pos`位置カウンターは各呼び出しの後に更新します。 取得した要素が、ツリー内の最後の場合は`pos`は NULL に設定します。  
  
##  <a name="getnextkey"></a>  CRBTree::GetNextKey  
 ツリー内の要素のキーを取得するには、このメソッドを呼び出すし、次の要素に位置を進めます。  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 などのメソッドに以前の呼び出しによって返される位置カウンター [CRBTree::GetHeadPosition](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)です。  
  
### <a name="return-value"></a>戻り値  
 ツリーで、[次へ] のキーへの参照を返します。  
  
### <a name="remarks"></a>コメント  
 現在の位置のカウンターを更新`pos`です。 ツリーにエントリがある場合、位置のカウンターは NULL に設定します。  
  
##  <a name="getnextvalue"></a>  CRBTree::GetNextValue  
 ツリー内の要素の値を取得するには、このメソッドを呼び出すし、次の要素に位置を進めます。  
  
```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 などのメソッドに以前の呼び出しによって返される位置カウンター [CRBTree::GetHeadPosition](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)です。  
  
### <a name="return-value"></a>戻り値  
 ツリーで、[次へ] の値への参照を返します。  
  
### <a name="remarks"></a>コメント  
 現在の位置のカウンターを更新`pos`です。 ツリーにエントリがある場合、位置のカウンターは NULL に設定します。  
  
##  <a name="getprev"></a>  CRBTree::GetPrev  
 格納されている要素へのポインターを取得するには、このメソッドを呼び出して、`CRBTree`オブジェクト、およびその直前の要素に位置を更新します。  
  
```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 などのメソッドに以前の呼び出しによって返される位置カウンター [CRBTree::GetHeadPosition](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)です。  
  
### <a name="return-value"></a>戻り値  
 前のポインターを返します[CPair](#cpair_class)ツリーで、格納されている値。  
  
### <a name="remarks"></a>コメント  
 現在の位置のカウンターを更新`pos`です。 ツリーにエントリがある場合、位置のカウンターは NULL に設定します。  
  
##  <a name="gettailposition"></a>  CRBTree::GetTailPosition  
 ツリーの末尾にある要素の位置を表す値を取得するには、このメソッドを呼び出します。  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ツリーの末尾にある要素の位置を表す値を返します。  
  
### <a name="remarks"></a>コメント  
 によって返される値`GetTailPosition`などのメソッドで使用できる[CRBTree::GetKeyAt](#getkeyat)または[CRBTree::GetPrev](#getprev)ツリーを走査し、値を取得します。  
  
##  <a name="getvalueat"></a>  CRBTree::GetValueAt  
 内の指定位置に格納された値を取得するには、このメソッドを呼び出して、`CRBTree`オブジェクト。  
  
```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 などのメソッドに以前の呼び出しによって返される位置カウンター [CRBTree::GetHeadPosition](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)です。  
  
### <a name="return-value"></a>戻り値  
 指定された位置に格納されている値への参照を返します、`CRBTree`オブジェクト。  
  
##  <a name="isempty"></a>  CRBTree::IsEmpty  
 空のツリーのオブジェクトをテストするには、このメソッドを呼び出します。  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**ツリーが空の場合、 **false**それ以外の場合。  
  
##  <a name="kinargtype"></a>  CRBTree::KINARGTYPE  
 キーが入力引数として渡されるときに使用される型。  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>  CRBTree::KOUTARGTYPE  
 キーが出力引数として返されるときに使用される型。  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="removeall"></a>  CRBTree::RemoveAll  
 すべての要素を削除するには、このメソッドを呼び出す、`CRBTree`オブジェクト。  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>コメント  
 クリアして、`CRBTree`オブジェクト、要素を格納するために使用するメモリを解放します。  
  
##  <a name="removeat"></a>  CRBTree::RemoveAt  
 指定された位置に要素を削除するには、このメソッドを呼び出す、 **CRBTree**オブジェクト。  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 などのメソッドに以前の呼び出しによって返される位置カウンター [CRBTree::GetHeadPosition](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)です。  
  
### <a name="remarks"></a>コメント  
 指定した位置に格納されているキー/値ペアを削除します。 要素の格納に使用されるメモリは解放されます。 によって参照される位置`pos`、無効になり、ツリー内の他の要素の位置を必ずしもを行うには、有効にしたまま、同じ順序を保持します。  
  
##  <a name="setvalueat"></a>  CRBTree::SetValueAt  
 指定された位置に格納されている値を変更するには、このメソッドを呼び出して、`CRBTree`オブジェクト。  
  
```
void SetValueAt(POSITION pos, VINARGTYPE value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 などのメソッドに以前の呼び出しによって返される位置カウンター [CRBTree::GetHeadPosition](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)です。  
  
 *値*  
 追加する値、`CRBTree`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 指定された位置に格納されている値を変更、`CRBTree`オブジェクト。  
  
##  <a name="vinargtype"></a>  CRBTree::VINARGTYPE  
 値が入力引数として渡されるときに使用される型。  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>  CRBTree::VOUTARGTYPE  
 値が出力引数として渡されるときに使用される型。  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
