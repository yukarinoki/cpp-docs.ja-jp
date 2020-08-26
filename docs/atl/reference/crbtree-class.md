---
title: CRBTree クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
ms.openlocfilehash: 7b8e47b5cd0ac278711947abc867956333371be3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833492"
---
# <a name="crbtree-class"></a>CRBTree クラス

このクラスは、赤の黒のツリーを作成および利用するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBTree
```

#### <a name="parameters"></a>パラメーター

*Kb*<br/>
キー要素の型。

*V*<br/>
値要素の型。

*KTraits*<br/>
キー要素をコピーまたは移動するために使用されるコード。 詳細については、「 [Celementtraits クラス](../../atl/reference/celementtraits-class.md) 」を参照してください。

*VTraits*<br/>
値要素をコピーまたは移動するために使用されるコード。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CRBTree:: KINARGTYPE](#kinargtype)|キーが入力引数として渡されるときに使用される型。|
|[CRBTree:: KOUTARGTYPE](#koutargtype)|キーが出力引数として返されるときに使用される型。|
|[CRBTree:: VINARGTYPE](#vinargtype)|値が入力引数として渡されるときに使用される型。|
|[CRBTree:: VOUTARGTYPE](#voutargtype)|値が出力引数として渡されるときに使用される型。|

### <a name="public-classes"></a>パブリック クラス

|名前|説明|
|----------|-----------------|
|[CRBTree:: CPair クラス](#cpair_class)|キー要素と値要素を格納しているクラス。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRBTree:: ~ CRBTree](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)|次に使用可能なキーを使用する要素の位置を検索するには、このメソッドを呼び出します。|
|[CRBTree:: GetAt](#getat)|ツリー内の指定した位置にある要素を取得するには、このメソッドを呼び出します。|
|[CRBTree:: GetCount](#getcount)|ツリー内の要素の数を取得するには、このメソッドを呼び出します。|
|[CRBTree:: GetHeadPosition](#getheadposition)|ツリーの先頭にある要素の位置の値を取得するには、このメソッドを呼び出します。|
|[CRBTree:: GetKeyAt](#getkeyat)|ツリー内の指定された位置からキーを取得するには、このメソッドを呼び出します。|
|[CRBTree:: GetNext](#getnext)|オブジェクトに格納されている要素へのポインターを取得し、その位置を次の要素に進めるには、このメソッドを呼び出し `CRBTree` ます。|
|[CRBTree:: GetNextAssoc](#getnextassoc)|Map に格納されている要素のキーと値を取得し、その位置を次の要素に進めるには、このメソッドを呼び出します。|
|[CRBTree:: GetNextKey](#getnextkey)|このメソッドを呼び出して、ツリーに格納されている要素のキーを取得し、その位置を次の要素に進めます。|
|[CRBTree:: GetNextValue](#getnextvalue)|このメソッドを呼び出して、ツリーに格納されている要素の値を取得し、その位置を次の要素に進めます。|
|[CRBTree:: GetPrev](#getprev)|オブジェクトに格納されている要素へのポインターを取得し、その位置を前の要素に更新するには、このメソッドを呼び出し `CRBTree` ます。|
|[CRBTree:: GetTailPosition](#gettailposition)|ツリーの末尾にある要素の位置の値を取得するには、このメソッドを呼び出します。|
|[CRBTree:: GetValueAt](#getvalueat)|オブジェクト内の指定した位置に格納されている値を取得するには、このメソッドを呼び出し `CRBTree` ます。|
|[CRBTree:: IsEmpty](#isempty)|空のツリーオブジェクトをテストするには、このメソッドを呼び出します。|
|[CRBTree:: RemoveAll](#removeall)|オブジェクトからすべての要素を削除するには、このメソッドを呼び出し `CRBTree` ます。|
|[CRBTree:: RemoveAt](#removeat)|オブジェクト内の指定された位置にある要素を削除するには、このメソッドを呼び出し `CRBTree` ます。|
|[CRBTree:: SetValueAt](#setvalueat)|オブジェクト内の指定した位置に格納されている値を変更するには、このメソッドを呼び出し `CRBTree` ます。|

## <a name="remarks"></a>解説

赤い黒のツリーは、ノードごとに追加の情報を使用して "均衡" を保つようにするバイナリ検索ツリーです。つまり、ツリーの高さが過度に大きくなり、パフォーマンスに影響を与えることはありません。

このテンプレートクラスは、 [CRBMap](../../atl/reference/crbmap-class.md) と [CRBMultiMap](../../atl/reference/crbmultimap-class.md)によって使用されるように設計されています。 これらの派生クラスを構成するメソッドの大部分は、によって提供され `CRBTree` ます。

さまざまなコレクションクラスとその機能とパフォーマンス特性の詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll. h

## <a name="crbtreecpair-class"></a><a name="cpair_class"></a> CRBTree:: CPair クラス

キー要素と値要素を格納しているクラス。

```
class CPair : public __POSITION
```

### <a name="remarks"></a>解説

このクラスは、のメソッドである [crbtree:: GetAt](#getat)、 [Crbtree:: GetNext](#getnext)、および [CRBTree:: getprev](#getprev) を使用して、ツリー構造に格納されているキー要素と値要素にアクセスします。

メンバーは次のとおりです。

|データ メンバー|説明|
|-|-|
|`m_key`|キー要素を格納しているデータメンバー。|
|`m_value`|値要素を格納しているデータメンバー。|

## <a name="crbtreecrbtree"></a><a name="dtor"></a> CRBTree:: ~ CRBTree

デストラクターです。

```
~CRBTree() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。 すべての要素を削除するには、 [CRBTree:: RemoveAll](#removeall) を呼び出します。

## <a name="crbtreefindfirstkeyafter"></a><a name="findfirstkeyafter"></a> CRBTree:: FindFirstKeyAfter

次に使用可能なキーを使用する要素の位置を検索するには、このメソッドを呼び出します。

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー値。

### <a name="return-value"></a>戻り値

次に使用可能なキーを使用する要素の位置の値を返します。 それ以上要素がない場合は、NULL が返されます。

### <a name="remarks"></a>解説

このメソッドを使用すると、位置の値を事前に計算しなくても、ツリーを簡単に走査できます。

## <a name="crbtreegetat"></a><a name="getat"></a> CRBTree:: GetAt

ツリー内の指定した位置にある要素を取得するには、このメソッドを呼び出します。

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>パラメーター

*po*<br/>
位置を表す値です。

*key*<br/>
キーを受け取る変数。

*value*<br/>
値を受け取る変数。

### <a name="return-value"></a>戻り値

最初の2つの形式は、 [CPair](#cpair_class)へのポインターを返します。 3番目の形式は、指定された位置のキーと値を取得します。

### <a name="remarks"></a>解説

位置の値は、以前は、 [crbtree:: GetHeadPosition](#getheadposition) や [Crbtree:: GetTailPosition](#gettailposition)などのメソッドを呼び出すことによって決定できます。

デバッグビルドでは、 *pos* が NULL と等しい場合にアサーションエラーが発生します。

## <a name="crbtreegetcount"></a><a name="getcount"></a> CRBTree:: GetCount

ツリー内の要素の数を取得するには、このメソッドを呼び出します。

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>戻り値

ツリーに格納されている要素の数 (各キーと値のペアが1つの要素) を返します。

## <a name="crbtreegetheadposition"></a><a name="getheadposition"></a> CRBTree:: GetHeadPosition

ツリーの先頭にある要素の位置の値を取得するには、このメソッドを呼び出します。

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>戻り値

ツリーの先頭にある要素の位置の値を返します。

### <a name="remarks"></a>解説

によって返される値は、 `GetHeadPosition` [crbtree:: GetKeyAt](#getkeyat) や [crbtree:: GetNext](#getnext) などのメソッドと共に使用して、ツリーを走査し、値を取得することができます。

## <a name="crbtreegetkeyat"></a><a name="getkeyat"></a> CRBTree:: GetKeyAt

ツリー内の指定された位置からキーを取得するには、このメソッドを呼び出します。

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
位置を表す値です。

### <a name="return-value"></a>戻り値

ツリーの位置 *pos* に格納されているキーを返します。

### <a name="remarks"></a>解説

*Pos*が有効な位置の値でない場合、結果は予測できません。 デバッグビルドでは、 *pos* が NULL と等しい場合にアサーションエラーが発生します。

## <a name="crbtreegetnext"></a><a name="getnext"></a> CRBTree:: GetNext

オブジェクトに格納されている要素へのポインターを取得し、その位置を次の要素に進めるには、このメソッドを呼び出し `CRBTree` ます。

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
[Crbtree:: GetHeadPosition](#getheadposition)や[Crbtree:: FindFirstKeyAfter](#findfirstkeyafter)などのメソッドの以前の呼び出しによって返された位置カウンター。

### <a name="return-value"></a>戻り値

ツリー内の次の [CPair](#cpair_class) 値へのポインターを返します。

### <a name="remarks"></a>解説

各呼び出しの後に、 *pos* 位置カウンターが更新されます。 取得した要素がツリーの最後の要素である場合、 *pos* は NULL に設定されます。

## <a name="crbtreegetnextassoc"></a><a name="getnextassoc"></a> CRBTree:: GetNextAssoc

Map に格納されている要素のキーと値を取得し、その位置を次の要素に進めるには、このメソッドを呼び出します。

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>パラメーター

*po*<br/>
[Crbtree:: GetHeadPosition](#getheadposition)や[Crbtree:: FindFirstKeyAfter](#findfirstkeyafter)などのメソッドの以前の呼び出しによって返された位置カウンター。

*key*<br/>
ツリーのキーの型を指定するテンプレートパラメーター。

*value*<br/>
ツリーの値の型を指定するテンプレートパラメーター。

### <a name="remarks"></a>解説

各呼び出しの後に、 *pos* 位置カウンターが更新されます。 取得した要素がツリーの最後の要素である場合、 *pos* は NULL に設定されます。

## <a name="crbtreegetnextkey"></a><a name="getnextkey"></a> CRBTree:: GetNextKey

このメソッドを呼び出して、ツリーに格納されている要素のキーを取得し、その位置を次の要素に進めます。

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
[Crbtree:: GetHeadPosition](#getheadposition)や[Crbtree:: FindFirstKeyAfter](#findfirstkeyafter)などのメソッドの以前の呼び出しによって返された位置カウンター。

### <a name="return-value"></a>戻り値

ツリー内の次のキーへの参照を返します。

### <a name="remarks"></a>解説

現在の位置カウンター ( *pos*) を更新します。ツリーにエントリがそれ以上ない場合は、position カウンターが NULL に設定されます。

## <a name="crbtreegetnextvalue"></a><a name="getnextvalue"></a> CRBTree:: GetNextValue

このメソッドを呼び出して、ツリーに格納されている要素の値を取得し、その位置を次の要素に進めます。

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
[Crbtree:: GetHeadPosition](#getheadposition)や[Crbtree:: FindFirstKeyAfter](#findfirstkeyafter)などのメソッドの以前の呼び出しによって返された位置カウンター。

### <a name="return-value"></a>戻り値

ツリー内の次の値への参照を返します。

### <a name="remarks"></a>解説

現在の位置カウンター ( *pos*) を更新します。ツリーにエントリがそれ以上ない場合は、position カウンターが NULL に設定されます。

## <a name="crbtreegetprev"></a><a name="getprev"></a> CRBTree:: GetPrev

オブジェクトに格納されている要素へのポインターを取得し、その位置を前の要素に更新するには、このメソッドを呼び出し `CRBTree` ます。

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
[Crbtree:: GetHeadPosition](#getheadposition)や[Crbtree:: FindFirstKeyAfter](#findfirstkeyafter)などのメソッドの以前の呼び出しによって返された位置カウンター。

### <a name="return-value"></a>戻り値

ツリーに格納されている前の [CPair](#cpair_class) 値へのポインターを返します。

### <a name="remarks"></a>解説

現在の位置カウンター ( *pos*) を更新します。ツリーにエントリがそれ以上ない場合は、position カウンターが NULL に設定されます。

## <a name="crbtreegettailposition"></a><a name="gettailposition"></a> CRBTree:: GetTailPosition

ツリーの末尾にある要素の位置の値を取得するには、このメソッドを呼び出します。

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>戻り値

ツリーの末尾にある要素の位置の値を返します。

### <a name="remarks"></a>解説

によって返される値は、 `GetTailPosition` [crbtree:: GetKeyAt](#getkeyat) や [Crbtree:: getprev](#getprev) などのメソッドと共に使用して、ツリーを走査し、値を取得することができます。

## <a name="crbtreegetvalueat"></a><a name="getvalueat"></a> CRBTree:: GetValueAt

オブジェクト内の指定した位置に格納されている値を取得するには、このメソッドを呼び出し `CRBTree` ます。

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
[Crbtree:: GetHeadPosition](#getheadposition)や[Crbtree:: FindFirstKeyAfter](#findfirstkeyafter)などのメソッドの以前の呼び出しによって返された位置カウンター。

### <a name="return-value"></a>戻り値

オブジェクト内の指定した位置に格納されている値への参照を返し `CRBTree` ます。

## <a name="crbtreeisempty"></a><a name="isempty"></a> CRBTree:: IsEmpty

空のツリーオブジェクトをテストするには、このメソッドを呼び出します。

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

ツリーが空の場合は TRUE、それ以外の場合は FALSE を返します。

## <a name="crbtreekinargtype"></a><a name="kinargtype"></a> CRBTree:: KINARGTYPE

キーが入力引数として渡されるときに使用される型。

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="crbtreekoutargtype"></a><a name="koutargtype"></a> CRBTree:: KOUTARGTYPE

キーが出力引数として返されるときに使用される型。

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="crbtreeremoveall"></a><a name="removeall"></a> CRBTree:: RemoveAll

オブジェクトからすべての要素を削除するには、このメソッドを呼び出し `CRBTree` ます。

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>解説

オブジェクトをクリアし `CRBTree` 、要素の格納に使用されているメモリを解放します。

## <a name="crbtreeremoveat"></a><a name="removeat"></a> CRBTree:: RemoveAt

オブジェクト内の指定された位置にある要素を削除するには、このメソッドを呼び出し `CRBTree` ます。

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
[Crbtree:: GetHeadPosition](#getheadposition)や[Crbtree:: FindFirstKeyAfter](#findfirstkeyafter)などのメソッドの以前の呼び出しによって返された位置カウンター。

### <a name="remarks"></a>解説

指定した位置に格納されているキーと値のペアを削除します。 要素を格納するために使用されるメモリが解放されます。 *Pos*によって参照される位置が無効になり、ツリー内の他の要素の位置が有効なままでも、必ずしも同じ順序で保持されるわけではありません。

## <a name="crbtreesetvalueat"></a><a name="setvalueat"></a> CRBTree:: SetValueAt

オブジェクト内の指定した位置に格納されている値を変更するには、このメソッドを呼び出し `CRBTree` ます。

```cpp
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>パラメーター

*po*<br/>
[Crbtree:: GetHeadPosition](#getheadposition)や[Crbtree:: FindFirstKeyAfter](#findfirstkeyafter)などのメソッドの以前の呼び出しによって返された位置カウンター。

*value*<br/>
オブジェクトに追加する値 `CRBTree` 。

### <a name="remarks"></a>解説

オブジェクト内の指定した位置に格納されている値要素を変更 `CRBTree` します。

## <a name="crbtreevinargtype"></a><a name="vinargtype"></a> CRBTree:: VINARGTYPE

値が入力引数として渡されるときに使用される型。

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="crbtreevoutargtype"></a><a name="voutargtype"></a> CRBTree:: VOUTARGTYPE

値が出力引数として渡されるときに使用される型。

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
