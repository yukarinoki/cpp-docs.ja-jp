---
title: CAtlMap クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
ms.openlocfilehash: b79e6cbd796569e6ba11c96158099de6c30b310a
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168060"
---
# <a name="catlmap-class"></a>CAtlMap クラス

このクラスには、マップオブジェクトを作成および管理するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```cpp
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
```

### <a name="parameters"></a>パラメーター

*Kb*<br/>
キー要素の型。

*画像*<br/>
値要素の型。

*KTraits*<br/>
キー要素をコピーまたは移動するために使用されるコード。 詳細については、「 [Celementtraits クラス](../../atl/reference/celementtraits-class.md)」を参照してください。

*VTraits*<br/>
値要素をコピーまたは移動するために使用されるコード。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CAtlMap:: KINARGTYPE](#kinargtype)|キーが入力引数として渡されるときに使用される型|
|[CAtlMap:: KOUTARGTYPE](#koutargtype)|キーが出力引数として返されるときに使用される型。|
|[CAtlMap:: VINARGTYPE](#vinargtype)|値が入力引数として渡されるときに使用される型。|
|[CAtlMap:: VOUTARGTYPE](#voutargtype)|値が出力引数として渡されるときに使用される型。|

### <a name="public-classes"></a>パブリック クラス

|名前|説明|
|----------|-----------------|
|[CAtlMap:: CPair クラス](#cpair_class)|キー要素と値要素を格納しているクラス。|

### <a name="cpair-data-members"></a>CPair データメンバー

|名前|説明|
|----------|-----------------|
|[CPair:: m_key](#m_key)|キー要素を格納しているデータメンバー。|
|[CPair:: m_value](#m_value)|値要素を格納しているデータメンバー。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAtlMap:: CAtlMap](#catlmap)|コンストラクターです。|
|[CAtlMap:: ~ CAtlMap](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlMap:: AssertValid](#assertvalid)|が有効でない場合に ASSERT を発生`CAtlMap`させるには、このメソッドを呼び出します。|
|[CAtlMap: isableAutoRehash の:D](#disableautorehash)|オブジェクトの自動悪くを無効にするに`CAtlMap`は、このメソッドを呼び出します。|
|[CAtlMap:: EnableAutoRehash](#enableautorehash)|オブジェクトの自動悪くを有効にするに`CAtlMap`は、このメソッドを呼び出します。|
|[CAtlMap:: GetAt](#getat)|Map 内の指定した位置にある要素を返すには、このメソッドを呼び出します。|
|[CAtlMap:: GetCount](#getcount)|Map 内の要素の数を取得するには、このメソッドを呼び出します。|
|[CAtlMap:: GetHashTableSize](#gethashtablesize)|マップのハッシュテーブル内のビン数を確認するには、このメソッドを呼び出します。|
|[CAtlMap:: GetKeyAt](#getkeyat)|`CAtlMap`オブジェクト内の指定した位置に格納されているキーを取得するには、このメソッドを呼び出します。|
|[CAtlMap:: GetNext](#getnext)|`CAtlMap`オブジェクトに格納されている次の要素ペアへのポインターを取得するには、このメソッドを呼び出します。|
|[CAtlMap:: GetNextAssoc](#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CAtlMap:: GetNextKey](#getnextkey)|`CAtlMap`オブジェクトから次のキーを取得するには、このメソッドを呼び出します。|
|[CAtlMap:: GetNextValue](#getnextvalue)|`CAtlMap`オブジェクトから次の値を取得するには、このメソッドを呼び出します。|
|[CAtlMap:: GetStartPosition](#getstartposition)|このメソッドを呼び出して、マップの反復処理を開始します。|
|[CAtlMap:: GetValueAt](#getvalueat)|`CAtlMap`オブジェクト内の指定した位置に格納されている値を取得するには、このメソッドを呼び出します。|
|[CAtlMap:: InitHashTable](#inithashtable)|ハッシュテーブルを初期化するには、このメソッドを呼び出します。|
|[CAtlMap:: IsEmpty](#isempty)|空の map オブジェクトをテストするには、このメソッドを呼び出します。|
|[CAtlMap:: Lookup](#lookup)|オブジェクト内のキーまたは値を参照するに`CAtlMap`は、このメソッドを呼び出します。|
|[CAtlMap:: Rehash](#rehash)|オブジェクトを rehash するには`CAtlMap` 、このメソッドを呼び出します。|
|[CAtlMap:: RemoveAll](#removeall)|オブジェクトからすべての要素を削除するに`CAtlMap`は、このメソッドを呼び出します。|
|[CAtlMap:: RemoveAtPos](#removeatpos)|`CAtlMap`オブジェクト内の指定された位置にある要素を削除するには、このメソッドを呼び出します。|
|[CAtlMap:: RemoveKey](#removekey)|キーを指定して`CAtlMap` 、オブジェクトから要素を削除するには、このメソッドを呼び出します。|
|[CAtlMap:: SetAt](#setat)|Map に要素ペアを挿入するには、このメソッドを呼び出します。|
|[CAtlMap:: SetOptimalLoad](#setoptimalload)|`CAtlMap`オブジェクトの最適な読み込みを設定するには、このメソッドを呼び出します。|
|[CAtlMap:: SetValueAt](#setvalueat)|`CAtlMap`オブジェクト内の指定した位置に格納されている値を変更するには、このメソッドを呼び出します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|新しい要素をに置換または追加`CAtlMap`します。|

## <a name="remarks"></a>解説

`CAtlMap`指定された型のマッピング配列をサポートし、キー要素の順序付けられていない配列および関連する値を管理します。 要素 (キーと値で構成される) は、ハッシュアルゴリズムを使用して格納されます。これにより、大量のデータを効率的に格納および取得できるようになります。

*Ktraits*パラメーターと*vtraits*パラメーターは、要素をコピーまたは移動するために必要な補足コードを含む特徴クラスです。

の代替手段`CAtlMap`は、 [CRBMap](../../atl/reference/crbmap-class.md)クラスによって提供されます。 `CRBMap`にはキーと値のペアも格納されますが、パフォーマンス特性が異なります。 項目の挿入、キーの検索、または`CRBMap`オブジェクトからのキーの削除にかかる時間は、order *log (n)* です。ここで、 *n*は要素の数です。 で`CAtlMap`は、これらすべての操作は通常、一定の時間がかかりますが、最悪のシナリオでは順序*n*である可能性があります。 そのため、一般的なケースで`CAtlMap`は、の方が高速です。

と`CRBMap` `CAtlMap`間のもう1つの違いは、格納されている要素を反復処理するときに明らかになります。 `CRBMap`では、要素は並べ替えられた順序でアクセスされます。 `CAtlMap`では、要素は順序付けされず、順序を推論することはできません。

少数の要素を格納する必要がある場合は、代わりに[CSimpleMap](../../atl/reference/csimplemap-class.md)クラスを使用することを検討してください。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll. h

## <a name="catlmapassertvalid"></a><a name="assertvalid"></a>CAtlMap:: AssertValid

`CAtlMap`オブジェクトが有効でない場合に ASSERT を発生させるには、このメソッドを呼び出します。

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>解説

デバッグビルドでは、 `CAtlMap`オブジェクトが有効でない場合、このメソッドによってアサートが発生します。

### <a name="example"></a>例

「 [Catlmap:: catlmap](#catlmap)」の例を参照してください。

## <a name="catlmapcatlmap"></a><a name="catlmap"></a>CAtlMap:: CAtlMap

コンストラクターです。

```cpp
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```

### <a name="parameters"></a>パラメーター

*nBins*<br/>
格納されている要素へのポインターを提供するビンの数。 ビンの説明については、このトピックの後半の「解説」を参照してください。

*F最適化 Alload*<br/>
最適な負荷比率。

*fLoThreshold*<br/>
負荷比率の下限しきい値。

*fHiThreshold*<br/>
負荷比率の上限しきい値。

*nBlockSize*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

`CAtlMap`最初にキーのハッシュアルゴリズムを使用してインデックスを作成することによって、格納されているすべての要素を参照します。 このインデックスは、格納されている要素へのポインターを含む "bin" を参照します。 ビンが既に使用されている場合は、後続の要素にアクセスするためのリンクリストが作成されます。 リストを走査することは、適切な要素に直接アクセスするよりも低速であるため、マップ構造でストレージ要件とパフォーマンスのバランスを取る必要があります。 既定のパラメーターは、ほとんどの場合に適切な結果を得るために選択されています。

読み込み比率は、マップオブジェクトに格納されている要素の数に対するビン数の比率です。 マップ構造が再計算されると、必要なビン数を計算するために*F最適化 Alload*パラメーター値が使用されます。 この値は、 [CAtlMap:: SetOptimalLoad](#setoptimalload)メソッドを使用して変更できます。

*FLoThreshold*パラメーターは、マップの最適なサイズを再計算する前`CAtlMap`に、負荷比率が達成できる下限値です。

*Fhithreshold*パラメーターは、 `CAtlMap`オブジェクトがマップの最適なサイズを再計算する前に、負荷の比率が到達できる上限値です。

この再計算プロセス (悪くと呼ばれます) は、既定で有効になっています。 このプロセスを無効にする場合は (一度に大量のデータを入力する場合など)、 [CAtlMap::D isableAutoRehash](#disableautorehash)メソッドを呼び出します。 [CAtlMap:: EnableAutoRehash](#enableautorehash)メソッドで再アクティブ化します。

*Nblocksize*パラメーターは、新しい要素が必要な場合に割り当てられるメモリの量を測定したものです。 ブロックサイズを大きくすると、メモリ割り当てルーチンの呼び出しが減少しますが、より多くのリソースが使用されます。

データを格納できるようにするには、まず、 [CAtlMap:: InitHashTable](#inithashtable)を呼び出してハッシュテーブルを初期化する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

## <a name="catlmapcatlmap"></a><a name="dtor"></a>CAtlMap:: ~ CAtlMap

デストラクターです。

```cpp
~CAtlMap() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。

## <a name="catlmapcpair-class"></a><a name="cpair_class"></a>CAtlMap:: CPair クラス

キー要素と値要素を格納しているクラス。

```cpp
class CPair : public __POSITION
```

### <a name="remarks"></a>解説

このクラスは、マップ構造体に格納されているキー要素と値要素にアクセスするために、 [catlmap:: GetNext](#getnext)メソッドおよび[Catlmap:: Lookup](#lookup)メソッドによって使用されます。

## <a name="catlmapdisableautorehash"></a><a name="disableautorehash"></a>CAtlMap: isableAutoRehash の:D

オブジェクトの自動悪くを無効にするに`CAtlMap`は、このメソッドを呼び出します。

```cpp
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>解説

自動悪くが有効になっている場合 (既定では)、読み込み値 (配列に格納されている要素の数に対するビン数の比率) がマップの作成時に指定された最大値または最小値を超えた場合、ハッシュテーブル内のビンの数が自動的に再計算されます。

`DisableAutoRehash`は、多数の要素が一度にマップに追加される場合に最も役立ちます。 制限を超えたときに悪くプロセスをトリガーするのではなく、を呼び出し`DisableAutoRehash`て要素を追加し、最後に[CAtlMap:: enableautorehash](#enableautorehash)を呼び出す方が効率的です。

## <a name="catlmapenableautorehash"></a><a name="enableautorehash"></a>CAtlMap:: EnableAutoRehash

オブジェクトの自動悪くを有効にするに`CAtlMap`は、このメソッドを呼び出します。

```cpp
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>解説

自動悪くが有効になっている場合 (既定では)、読み込み値 (配列に格納されている要素の数に対するビン数の比率) がマップの作成時に指定された最大値または最小値を超えた場合、ハッシュテーブル内のビンの数が自動的に再計算されます。

`EnableAutoRefresh`は、 [CAtlMap::D isableAutoRehash](#disableautorehash)の呼び出しの後で最もよく使用されます。

## <a name="catlmapgetat"></a><a name="getat"></a>CAtlMap:: GetAt

Map 内の指定した位置にある要素を返すには、このメソッドを呼び出します。

```cpp
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前に[catlmap:: GetNextAssoc](#getnextassoc)または[Catlmap:: GetStartPosition](#getstartposition)を呼び出したときに返された位置カウンター。

*key*<br/>
マップのキーの種類を指定するテンプレートパラメーター。

*value*<br/>
マップの値の型を指定するテンプレートパラメーター。

### <a name="return-value"></a>戻り値

Map に格納されているキー/値要素の現在のペアへのポインターを返します。

### <a name="remarks"></a>解説

デバッグビルドでは、 *pos*が NULL と等しい場合にアサーションエラーが発生します。

## <a name="catlmapgetcount"></a><a name="getcount"></a>CAtlMap:: GetCount

Map 内の要素の数を取得するには、このメソッドを呼び出します。

```cpp
size_t GetCount() const throw();
```

### <a name="return-value"></a>戻り値

Map オブジェクト内の要素の数を返します。 1つの要素は、キーと値のペアです。

### <a name="example"></a>例

「 [Catlmap:: catlmap](#catlmap)」の例を参照してください。

## <a name="catlmapgethashtablesize"></a><a name="gethashtablesize"></a>CAtlMap:: GetHashTableSize

マップのハッシュテーブル内のビン数を確認するには、このメソッドを呼び出します。

```cpp
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>戻り値

ハッシュテーブル内のビン数を返します。 説明については、「 [catlmap:: catlmap](#catlmap) 」を参照してください。

## <a name="catlmapgetkeyat"></a><a name="getkeyat"></a>CAtlMap:: GetKeyAt

`CAtlMap`オブジェクト内の指定した位置に格納されているキーを取得するには、このメソッドを呼び出します。

```cpp
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前に[catlmap:: GetNextAssoc](#getnextassoc)または[Catlmap:: GetStartPosition](#getstartposition)を呼び出したときに返された位置カウンター。

### <a name="return-value"></a>戻り値

`CAtlMap`オブジェクト内の指定した位置に格納されているキーへの参照を返します。

### <a name="example"></a>例

「 [Catlmap:: catlmap](#catlmap)」の例を参照してください。

## <a name="catlmapgetnext"></a><a name="getnext"></a>CAtlMap:: GetNext

`CAtlMap`オブジェクトに格納されている次の要素ペアへのポインターを取得するには、このメソッドを呼び出します。

```cpp
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前に[catlmap:: GetNextAssoc](#getnextassoc)または[Catlmap:: GetStartPosition](#getstartposition)を呼び出したときに返された位置カウンター。

### <a name="return-value"></a>戻り値

Map に格納されている次のキー/値要素のペアへのポインターを返します。 各呼び出しの後に、 *pos*位置カウンターが更新されます。 取得した要素が map 内の最後の要素である場合、 *pos*は NULL に設定されます。

## <a name="catlmapgetnextassoc"></a><a name="getnextassoc"></a>CAtlMap:: GetNextAssoc

反復処理の対象となる次の要素を取得します。

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前に[catlmap:: GetNextAssoc](#getnextassoc)または[Catlmap:: GetStartPosition](#getstartposition)を呼び出したときに返された位置カウンター。

*key*<br/>
マップのキーの種類を指定するテンプレートパラメーター。

*value*<br/>
マップの値の型を指定するテンプレートパラメーター。

### <a name="remarks"></a>解説

各呼び出しの後に、 *pos*位置カウンターが更新されます。 取得した要素が map 内の最後の要素である場合、 *pos*は NULL に設定されます。

## <a name="catlmapgetnextkey"></a><a name="getnextkey"></a>CAtlMap:: GetNextKey

`CAtlMap`オブジェクトから次のキーを取得するには、このメソッドを呼び出します。

```cpp
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前に[catlmap:: GetNextAssoc](#getnextassoc)または[Catlmap:: GetStartPosition](#getstartposition)を呼び出したときに返された位置カウンター。

### <a name="return-value"></a>戻り値

Map 内の次のキーへの参照を返します。

### <a name="remarks"></a>解説

現在の位置カウンター ( *pos*) を更新します。マップにエントリがこれ以上ない場合、position カウンターは NULL に設定されます。

## <a name="catlmapgetnextvalue"></a><a name="getnextvalue"></a>CAtlMap:: GetNextValue

`CAtlMap`オブジェクトから次の値を取得するには、このメソッドを呼び出します。

```cpp
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前に[catlmap:: GetNextAssoc](#getnextassoc)または[Catlmap:: GetStartPosition](#getstartposition)を呼び出したときに返された位置カウンター。

### <a name="return-value"></a>戻り値

Map 内の次の値への参照を返します。

### <a name="remarks"></a>解説

現在の位置カウンター ( *pos*) を更新します。マップにエントリがこれ以上ない場合、position カウンターは NULL に設定されます。

### <a name="example"></a>例

「 [Catlmap:: catlmap](#catlmap)」の例を参照してください。

## <a name="catlmapgetstartposition"></a><a name="getstartposition"></a>CAtlMap:: GetStartPosition

このメソッドを呼び出して、マップの反復処理を開始します。

```cpp
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>戻り値

開始位置を返します。マップが空の場合は NULL が返されます。

### <a name="remarks"></a>解説

このメソッドを呼び出して、 `GetNextAssoc`メソッドに渡すことができる位置の値を返すことによって、マップの反復を開始します。

> [!NOTE]
> イテレーションシーケンスは予測可能ではありません

### <a name="example"></a>例

「 [Catlmap:: catlmap](#catlmap)」の例を参照してください。

## <a name="catlmapgetvalueat"></a><a name="getvalueat"></a>CAtlMap:: GetValueAt

`CAtlMap`オブジェクト内の指定した位置に格納されている値を取得するには、このメソッドを呼び出します。

```cpp
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前に[catlmap:: GetNextAssoc](#getnextassoc)または[Catlmap:: GetStartPosition](#getstartposition)を呼び出したときに返された位置カウンター。

### <a name="return-value"></a>戻り値

`CAtlMap`オブジェクト内の指定した位置に格納されている値への参照を返します。

## <a name="catlmapinithashtable"></a><a name="inithashtable"></a>CAtlMap:: InitHashTable

ハッシュテーブルを初期化するには、このメソッドを呼び出します。

```cpp
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>パラメーター

*nBins*<br/>
ハッシュテーブルによって使用されるビンの数。 説明については、「 [catlmap:: catlmap](#catlmap) 」を参照してください。

*今すぐ*<br/>
メモリを割り当てるかどうかを示すフラグ。

### <a name="return-value"></a>戻り値

正常に初期化された場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`InitHashTable`要素がハッシュテーブルに格納される前に、を呼び出す必要があります。  このメソッドが明示的に呼び出されない場合は、 `CAtlMap`コンストラクターによって指定されたビン数を使用して要素が初めて追加されたときに、自動的に呼び出されます。  それ以外の場合は、 *nbins*パラメーターによって指定された新しいビン数を使用してマップが初期化されます。

このパラメーター*が false の場合*、ハッシュテーブルに必要なメモリは、最初に必要になるまで割り当てられません。 これは、マップが使用されるかどうかが不明な場合に便利です。

### <a name="example"></a>例

「 [Catlmap:: catlmap](#catlmap)」の例を参照してください。

## <a name="catlmapisempty"></a><a name="isempty"></a>CAtlMap:: IsEmpty

空の map オブジェクトをテストするには、このメソッドを呼び出します。

```cpp
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

マップが空の場合は TRUE、それ以外の場合は FALSE を返します。

## <a name="catlmapkinargtype"></a><a name="kinargtype"></a>CAtlMap:: KINARGTYPE

キーが入力引数として渡されるときに使用される型。

```cpp
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="catlmapkoutargtype"></a><a name="koutargtype"></a>CAtlMap:: KOUTARGTYPE

キーが出力引数として返されるときに使用される型。

```cpp
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="catlmaplookup"></a><a name="lookup"></a>CAtlMap:: Lookup

オブジェクト内のキーまたは値を参照するに`CAtlMap`は、このメソッドを呼び出します。

```cpp
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索する要素を識別するキーを指定します。

*value*<br/>
検索対象の値を受け取る変数。

### <a name="return-value"></a>戻り値

メソッドの最初の形式は、キーが見つかった場合は true、それ以外の場合は false を返します。 2番目と3番目のフォームは、 [CPair](#cpair_class)へのポインターを返します。これは、 [CAtlMap:: GetNext](#getnext)の呼び出しの位置として使用できます。

### <a name="remarks"></a>解説

`Lookup`ハッシュアルゴリズムを使用して、指定されたキーパラメーターと完全に一致するキーを含む map 要素をすばやく検索します。

## <a name="catlmapoperator-"></a><a name="operator_at"></a>CAtlMap:: 演算子\[\]

新しい要素をに置換または追加`CAtlMap`します。

```cpp
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
追加または置換する要素のキー。

### <a name="return-value"></a>戻り値

指定されたキーに関連付けられている値への参照を返します。

### <a name="example"></a>例

キーが既に存在する場合は、要素が置き換えられます。 キーが存在しない場合は、新しい要素が追加されます。 「 [Catlmap:: catlmap](#catlmap)」の例を参照してください。

## <a name="catlmaprehash"></a><a name="rehash"></a>CAtlMap:: Rehash

オブジェクトを rehash するには`CAtlMap` 、このメソッドを呼び出します。

```cpp
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>パラメーター

*nBins*<br/>
ハッシュテーブルで使用する新しいビンの数。 説明については、「 [catlmap:: catlmap](#catlmap) 」を参照してください。

### <a name="remarks"></a>解説

*Nbins*が0の場合`CAtlMap` 、は、マップ内の要素数と最適な読み込み設定に基づいて、適切な数を計算します。 通常、悪くプロセスは自動的に行われますが、 [CAtlMap::D isableAutoRehash](#disableautorehash)が呼び出されている場合、このメソッドは必要なサイズ変更を実行します。

## <a name="catlmapremoveall"></a><a name="removeall"></a>CAtlMap:: RemoveAll

オブジェクトからすべての要素を削除するに`CAtlMap`は、このメソッドを呼び出します。

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>解説

`CAtlMap`オブジェクトをクリアし、要素の格納に使用されているメモリを解放します。

## <a name="catlmapremoveatpos"></a><a name="removeatpos"></a>CAtlMap:: RemoveAtPos

`CAtlMap`オブジェクト内の指定された位置にある要素を削除するには、このメソッドを呼び出します。

```cpp
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前に[catlmap:: GetNextAssoc](#getnextassoc)または[Catlmap:: GetStartPosition](#getstartposition)を呼び出したときに返された位置カウンター。

### <a name="remarks"></a>解説

指定した位置に格納されているキーと値のペアを削除します。 要素を格納するために使用されるメモリが解放されます。 *Pos*によって参照される位置が無効になり、マップ内の他の要素の位置が有効なままでも、必ずしも同じ順序で保持されるわけではありません。

## <a name="catlmapremovekey"></a><a name="removekey"></a>CAtlMap:: RemoveKey

キーを指定して`CAtlMap` 、オブジェクトから要素を削除するには、このメソッドを呼び出します。

```cpp
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
削除する要素ペアに対応するキー。

### <a name="return-value"></a>戻り値

キーが見つかって削除された場合は TRUE、失敗した場合は FALSE を返します。

### <a name="example"></a>例

「 [Catlmap:: catlmap](#catlmap)」の例を参照してください。

## <a name="catlmapsetat"></a><a name="setat"></a>CAtlMap:: SetAt

Map に要素ペアを挿入するには、このメソッドを呼び出します。

```cpp
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
`CAtlMap`オブジェクトに追加するキー値。

*value*<br/>
`CAtlMap`オブジェクトに追加する値。

### <a name="return-value"></a>戻り値

`CAtlMap`オブジェクト内のキーと値の要素のペアの位置を返します。

### <a name="remarks"></a>解説

`SetAt`一致するキーが見つかった場合は、既存の要素を置き換えます。 キーが見つからない場合は、新しいキーと値のペアが作成されます。

## <a name="catlmapsetoptimalload"></a><a name="setoptimalload"></a>CAtlMap:: SetOptimalLoad

`CAtlMap`オブジェクトの最適な読み込みを設定するには、このメソッドを呼び出します。

```cpp
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>パラメーター

*F最適化 Alload*<br/>
最適な負荷比率。

*fLoThreshold*<br/>
負荷比率の下限しきい値。

*fHiThreshold*<br/>
負荷比率の上限しきい値。

*現在の hash*<br/>
ハッシュテーブルを再計算する必要があるかどうかを示すフラグです。

### <a name="remarks"></a>解説

このメソッドは、 `CAtlMap`オブジェクトの最適な読み込み値を再定義します。 さまざまなパラメーターの詳細については、「 [catlmap:: catlmap](#catlmap) 」を参照してください。 *現在*の値が true であり、要素の数が最小値と最大値の範囲外である場合、ハッシュテーブルが再計算されます。

## <a name="catlmapsetvalueat"></a><a name="setvalueat"></a>CAtlMap:: SetValueAt

`CAtlMap`オブジェクト内の指定した位置に格納されている値を変更するには、このメソッドを呼び出します。

```cpp
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>パラメーター

*po*<br/>
以前に[catlmap:: GetNextAssoc](#getnextassoc)または[Catlmap:: GetStartPosition](#getstartposition)を呼び出したときに返された位置カウンター。

*value*<br/>
`CAtlMap`オブジェクトに追加する値。

### <a name="remarks"></a>解説

`CAtlMap`オブジェクト内の指定した位置に格納されている値要素を変更します。

## <a name="catlmapvinargtype"></a><a name="vinargtype"></a>CAtlMap:: VINARGTYPE

値が入力引数として渡されるときに使用される型。

```cpp
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="catlmapvoutargtype"></a><a name="voutargtype"></a>CAtlMap:: VOUTARGTYPE

値が出力引数として渡されるときに使用される型。

```cpp
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="catlmapcpairm_key"></a><a name="m_key"></a>CAtlMap:: CPair:: m_key

キー要素を格納しているデータメンバー。

```cpp
const K m_key;
```

### <a name="parameters"></a>パラメーター

*Kb*<br/>
キー要素の型。

## <a name="catlmapcpairm_value"></a><a name="m_value"></a>CAtlMap:: CPair:: m_value

値要素を格納しているデータメンバー。

```cpp
V  m_value;
```

### <a name="parameters"></a>パラメーター

*画像*<br/>
値要素の型。

## <a name="see-also"></a>関連項目

[Marquee サンプル](../../overview/visual-cpp-samples.md)<br/>
[UpdatePV サンプル](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
