---
title: CAtlMap クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlMap
- ATLCOLL/ATL::CAtlMap
- ATLCOLL/ATL::CAtlMap::KINARGTYPE
- ATLCOLL/ATL::CAtlMap::KOUTARGTYPE
- ATLCOLL/ATL::CAtlMap::VINARGTYPE
- ATLCOLL/ATL::CAtlMap::VOUTARGTYPE
- ATLCOLL/ATL::CPair::m_key
- ATLCOLL/ATL::CPair::m_value
- ATLCOLL/ATL::CAtlMap::CAtlMap
- ATLCOLL/ATL::CAtlMap::AssertValid
- ATLCOLL/ATL::CAtlMap::DisableAutoRehash
- ATLCOLL/ATL::CAtlMap::EnableAutoRehash
- ATLCOLL/ATL::CAtlMap::GetAt
- ATLCOLL/ATL::CAtlMap::GetCount
- ATLCOLL/ATL::CAtlMap::GetHashTableSize
- ATLCOLL/ATL::CAtlMap::GetKeyAt
- ATLCOLL/ATL::CAtlMap::GetNext
- ATLCOLL/ATL::CAtlMap::GetNextAssoc
- ATLCOLL/ATL::CAtlMap::GetNextKey
- ATLCOLL/ATL::CAtlMap::GetNextValue
- ATLCOLL/ATL::CAtlMap::GetStartPosition
- ATLCOLL/ATL::CAtlMap::GetValueAt
- ATLCOLL/ATL::CAtlMap::InitHashTable
- ATLCOLL/ATL::CAtlMap::IsEmpty
- ATLCOLL/ATL::CAtlMap::Lookup
- ATLCOLL/ATL::CAtlMap::Rehash
- ATLCOLL/ATL::CAtlMap::RemoveAll
- ATLCOLL/ATL::CAtlMap::RemoveAtPos
- ATLCOLL/ATL::CAtlMap::RemoveKey
- ATLCOLL/ATL::CAtlMap::SetAt
- ATLCOLL/ATL::CAtlMap::SetOptimalLoad
- ATLCOLL/ATL::CAtlMap::SetValueAt
dev_langs:
- C++
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c0a90ad7ce9d515331f817ef9ef5ee40d2d25b2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366296"
---
# <a name="catlmap-class"></a>CAtlMap クラス
このクラスは、作成と管理、map オブジェクトのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>>
class CAtlMap
```  
  
#### <a name="parameters"></a>パラメーター  
 `K`  
 キーの要素の型。  
  
 V  
 値の要素型。  
  
 `KTraits`  
 コピーまたは主要な要素を移動するために使用するコードです。 参照してください[CElementTraits クラス](../../atl/reference/celementtraits-class.md)詳細についてはします。  
  
 `VTraits`  
 コピーまたは値の要素を移動するために使用するコードです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::KINARGTYPE](#kinargtype)|キーが入力引数として渡されるときに使用される型|  
|[CAtlMap::KOUTARGTYPE](#koutargtype)|キーが出力引数として返されるときに使用される型。|  
|[CAtlMap::VINARGTYPE](#vinargtype)|値が入力引数として渡されるときに使用される型。|  
|[CAtlMap::VOUTARGTYPE](#voutargtype)|値が出力引数として渡されるときに使用される型。|  
  
### <a name="public-classes"></a>パブリック クラス  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::CPair クラス](#cpair_class)|キーと値の要素を含むクラスです。|  

  
### <a name="cpair-data-members"></a>CPair データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPair::m_key](#m_key)|キーの要素を格納するデータ メンバーです。|  
|[CPair::m_value](#m_value)|データ メンバーは、値の要素を格納します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::CAtlMap](#catlmap)|コンストラクターです。|  
|[CAtlMap:: ~ CAtlMap](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::AssertValid](#assertvalid)|アサートが発生する場合にこのメソッドを呼び出して、`CAtlMap`が無効です。|  
|[CAtlMap::DisableAutoRehash](#disableautorehash)|自動再ハッシュを無効にするには、このメソッドを呼び出して、`CAtlMap`オブジェクト。|  
|[CAtlMap::EnableAutoRehash](#enableautorehash)|自動再ハッシュを有効にするには、このメソッドを呼び出して、`CAtlMap`オブジェクト。|  
|[CAtlMap::GetAt](#getat)|マップ内の指定位置にある要素を返すには、このメソッドを呼び出します。|  
|[CAtlMap::GetCount](#getcount)|マップ内の要素の数を取得するには、このメソッドを呼び出します。|  
|[CAtlMap::GetHashTableSize](#gethashtablesize)|マップのハッシュ テーブルでビンの数を決定するには、このメソッドを呼び出します。|  
|[CAtlMap::GetKeyAt](#getkeyat)|指定された位置に格納されているキーを取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。|  
|[で](#getnext)|ペアが格納されている次の要素へのポインターを取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。|  
|[CAtlMap::GetNextAssoc](#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CAtlMap::GetNextKey](#getnextkey)|次のキーを取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。|  
|[CAtlMap::GetNextValue](#getnextvalue)|[次へ] の値を取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。|  
|[CAtlMap::GetStartPosition](#getstartposition)|マップの反復処理を開始するには、このメソッドを呼び出します。|  
|[CAtlMap::GetValueAt](#getvalueat)|内の指定位置に格納された値を取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。|  
|[格納します。](#inithashtable)|このメソッドを呼び出して、ハッシュ テーブルを初期化します。|  
|[CAtlMap::IsEmpty](#isempty)|空のマップ オブジェクトに対してテストするには、このメソッドを呼び出します。|  
|[CAtlMap::Lookup](#lookup)|キーまたは値を検索するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。|  
|[CAtlMap::Rehash](#rehash)|Rehash にこのメソッドを呼び出して、`CAtlMap`オブジェクト。|  
|[CAtlMap::RemoveAll](#removeall)|すべての要素を削除するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。|  
|[CAtlMap::RemoveAtPos](#removeatpos)|指定された位置に要素を削除するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。|  
|[CAtlMap::RemoveKey](#removekey)|要素を削除するには、このメソッドを呼び出して、`CAtlMap`キーが指定されたオブジェクト。|  
|[CAtlMap::SetAt](#setat)|Map に要素のペアを挿入するには、このメソッドを呼び出します。|  
|[CAtlMap::SetOptimalLoad](#setoptimalload)|最適な読み込みを設定するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。|  
|[CAtlMap::SetValueAt](#setvalueat)|指定された位置に格納されている値を変更するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|置き換えるか、新しい要素を追加、`CAtlMap`です。|  

  
## <a name="remarks"></a>コメント  
 `CAtlMap` 主要な要素とその関連値の順序なしの配列を管理する、指定された型のマッピングの配列のサポートを提供します。 (キーおよび値から成る) 要素は、大量のデータを効率よく格納および取得を許可するハッシュ アルゴリズムを使用して格納されます。  
  
 `KTraits`と`VTraits`パラメーターは次の特徴 (traits) クラスをコピーまたは要素を移動するために必要な補足コードが含まれています。  
  
 代わりに`CAtlMap`によって提供される、 [CRBMap](../../atl/reference/crbmap-class.md)クラスです。 `CRBMap` またさまざまなパフォーマンスの特徴は、キー/値ペアを保存します。 所要時間を項目を挿入する検索キー、およびからキーを削除、`CRBMap`オブジェクトの順序は*log (n)* ここで、 *n*要素の数です。 `CAtlMap`、注文の最悪のシナリオもありますが、通常、定数時間がかかるこれらすべての操作*n*です。 そのためでは、一般的な事例`CAtlMap`高速です。  
  
 その他の違い`CRBMap`と`CAtlMap`格納されている要素を反復処理するときに、明らかになります。 `CRBMap`、並べ替え順序で要素を閲覧します。 `CAtlMap`要素の順序がありません、および順序を推論できません。  
  
 格納する必要がある要素の数が少ない場合は、使用を検討して、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラスの代わりにします。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="assertvalid"></a>  CAtlMap::AssertValid  
 アサートが発生する場合にこのメソッドを呼び出して、`CAtlMap`オブジェクトが無効です。  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、このメソッドは、アサート場合、`CAtlMap`オブジェクトが無効です。  
  
### <a name="example"></a>例  
 例を参照して[CAtlMap::CAtlMap](#catlmap)です。  
  
##  <a name="catlmap"></a>  CAtlMap::CAtlMap  
 コンストラクターです。  
  
```
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBins`  
 格納されている要素へのポインターを提供するビンの数。 ビンの詳細については、このトピックの後半の「解説」を参照してください。  
  
 `fOptimalLoad`  
 最適な読み込みの比率です。  
  
 `fLoThreshold`  
 読み込みの比率の下限のしきい値。  
  
 `fHiThreshold`  
 負荷率の上限しきい値。  
  
 `nBlockSize`  
 ブロック サイズ。  
  
### <a name="remarks"></a>コメント  
 `CAtlMap` 最初に、キーのハッシュ アルゴリズムを使用してインデックスを作成することで、格納されている要素のすべてを参照します。 このインデックスは、格納されている要素へのポインターを含む"bin"を参照します。 箱が既に使用されている、後続の要素にアクセスするリンクされたリストが作成されます。 リストの走査することが、正しい要素に直接アクセスするよりも低いとマップの構造がパフォーマンスとストレージ要件のバランスをとる必要があるためです。 ほとんどの場合に良い結果を提供する既定のパラメーターが選択されています。  
  
 読み込みの比率は、マップ オブジェクト内に格納されている要素の数のビンの数の比率です。 マップの構造が再計算するとき、 *fOptimalLoad*パラメーター値が必要なビンの数を計算に使用されます。 使用して、この値を変更することができます、 [CAtlMap::SetOptimalLoad](#setoptimalload)メソッドです。  
  
 `fLoThreshold`パラメーターは、読み込みの比率にする前に到達可能な下限値`CAtlMap`マップの最適なサイズを再計算されます。  
  
 `fHiThreshold`パラメーターは、読み込みの比率は、前に到達できる上限の値、`CAtlMap`オブジェクトは、マップの最適なサイズを再計算されます。  
  
 この再計算プロセス (再ハッシュと呼ばれます) が既定で有効にします。 大量のデータで同時に呼び出しを入力するときに、このプロセスを無効にする場合、 [CAtlMap::DisableAutoRehash](#disableautorehash)メソッドです。 再アクティブ化することで、 [CAtlMap::EnableAutoRehash](#enableautorehash)メソッドです。  
  
 `nBlockSize`パラメーターは、新しい要素が必要な場合に割り当てられたメモリの量の測定結果。 ブロック サイズを大きくはメモリ割り当てルーチンに呼び出しを減らすことより多くのリソースを使用します。  
  
 呼び出しにハッシュ テーブルを初期化する必要があるすべてのデータを格納することができます、前に[格納する](#inithashtable)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]  
  
##  <a name="dtor"></a>  CAtlMap:: ~ CAtlMap  
 デストラクターです。  
  
```
~CAtlMap() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたリソースを解放します。  
  
##  <a name="cpair_class"></a>  CAtlMap::CPair クラス  
 キーと値の要素を含むクラスです。  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>コメント  
 このクラスは、メソッドによって使用[で](#getnext)と[CAtlMap::Lookup](#lookup)マップ構造体に格納されているキーと値の要素にアクセスします。  
  
##  <a name="disableautorehash"></a>  CAtlMap::DisableAutoRehash  
 自動再ハッシュを無効にするには、このメソッドを呼び出して、`CAtlMap`オブジェクト。  
  
```
void DisableAutoRehash() throw();
```  
  
### <a name="remarks"></a>コメント  
 自動再ハッシュが有効な場合 (既定である)、ハッシュ テーブルでビンの数が自動的に再計算負荷値 (配列に格納されている要素の数のビンの数の比率) が最大値または最小値を超えた場合マップの作成時に指定します。  
  
 `DisableAutoRehash` 多数の要素を 1 回に、マップに追加される場合最も便利です。 呼び出す方が効率的です rehashing プロセスをトリガーする制限を超えるたびに、代わりに`DisableAutoRehash`の要素を追加し、最後に呼び出して、 [CAtlMap::EnableAutoRehash](#enableautorehash)です。  
  
##  <a name="enableautorehash"></a>  CAtlMap::EnableAutoRehash  
 自動再ハッシュを有効にするには、このメソッドを呼び出して、`CAtlMap`オブジェクト。  
  
```
void EnableAutoRehash() throw();
```  
  
### <a name="remarks"></a>コメント  
 自動再ハッシュが有効な場合 (既定である)、ハッシュ テーブルでビンの数が自動的に再計算負荷値 (配列に格納されている要素の数のビンの数の比率) が最大値または最小値を超えた場合マップの作成時に指定します。  
  
 **EnableAutoRefresh**への呼び出し後が最もよく使用される[CAtlMap::DisableAutoRehash](#disableautorehash)です。  
  
##  <a name="getat"></a>  CAtlMap::GetAt  
 マップ内の指定位置にある要素を返すには、このメソッドを呼び出します。  
  
```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)です。  
  
 `key`  
 マップのキーの種類を指定するテンプレート パラメーター。  
  
 *値*  
 マップの値の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 現在、マップに格納されているキー/値要素のペアにポインターを返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
##  <a name="getcount"></a>  CAtlMap::GetCount  
 マップ内の要素の数を取得するには、このメソッドを呼び出します。  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 マップ オブジェクト内の要素の数を返します。 1 つの要素は、キー/値ペアです。  
  
### <a name="example"></a>例  
 例を参照して[CAtlMap::CAtlMap](#catlmap)です。  
  
##  <a name="gethashtablesize"></a>  CAtlMap::GetHashTableSize  
 マップのハッシュ テーブルでビンの数を決定するには、このメソッドを呼び出します。  
  
```
UINT GetHashTableSize() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ハッシュ テーブルには、ビンの数を返します。 参照してください[CAtlMap::CAtlMap](#catlmap)説明します。  
  
##  <a name="getkeyat"></a>  CAtlMap::GetKeyAt  
 指定された位置に格納されているキーを取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)です。  
  
### <a name="return-value"></a>戻り値  
 指定された位置に格納されているキーへの参照を返します、`CAtlMap`オブジェクト。  
  
### <a name="example"></a>例  
 例を参照して[CAtlMap::CAtlMap](#catlmap)です。  
  
##  <a name="getnext"></a>  で  
 ペアが格納されている次の要素へのポインターを取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。  
  
```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)です。  
  
### <a name="return-value"></a>戻り値  
 マップに格納されているキー/値要素の次の組み合わせへのポインターを返します。 `pos`位置カウンターは各呼び出しの後に更新します。 取得した要素が、マップ内の最後の場合は`pos`は NULL に設定します。  
  
##  <a name="getnextassoc"></a>  CAtlMap::GetNextAssoc  
 反復処理するためには、次の要素を取得します。  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)です。  
  
 `key`  
 マップのキーの種類を指定するテンプレート パラメーター。  
  
 *値*  
 マップの値の型を指定するテンプレート パラメーター。  
  
### <a name="remarks"></a>コメント  
 `pos`位置カウンターは各呼び出しの後に更新します。 取得した要素が、マップ内の最後の場合は`pos`は NULL に設定します。  
  
##  <a name="getnextkey"></a>  CAtlMap::GetNextKey  
 次のキーを取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)です。  
  
### <a name="return-value"></a>戻り値  
 マップ内には、次のキーへの参照を返します。  
  
### <a name="remarks"></a>コメント  
 現在の位置のカウンターを更新`pos`です。 マップのエントリがある場合、位置のカウンターは NULL に設定します。  
  
##  <a name="getnextvalue"></a>  CAtlMap::GetNextValue  
 [次へ] の値を取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。  
  
```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)です。  
  
### <a name="return-value"></a>戻り値  
 マップで、[次へ] の値への参照を返します。  
  
### <a name="remarks"></a>コメント  
 現在の位置のカウンターを更新`pos`です。 マップのエントリがある場合、位置のカウンターは NULL に設定します。  
  
### <a name="example"></a>例  
 例を参照して[CAtlMap::CAtlMap](#catlmap)です。  
  
##  <a name="getstartposition"></a>  CAtlMap::GetStartPosition  
 マップの反復処理を開始するには、このメソッドを呼び出します。  
  
```
POSITION GetStartPosition() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 マップが空の場合に、開始位置、または NULL が返されますを返します。  
  
### <a name="remarks"></a>コメント  
 返すことによって、マップの反復処理を開始するには、このメソッドを呼び出して、**位置**値を渡すことができる、`GetNextAssoc`メソッドです。  
  
> [!NOTE]
>  イテレーションの順序は予測できません。  
  
### <a name="example"></a>例  
 例を参照して[CAtlMap::CAtlMap](#catlmap)です。  
  
##  <a name="getvalueat"></a>  CAtlMap::GetValueAt  
 内の指定位置に格納された値を取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。  
  
```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)です。  
  
### <a name="return-value"></a>戻り値  
 指定された位置に格納されている値への参照を返します、`CAtlMap`オブジェクト。  
  
##  <a name="inithashtable"></a>  格納します。  
 このメソッドを呼び出して、ハッシュ テーブルを初期化します。  
  
```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBins`  
 ハッシュ テーブルで使用されるビンの数。 参照してください[CAtlMap::CAtlMap](#catlmap)説明します。  
  
 `bAllocNow`  
 示すフラグとメモリを割り当てる必要があります。  
  
### <a name="return-value"></a>戻り値  
 返します**true**初期化が成功する、 **false**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 `InitHashTable` すべての要素が、ハッシュ テーブルに保存される前に呼び出す必要があります。  このメソッドが明示的に呼び出されない場合は呼び出されます自動的に初めてによって指定されたビン数を使用して、要素が追加された、 **CAtlMap**コンス トラクターです。  によって指定された新しいビン数を使用して、マップを初期化、それ以外の場合、`nBins`パラメーター。  
  
 場合、`bAllocNow`パラメーターが false で、必要になるまで、最初に、ハッシュ テーブルに必要なメモリを割り当てられませんされます。 マップを使用する場合は、確定されていない場合に役立ちます。 これができます。  
  
### <a name="example"></a>例  
 例を参照して[CAtlMap::CAtlMap](#catlmap)です。  
  
##  <a name="isempty"></a>  CAtlMap::IsEmpty  
 空のマップ オブジェクトに対してテストするには、このメソッドを呼び出します。  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**マップが空の場合、 **false**それ以外の場合。  
  
##  <a name="kinargtype"></a>  CAtlMap::KINARGTYPE  
 キーが入力引数として渡されるときに使用される型。  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>  CAtlMap::KOUTARGTYPE  
 キーが出力引数として返されるときに使用される型。  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="lookup"></a>  CAtlMap::Lookup  
 キーまたは値を検索するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 検索する要素を識別するキーを指定します。  
  
 *値*  
 検索された値を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 メソッドの最初の形式は、キーが見つかった場合は true を返します。 2 番目と 3 番目のフォームへのポインターを返す、 [CPair](#cpair_class)呼び出しのために、位置として使用できる[で](#getnext)などです。  
  
### <a name="remarks"></a>コメント  
 `Lookup` ハッシュ アルゴリズムを使用して、迅速に特定のキー パラメーターと一致するキーを含むマップの要素を検索します。  
  
##  <a name="operator_at"></a>  CAtlMap::operator \[\]  
 置き換えるか、新しい要素を追加、`CAtlMap`です。  
  
```
V& operator[](kinargtype key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 追加または置換する要素のキー。  
  
### <a name="return-value"></a>戻り値  
 指定したキーに関連付けられている値への参照を返します。  
  
### <a name="example"></a>例  
 キーが既に存在する場合は、要素が置き換えられます。 キーが存在しない場合は、新しい要素が追加されます。 例を参照して[CAtlMap::CAtlMap](#catlmap)です。  
  
##  <a name="rehash"></a>  CAtlMap::Rehash  
 Rehash にこのメソッドを呼び出して、`CAtlMap`オブジェクト。  
  
```
void Rehash(UINT nBins = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBins`  
 ハッシュ テーブルで使用する新しいビン数です。 参照してください[CAtlMap::CAtlMap](#catlmap)説明します。  
  
### <a name="remarks"></a>コメント  
 場合`nBins`0 の場合は、`CAtlMap`マップおよび最適な読み込みの設定内の要素の数に基づいて、適切な数を計算します。 通常、rehashing プロセスは、自動、場合に、 [CAtlMap::DisableAutoRehash](#disableautorehash)されました呼び出されると、このメソッドは、必要なサイズ変更は実行します。  
  
##  <a name="removeall"></a>  CAtlMap::RemoveAll  
 すべての要素を削除するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>コメント  
 クリアして、`CAtlMap`オブジェクト、要素を格納するために使用するメモリを解放します。  
  
##  <a name="removeatpos"></a>  CAtlMap::RemoveAtPos  
 指定された位置に要素を削除するには、このメソッドを呼び出す、`CAtlMap`オブジェクト。  
  
```
void RemoveAtPos(POSITION pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)です。  
  
### <a name="remarks"></a>コメント  
 指定した位置に格納されているキー/値ペアを削除します。 要素の格納に使用されるメモリは解放されます。 によって参照される位置`pos`、無効になり、マップ内の他の要素の位置を必ずしもを行うには、有効にしたまま、同じ順序を保持します。  
  
##  <a name="removekey"></a>  CAtlMap::RemoveKey  
 要素を削除するには、このメソッドを呼び出して、`CAtlMap`キーが指定されたオブジェクト。  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 削除する要素のペアに対応するキー。  
  
### <a name="return-value"></a>戻り値  
 返します**true**キーが検出され、削除、 **false**エラー発生時にします。  
  
### <a name="example"></a>例  
 例を参照して[CAtlMap::CAtlMap](#catlmap)です。  
  
##  <a name="setat"></a>  CAtlMap::SetAt  
 Map に要素のペアを挿入するには、このメソッドを呼び出します。  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 追加するキー値、`CAtlMap`オブジェクト。  
  
 *値*  
 追加する値、`CAtlMap`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 キー/値要素ペアでの位置を返します、`CAtlMap`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `SetAt` 一致するキーが見つかった場合は、既存の要素を置換します。 キーが見つからない場合は、新しいキー/値ペアが作成されます。  
  
##  <a name="setoptimalload"></a>  CAtlMap::SetOptimalLoad  
 最適な読み込みを設定するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。  
  
```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```  
  
### <a name="parameters"></a>パラメーター  
 `fOptimalLoad`  
 最適な読み込みの比率です。  
  
 `fLoThreshold`  
 読み込みの比率の下限のしきい値。  
  
 `fHiThreshold`  
 負荷率の上限しきい値。  
  
 `bRehashNow`  
 ハッシュ テーブルを再計算する必要がありますかを示すフラグです。  
  
### <a name="remarks"></a>コメント  
 このメソッドの値は、最適な負荷を再定義、`CAtlMap`オブジェクト。 参照してください[CAtlMap::CAtlMap](#catlmap)については、さまざまなパラメーターです。 場合`bRehashNow`が true の場合、要素の数が最小値と最大値の範囲外、ハッシュ テーブルを再計算します。  
  
##  <a name="setvalueat"></a>  CAtlMap::SetValueAt  
 指定された位置に格納されている値を変更するには、このメソッドを呼び出して、`CAtlMap`オブジェクト。  
  
```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)です。  
  
 *値*  
 追加する値、`CAtlMap`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 指定された位置に格納されている値を変更、`CAtlMap`オブジェクト。  
  
##  <a name="vinargtype"></a>  CAtlMap::VINARGTYPE  
 値が入力引数として渡されるときに使用される型。  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>  CAtlMap::VOUTARGTYPE  
 値が出力引数として渡されるときに使用される型。  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
##  <a name="m_key"></a>  CAtlMap::CPair::m_key  
 キーの要素を格納するデータ メンバーです。  
  
```
const K m_key;
```    
  
### <a name="parameters"></a>パラメーター  
 `K`  
 キーの要素の型。  
  
##  <a name="m_value"></a>  CAtlMap::CPair::m_value  
 データ メンバーは、値の要素を格納します。  
  
```
V  m_value;
```    
  
### <a name="parameters"></a>パラメーター  
 *V*  
 値の要素型。  
  
## <a name="see-also"></a>関連項目  
 [マーキーのサンプル](../../visual-cpp-samples.md)   
 [UpdatePV サンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
