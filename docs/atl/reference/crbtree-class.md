---
title: クラス
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
ms.openlocfilehash: 56c9db9d1a7bcd7fe2a2647d8b1339d223c4b66b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331244"
---
# <a name="crbtree-class"></a>クラス

このクラスは、レッドブラック ツリーを作成して使用するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBTree
```

#### <a name="parameters"></a>パラメーター

*K*<br/>
キー要素の型。

*V*<br/>
値要素の型。

*クトレイツ*<br/>
キー要素のコピーまたは移動に使用されるコード。 詳細については[、「CElementTraits クラス](../../atl/reference/celementtraits-class.md)」を参照してください。

*VTraits*<br/>
値要素のコピーまたは移動に使用されるコード。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CRBツリー:キナルグタイプ](#kinargtype)|キーが入力引数として渡されるときに使用される型。|
|[クエブツリー::クアージタイプ](#koutargtype)|キーが出力引数として返されるときに使用される型。|
|[クレブツリー::ヴィナージタイプ](#vinargtype)|値が入力引数として渡されるときに使用される型。|
|[クヴツリー::ヴルトアルグタイプ](#voutargtype)|値が出力引数として渡されるときに使用される型。|

### <a name="public-classes"></a>パブリック クラス

|名前|説明|
|----------|-----------------|
|[クラスを組み合わせる](#cpair_class)|キーと値の要素を含むクラス。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRBツリー::~CRBツリー](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRBツリー::後に最初のキーを見つける](#findfirstkeyafter)|次に使用可能なキーを使用する要素の位置を検索します。|
|[クレブツリー::ゲットアット](#getat)|ツリー内の指定した位置にある要素を取得します。|
|[を取得します。](#getcount)|ツリー内の要素の数を取得します。|
|[CRBツリー::ゲットヘッドポジション](#getheadposition)|ツリーの先頭にある要素の位置の値を取得します。|
|[クレブツリー::ゲットキーアット](#getkeyat)|ツリー内の指定された位置からキーを取得します。|
|[次の値を取得します。](#getnext)|`CRBTree`オブジェクトに格納されている要素へのポインターを取得し、次の要素に位置を進めます。|
|[CRBツリー::ゲットネクストアソック](#getnextassoc)|マップに格納されている要素のキーと値を取得し、次の要素に位置を進めます。|
|[次のキーを取得します。](#getnextkey)|ツリーに格納されている要素のキーを取得し、次の要素に位置を進めます。|
|[次の値を取得します。](#getnextvalue)|ツリーに格納されている要素の値を取得し、次の要素に位置を進めます。|
|[CRBツリー::ゲットプレフ](#getprev)|`CRBTree`オブジェクトに格納されている要素へのポインターを取得し、前の要素に位置を更新します。|
|[CRBツリー::ゲットテールポジション](#gettailposition)|ツリーの末尾にある要素の位置の値を取得します。|
|[を取得します。](#getvalueat)|`CRBTree`オブジェクト内の指定した位置に格納されている値を取得します。|
|[クレブツリー::IsEmpty](#isempty)|空のツリー オブジェクトをテストします。|
|[すべてを削除します。](#removeall)|`CRBTree`オブジェクトからすべての要素を削除します。|
|[CRBツリー::削除アット](#removeat)|`CRBTree`オブジェクト内の指定した位置にある要素を削除します。|
|[を設定します。](#setvalueat)|`CRBTree`オブジェクト内の指定した位置に格納されている値を変更します。|

## <a name="remarks"></a>解説

Red-Black ツリーは、ノードごとに追加の情報を使用して、ツリーの高さが不均衡に大きくならず、パフォーマンスに影響を与えないようにするバイナリ検索ツリーです。

このテンプレート クラスは[、CRBMap](../../atl/reference/crbmap-class.md)および[CRBMultiMap](../../atl/reference/crbmultimap-class.md)で使用するように設計されています。 これらの派生クラスを構成するメソッドの大部分は、 によって`CRBTree`提供されます。

さまざまなコレクション クラスとその機能とパフォーマンス特性の詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="crbtreecpair-class"></a><a name="cpair_class"></a>クラスを組み合わせる

キーと値の要素を含むクラス。

```
class CPair : public __POSITION
```

### <a name="remarks"></a>解説

このクラスは、ツリー構造に格納されているキー要素と値要素にアクセスするために[、CRBTree::GetAt、CRBTree::](#getat)[および](#getnext) [CRBTree::GetPrev](#getprev)メソッドによって使用されます。

メンバーは次のとおりです。

|||
|-|-|
|`m_key`|キー要素を格納するデータ メンバー。|
|`m_value`|値要素を格納するデータ メンバー。|

## <a name="crbtreecrbtree"></a><a name="dtor"></a>CRBツリー::~CRBツリー

デストラクターです。

```
~CRBTree() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。 すべての要素を削除するには[、CRBTree::RemoveAll](#removeall)を呼び出します。

## <a name="crbtreefindfirstkeyafter"></a><a name="findfirstkeyafter"></a>CRBツリー::後に最初のキーを見つける

次に使用可能なキーを使用する要素の位置を検索します。

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
キー値。

### <a name="return-value"></a>戻り値

次に使用可能なキーを使用する要素の位置の値を返します。 要素がなくなった場合は、NULL が返されます。

### <a name="remarks"></a>解説

この方法を使用すると、事前に位置値を計算しなくても、ツリーを簡単に走査できます。

## <a name="crbtreegetat"></a><a name="getat"></a>クレブツリー::ゲットアット

ツリー内の指定した位置にある要素を取得します。

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
位置を表す値です。

*key*<br/>
キーを受け取る変数。

*value*<br/>
値を受け取る変数。

### <a name="return-value"></a>戻り値

最初の 2 つのフォームは[、CPair](#cpair_class)へのポインタを返します。 3 番目の形式は、指定された位置のキーと値を取得します。

### <a name="remarks"></a>解説

位置の値は[、CRBTree:::GetHeadPosition](#getheadposition)または[CRBTree::GetTailPosition](#gettailposition)などのメソッドの呼び出しで以前に決定できます。

デバッグ ビルドでは *、pos*が NULL に等しい場合、アサーション エラーが発生します。

## <a name="crbtreegetcount"></a><a name="getcount"></a>を取得します。

ツリー内の要素の数を取得します。

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>戻り値

ツリーに格納されている要素の数 (各キー/値ペアは 1 つの要素) を返します。

## <a name="crbtreegetheadposition"></a><a name="getheadposition"></a>CRBツリー::ゲットヘッドポジション

ツリーの先頭にある要素の位置の値を取得します。

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>戻り値

ツリーの先頭にある要素の位置の値を返します。

### <a name="remarks"></a>解説

返される`GetHeadPosition`値は[、CRBTree:::GetKeyAt](#getkeyat)または[CRBTree::GetNext](#getnext)などのメソッドで使用して、ツリーを走査して値を取得できます。

## <a name="crbtreegetkeyat"></a><a name="getkeyat"></a>クレブツリー::ゲットキーアット

ツリー内の指定された位置からキーを取得します。

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
位置を表す値です。

### <a name="return-value"></a>戻り値

ツリー内の位置*pos*に格納されているキーを返します。

### <a name="remarks"></a>解説

*pos*が有効なポジション値でない場合、結果は予測できません。 デバッグ ビルドでは *、pos*が NULL に等しい場合、アサーション エラーが発生します。

## <a name="crbtreegetnext"></a><a name="getnext"></a>次の値を取得します。

`CRBTree`オブジェクトに格納されている要素へのポインターを取得し、次の要素に位置を進めます。

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRB ツリー::GetHead位置](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)などのメソッドへの以前の呼び出しによって返される位置カウンター。

### <a name="return-value"></a>戻り値

ツリー内の次の[CPair](#cpair_class)値へのポインターを返します。

### <a name="remarks"></a>解説

*pos*位置カウンターは、各呼び出しの後に更新されます。 取得した要素がツリーの最後の要素である場合 *、pos*は NULL に設定されます。

## <a name="crbtreegetnextassoc"></a><a name="getnextassoc"></a>CRBツリー::ゲットネクストアソック

マップに格納されている要素のキーと値を取得し、次の要素に位置を進めます。

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRB ツリー::GetHead位置](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)などのメソッドへの以前の呼び出しによって返される位置カウンター。

*key*<br/>
ツリーのキーの種類を指定するテンプレート パラメーター。

*value*<br/>
ツリーの値の型を指定するテンプレート パラメーター。

### <a name="remarks"></a>解説

*pos*位置カウンターは、各呼び出しの後に更新されます。 取得した要素がツリーの最後の要素である場合 *、pos*は NULL に設定されます。

## <a name="crbtreegetnextkey"></a><a name="getnextkey"></a>次のキーを取得します。

ツリーに格納されている要素のキーを取得し、次の要素に位置を進めます。

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRB ツリー::GetHead位置](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)などのメソッドへの以前の呼び出しによって返される位置カウンター。

### <a name="return-value"></a>戻り値

ツリー内の次のキーへの参照を返します。

### <a name="remarks"></a>解説

現在の位置カウンタ*pos*を更新します。ツリーにエントリがなくなった場合、位置カウンタは NULL に設定されます。

## <a name="crbtreegetnextvalue"></a><a name="getnextvalue"></a>次の値を取得します。

ツリーに格納されている要素の値を取得し、次の要素に位置を進めます。

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRB ツリー::GetHead位置](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)などのメソッドへの以前の呼び出しによって返される位置カウンター。

### <a name="return-value"></a>戻り値

ツリー内の次の値への参照を返します。

### <a name="remarks"></a>解説

現在の位置カウンタ*pos*を更新します。ツリーにエントリがなくなった場合、位置カウンタは NULL に設定されます。

## <a name="crbtreegetprev"></a><a name="getprev"></a>CRBツリー::ゲットプレフ

`CRBTree`オブジェクトに格納されている要素へのポインターを取得し、前の要素に位置を更新します。

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRB ツリー::GetHead位置](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)などのメソッドへの以前の呼び出しによって返される位置カウンター。

### <a name="return-value"></a>戻り値

ツリーに格納されている前の[CPair](#cpair_class)値へのポインターを返します。

### <a name="remarks"></a>解説

現在の位置カウンタ*pos*を更新します。ツリーにエントリがなくなった場合、位置カウンタは NULL に設定されます。

## <a name="crbtreegettailposition"></a><a name="gettailposition"></a>CRBツリー::ゲットテールポジション

ツリーの末尾にある要素の位置の値を取得します。

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>戻り値

ツリーの末尾にある要素の位置の値を返します。

### <a name="remarks"></a>解説

返される`GetTailPosition`値は[、CRBTree:::GetKeyAt](#getkeyat)または[CRBTree::GetPrev](#getprev)などのメソッドで使用して、ツリーを走査し、値を取得できます。

## <a name="crbtreegetvalueat"></a><a name="getvalueat"></a>を取得します。

`CRBTree`オブジェクト内の指定した位置に格納されている値を取得します。

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRB ツリー::GetHead位置](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)などのメソッドへの以前の呼び出しによって返される位置カウンター。

### <a name="return-value"></a>戻り値

オブジェクト内の指定された位置に格納されている値への参照を`CRBTree`返します。

## <a name="crbtreeisempty"></a><a name="isempty"></a>クレブツリー::IsEmpty

空のツリー オブジェクトをテストします。

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

ツリーが空の場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="crbtreekinargtype"></a><a name="kinargtype"></a>CRBツリー:キナルグタイプ

キーが入力引数として渡されるときに使用される型。

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="crbtreekoutargtype"></a><a name="koutargtype"></a>クエブツリー::クアージタイプ

キーが出力引数として返されるときに使用される型。

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="crbtreeremoveall"></a><a name="removeall"></a>すべてを削除します。

`CRBTree`オブジェクトからすべての要素を削除します。

```
void RemoveAll() throw();
```

### <a name="remarks"></a>解説

オブジェクトを`CRBTree`クリアし、要素の格納に使用するメモリを解放します。

## <a name="crbtreeremoveat"></a><a name="removeat"></a>CRBツリー::削除アット

`CRBTree`オブジェクト内の指定した位置にある要素を削除します。

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRB ツリー::GetHead位置](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)などのメソッドへの以前の呼び出しによって返される位置カウンター。

### <a name="remarks"></a>解説

指定した位置に格納されているキーと値のペアを削除します。 要素の格納に使用されるメモリが解放されます。 *pos*によって参照される POSITION は無効になり、ツリー内の他の要素の POSITION は有効なままですが、必ずしも同じ順序を保持するとは限りません。

## <a name="crbtreesetvalueat"></a><a name="setvalueat"></a>を設定します。

`CRBTree`オブジェクト内の指定した位置に格納されている値を変更します。

```
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
[CRB ツリー::GetHead位置](#getheadposition)または[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)などのメソッドへの以前の呼び出しによって返される位置カウンター。

*value*<br/>
オブジェクトに追加する`CRBTree`値。

### <a name="remarks"></a>解説

オブジェクト内の指定された位置に格納されている値要素`CRBTree`を変更します。

## <a name="crbtreevinargtype"></a><a name="vinargtype"></a>クレブツリー::ヴィナージタイプ

値が入力引数として渡されるときに使用される型。

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="crbtreevoutargtype"></a><a name="voutargtype"></a>クヴツリー::ヴルトアルグタイプ

値が出力引数として渡されるときに使用される型。

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
