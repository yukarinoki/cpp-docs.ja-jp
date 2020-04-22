---
title: カトルマップクラス
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
ms.openlocfilehash: 8954eeae28f13fb50643646b41c032588ecc278f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748654"
---
# <a name="catlmap-class"></a>カトルマップクラス

このクラスには、マップ オブジェクトを作成および管理するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
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
|[カトルマップ::キナルグタイプ](#kinargtype)|キーが入力引数として渡されたときに使用される型|
|[カトルマップ::コウトアルグタイプ](#koutargtype)|キーが出力引数として返されるときに使用される型。|
|[カトルマップ::ヴィナーグタイプ](#vinargtype)|値が入力引数として渡されるときに使用される型。|
|[カトルマップ::ヴートアルグタイプ](#voutargtype)|値が出力引数として渡されるときに使用される型。|

### <a name="public-classes"></a>パブリック クラス

|名前|説明|
|----------|-----------------|
|[CAtlMap::CPairクラス](#cpair_class)|キーと値の要素を含むクラス。|

### <a name="cpair-data-members"></a>CPair データ メンバー

|名前|説明|
|----------|-----------------|
|[ペア::m_key](#m_key)|キー要素を格納するデータ メンバー。|
|[ペア::m_value](#m_value)|値要素を格納するデータ メンバー。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[カトルマップ::カトルマップ](#catlmap)|コンストラクターです。|
|[カトルマップ::~カトルマップ](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[カトルマップ::アサートValid](#assertvalid)|が無効な場合に ASSERT を`CAtlMap`発生させる場合に、このメソッドを呼び出します。|
|[カトルマップ::D可能なオートレハッシュ](#disableautorehash)|`CAtlMap`オブジェクトの自動再ハッシュを無効にします。|
|[カトルマップ::オートレハッシュを有効にする](#enableautorehash)|`CAtlMap`オブジェクトの自動再ハッシュを有効にします。|
|[カトルマップ::ゲットアット](#getat)|マップ内の指定した位置にある要素を返します。|
|[カトルマップ::ゲットカウント](#getcount)|マップ内の要素の数を取得します。|
|[カトルマップ::ゲットハッシュテーブルサイズ](#gethashtablesize)|マップのハッシュ テーブル内のビンの数を調べます。|
|[カトルマップ::ゲットキーアット](#getkeyat)|オブジェクト内の指定した位置に格納されているキーを`CAtlMap`取得します。|
|[カトルマップ::次に取得します](#getnext)|オブジェクトに格納されている次の要素ペアへのポインターを`CAtlMap`取得します。|
|[カトルマップ::ゲットネクストアソック](#getnextassoc)|反復処理の次の要素を取得します。|
|[カトルマップ::ゲットネクストキー](#getnextkey)|`CAtlMap`オブジェクトから次のキーを取得します。|
|[カトルマップ::次に値を取得します。](#getnextvalue)|`CAtlMap`オブジェクトから次の値を取得します。|
|[カトルマップ::ゲットスタートポジション](#getstartposition)|マップの反復処理を開始します。|
|[カトルマップ::ゲットバリューアット](#getvalueat)|`CAtlMap`オブジェクト内の指定した位置に格納されている値を取得します。|
|[カトルマップ::イニトハッシュテーブル](#inithashtable)|ハッシュ テーブルを初期化します。|
|[カトルマップ::IsEmpty](#isempty)|空のマップ オブジェクトをテストします。|
|[カトルマップ::ルックアップ](#lookup)|`CAtlMap`オブジェクト内のキーまたは値を検索します。|
|[カトルマップ::再ハッシュ](#rehash)|`CAtlMap`オブジェクトを再ハッシュします。|
|[カトルマップ::すべて削除](#removeall)|`CAtlMap`オブジェクトからすべての要素を削除します。|
|[カトルマップ::削除アトポス](#removeatpos)|`CAtlMap`オブジェクト内の指定した位置にある要素を削除します。|
|[キーの割り当て::キーの削除](#removekey)|キーを指定して、オブジェクトから要素を`CAtlMap`削除します。|
|[カトルマップ::セットアット](#setat)|マップに要素ペアを挿入します。|
|[カトルマップ::設定最適なロード](#setoptimalload)|`CAtlMap`オブジェクトの最適な負荷を設定します。|
|[カトルマップ::セットバリューアット](#setvalueat)|`CAtlMap`オブジェクト内の指定した位置に格納されている値を変更します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|新しい要素を置き換えるか、`CAtlMap`新しい要素を 追加します。|

## <a name="remarks"></a>解説

`CAtlMap`は、キー要素とその関連値の順序なし配列を管理する、任意の型のマッピング配列をサポートします。 要素 (キーと値で構成される) はハッシュ アルゴリズムを使用して格納されるため、大量のデータを効率的に格納および取得できます。

*KTraits*パラメーターと*VTraits*パラメーターは、要素のコピーまたは移動に必要な補足コードを含む traits クラスです。

代替の代`CAtlMap`わりとして[、CRBMap](../../atl/reference/crbmap-class.md)クラスが提供します。 `CRBMap`キーと値のペアも格納しますが、パフォーマンス特性は異なります。 項目の挿入、キーの検索、または`CRBMap`オブジェクトからのキーの削除に要する時間は、order *log(n) です*。 *n* の`CAtlMap`場合、これらの操作はすべて一定の時間を要しますが、最悪の場合のシナリオは*順序 n*になります。 したがって、典型的な場合には、`CAtlMap`より速い。

格納された要素を`CRBMap`反復`CAtlMap`処理するときに、その他の違いが明らかになります。 `CRBMap`では、要素は並べ替えられた順序で参照されます。 `CAtlMap`では、要素は順序付けされず、順序を推論することはできません。

少数の要素を格納する必要がある場合は、代わりに[CSimpleMap](../../atl/reference/csimplemap-class.md)クラスを使用することを検討してください。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="catlmapassertvalid"></a><a name="assertvalid"></a>カトルマップ::アサートValid

オブジェクトが無効な場合に ASSERT`CAtlMap`を発生させます。

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>解説

デバッグ ビルドでは、オブジェクトが有効でない場合、この`CAtlMap`メソッドによって ASSERT が発生します。

### <a name="example"></a>例

[CAtlMap::CAtlMap](#catlmap)の例を参照してください。

## <a name="catlmapcatlmap"></a><a name="catlmap"></a>カトルマップ::カトルマップ

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

*nビン*<br/>
格納された要素へのポインターを提供するビンの数。 ビンの詳細については、このトピックの後半の「解説」を参照してください。

*を行う*<br/>
最適な負荷比。

*フロしきい値*<br/>
負荷率の下限しきい値。

*フヒスレッショルド*<br/>
負荷率の上限しきい値。

*ブロックサイズ*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

`CAtlMap`は、キーにハッシュ アルゴリズムを使用してインデックスを作成することで、格納されているすべての要素を参照します。 このインデックスは、格納された要素へのポインターを含む "bin" を参照します。 ビンが既に使用されている場合は、後続の要素にアクセスするためのリンク リストが作成されます。 リストを走査する方が、正しい要素に直接アクセスするよりも遅いので、マップ構造はストレージ要件とパフォーマンスのバランスを取る必要があります。 ほとんどの場合、良好な結果を得るためにデフォルトのパラメータが選択されています。

読み込み率は、マップ オブジェクトに格納されている要素の数に対するビン数の比率です。 マップ構造が再計算されると *、fOptimalLoad*パラメーター値を使用して必要なビンの数が計算されます。 この値は[、CAtlMap::SetOptimalLoad](#setoptimalload)メソッドを使用して変更できます。

*fLoThreshold*パラメーターは、マップの最適なサイズを再計算する前`CAtlMap`に、負荷比率が到達できる低い値です。

*fHiThreshold*パラメーターは、オブジェクトがマップの最適なサイズを`CAtlMap`再計算する前に、負荷比率に到達できる上限値です。

この再計算プロセス (再ハッシュと呼ばれます) は、既定で有効になっています。 このプロセスを無効にする場合は、大量のデータを一度に入力する場合は[、CAtlMap::DisableAutoRehash](#disableautorehash)メソッドを呼び出します。 [CAtlMap::有効化オートレハッシュ](#enableautorehash)メソッドを使用して再アクティブ化します。

*nBlockSize*パラメーターは、新しい要素が必要なときに割り当てられるメモリの量の測定です。 ブロック サイズが大きくなると、メモリ割り当てルーチンの呼び出しは減りますが、使用するリソースは多くなります。

データを格納する前に[、CAtlMap::InitHashTable](#inithashtable)への呼び出しでハッシュ テーブルを初期化する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

## <a name="catlmapcatlmap"></a><a name="dtor"></a>カトルマップ::~カトルマップ

デストラクターです。

```
~CAtlMap() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。

## <a name="catlmapcpair-class"></a><a name="cpair_class"></a>CAtlMap::CPairクラス

キーと値の要素を含むクラス。

```
class CPair : public __POSITION
```

### <a name="remarks"></a>解説

このクラスは、マッピング構造体に格納されているキー要素と値要素にアクセスするために[、CAtlMap::GetNext](#getnext)と[CAtlMap::Lookup](#lookup)メソッドによって使用されます。

## <a name="catlmapdisableautorehash"></a><a name="disableautorehash"></a>カトルマップ::D可能なオートレハッシュ

`CAtlMap`オブジェクトの自動再ハッシュを無効にします。

```cpp
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>解説

自動再ハッシュが有効になっている場合 (デフォルトでは、ハッシュ テーブルのビン数は、読み込み値 (配列に格納されている要素の数に対するビンの数の比率) がマップの作成時に指定された最大値または最小値を超えると自動的に再計算されます。

`DisableAutoRehash`は、多数の要素が一度にマップに追加される場合に最も便利です。 制限を超えるたびに再ハッシュ処理をトリガする代わりに、要素を追加`DisableAutoRehash`し、最後に[CAtlMap::EnableAutoRehash](#enableautorehash)を呼び出す方が効率的です。

## <a name="catlmapenableautorehash"></a><a name="enableautorehash"></a>カトルマップ::オートレハッシュを有効にする

`CAtlMap`オブジェクトの自動再ハッシュを有効にします。

```cpp
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>解説

自動再ハッシュが有効になっている場合 (デフォルトでは、ハッシュ テーブルのビン数は、読み込み値 (配列に格納されている要素の数に対するビンの数の比率) がマップの作成時に指定された最大値または最小値を超えると自動的に再計算されます。

`EnableAutoRefresh`は[、CAtlMap::D可能なオートレハッシュ](#disableautorehash)への呼び出しの後に最も頻繁に使用されます。

## <a name="catlmapgetat"></a><a name="getat"></a>カトルマップ::ゲットアット

マップ内の指定した位置にある要素を返します。

```cpp
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置カウンター [:::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition).

*key*<br/>
マップのキーの種類を指定するテンプレート パラメーター。

*value*<br/>
マップの値の型を指定するテンプレート パラメーター。

### <a name="return-value"></a>戻り値

マップに格納されている現在のキー要素と値要素のペアへのポインターを返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは *、pos*が NULL に等しい場合、アサーション エラーが発生します。

## <a name="catlmapgetcount"></a><a name="getcount"></a>カトルマップ::ゲットカウント

マップ内の要素の数を取得します。

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>戻り値

マップ オブジェクト内の要素の数を返します。 単一の要素は、キーと値のペアです。

### <a name="example"></a>例

[CAtlMap::CAtlMap](#catlmap)の例を参照してください。

## <a name="catlmapgethashtablesize"></a><a name="gethashtablesize"></a>カトルマップ::ゲットハッシュテーブルサイズ

マップのハッシュ テーブル内のビンの数を調べます。

```
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>戻り値

ハッシュ テーブル内のビンの数を返します。 説明については[、CAtlMap::CAtlMap](#catlmap)を参照してください。

## <a name="catlmapgetkeyat"></a><a name="getkeyat"></a>カトルマップ::ゲットキーアット

オブジェクト内の指定した位置に格納されているキーを`CAtlMap`取得します。

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置カウンター [:::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>戻り値

オブジェクト内の指定された位置に格納されているキーへの参照を`CAtlMap`返します。

### <a name="example"></a>例

[CAtlMap::CAtlMap](#catlmap)の例を参照してください。

## <a name="catlmapgetnext"></a><a name="getnext"></a>カトルマップ::次に取得します

オブジェクトに格納されている次の要素ペアへのポインターを`CAtlMap`取得します。

```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置カウンター [:::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>戻り値

マップに格納されている次のキー要素と値要素のペアへのポインターを返します。 *pos*位置カウンターは、各呼び出しの後に更新されます。 取得した要素がマップ内の最後の要素である場合 *、pos*は NULL に設定されます。

## <a name="catlmapgetnextassoc"></a><a name="getnextassoc"></a>カトルマップ::ゲットネクストアソック

反復処理の次の要素を取得します。

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置カウンター [:::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition).

*key*<br/>
マップのキーの種類を指定するテンプレート パラメーター。

*value*<br/>
マップの値の型を指定するテンプレート パラメーター。

### <a name="remarks"></a>解説

*pos*位置カウンターは、各呼び出しの後に更新されます。 取得した要素がマップ内の最後の要素である場合 *、pos*は NULL に設定されます。

## <a name="catlmapgetnextkey"></a><a name="getnextkey"></a>カトルマップ::ゲットネクストキー

`CAtlMap`オブジェクトから次のキーを取得します。

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置カウンター [:::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>戻り値

マップ内の次のキーへの参照を返します。

### <a name="remarks"></a>解説

現在の位置カウンタ*pos*を更新します。マップにこれ以上エントリがない場合、位置カウンタは NULL に設定されます。

## <a name="catlmapgetnextvalue"></a><a name="getnextvalue"></a>カトルマップ::次に値を取得します。

`CAtlMap`オブジェクトから次の値を取得します。

```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置カウンター [:::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>戻り値

マップ内の次の値への参照を返します。

### <a name="remarks"></a>解説

現在の位置カウンタ*pos*を更新します。マップにこれ以上エントリがない場合、位置カウンタは NULL に設定されます。

### <a name="example"></a>例

[CAtlMap::CAtlMap](#catlmap)の例を参照してください。

## <a name="catlmapgetstartposition"></a><a name="getstartposition"></a>カトルマップ::ゲットスタートポジション

マップの反復処理を開始します。

```
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>戻り値

マップが空の場合は、開始位置を返すか NULL を返します。

### <a name="remarks"></a>解説

メソッドに渡すことができる POSITION 値を返してマップの反復処理を`GetNextAssoc`開始します。

> [!NOTE]
> 反復シーケンスは予測できません

### <a name="example"></a>例

[CAtlMap::CAtlMap](#catlmap)の例を参照してください。

## <a name="catlmapgetvalueat"></a><a name="getvalueat"></a>カトルマップ::ゲットバリューアット

`CAtlMap`オブジェクト内の指定した位置に格納されている値を取得します。

```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置カウンター [:::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>戻り値

オブジェクト内の指定された位置に格納されている値への参照を`CAtlMap`返します。

## <a name="catlmapinithashtable"></a><a name="inithashtable"></a>カトルマップ::イニトハッシュテーブル

ハッシュ テーブルを初期化します。

```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>パラメーター

*nビン*<br/>
ハッシュ テーブルで使用されるビンの数。 説明については[、CAtlMap::CAtlMap](#catlmap)を参照してください。

*バロックナウ*<br/>
メモリを割り当てるタイミングを示すフラグ。

### <a name="return-value"></a>戻り値

初期化が成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`InitHashTable`要素がハッシュ テーブルに格納される前に呼び出す必要があります。  このメソッドが明示的に呼び出されない場合、コンストラクターで指定されたビンカウントを使用して要素が最初に追加されると、自動的`CAtlMap`に呼び出されます。  それ以外の場合、マップは*nBins*パラメーターで指定された新しいビンカウントを使用して初期化されます。

*bAllocNow*パラメーターが false の場合、ハッシュ テーブルに必要なメモリは、最初に必要になるまで割り当てされません。 これは、マップが使用されるかどうかが不明な場合に役立ちます。

### <a name="example"></a>例

[CAtlMap::CAtlMap](#catlmap)の例を参照してください。

## <a name="catlmapisempty"></a><a name="isempty"></a>カトルマップ::IsEmpty

空のマップ オブジェクトをテストします。

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

マップが空の場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="catlmapkinargtype"></a><a name="kinargtype"></a>カトルマップ::キナルグタイプ

キーが入力引数として渡されるときに使用される型。

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="catlmapkoutargtype"></a><a name="koutargtype"></a>カトルマップ::コウトアルグタイプ

キーが出力引数として返されるときに使用される型。

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="catlmaplookup"></a><a name="lookup"></a>カトルマップ::ルックアップ

`CAtlMap`オブジェクト内のキーまたは値を検索します。

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索する要素を識別するキーを指定します。

*value*<br/>
検索された値を受け取る変数。

### <a name="return-value"></a>戻り値

メソッドの最初の形式は、キーが見つかった場合は true を返し、それ以外の場合は false を返します。 2 番目と 3 番目の形式は[、CAtlMap::GetNext](#getnext)などの呼び出しの位置として使用できる[CPair](#cpair_class)へのポインターを返します。

### <a name="remarks"></a>解説

`Lookup`ハッシュ アルゴリズムを使用して、指定された key パラメーターと正確に一致するキーを含むマップ要素をすばやく見つけることができます。

## <a name="catlmapoperator-"></a><a name="operator_at"></a>カトルマップ::演算子\[\]

新しい要素を置き換えるか、`CAtlMap`新しい要素を 追加します。

```
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
追加または置換する要素のキー。

### <a name="return-value"></a>戻り値

指定されたキーに関連付けられた値への参照を返します。

### <a name="example"></a>例

キーが既に存在する場合、要素は置き換えられます。 キーが存在しない場合は、新しい要素が追加されます。 [CAtlMap::CAtlMap](#catlmap)の例を参照してください。

## <a name="catlmaprehash"></a><a name="rehash"></a>カトルマップ::再ハッシュ

`CAtlMap`オブジェクトを再ハッシュします。

```cpp
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>パラメーター

*nビン*<br/>
ハッシュ テーブルで使用する新しいビン数。 説明については[、CAtlMap::CAtlMap](#catlmap)を参照してください。

### <a name="remarks"></a>解説

*nBins*が 0`CAtlMap`の場合、マップ内の要素数と最適な荷重設定に基づいて、妥当な数値を計算します。 通常、再ハッシュ処理は自動的に行われますが[、CAtlMap::DisableAutoRehash](#disableautorehash)が呼び出された場合、このメソッドは必要なサイズ変更を実行します。

## <a name="catlmapremoveall"></a><a name="removeall"></a>カトルマップ::すべて削除

`CAtlMap`オブジェクトからすべての要素を削除します。

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>解説

オブジェクトを`CAtlMap`クリアし、要素の格納に使用するメモリを解放します。

## <a name="catlmapremoveatpos"></a><a name="removeatpos"></a>カトルマップ::削除アトポス

`CAtlMap`オブジェクト内の指定した位置にある要素を削除します。

```cpp
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置カウンター [:::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition).

### <a name="remarks"></a>解説

指定した位置に格納されているキーと値のペアを削除します。 要素の格納に使用されるメモリが解放されます。 *pos*によって参照される POSITION は無効になり、マップ内の他のエレメントの位置は有効なままですが、必ずしも同じ順序を保持するとは限りません。

## <a name="catlmapremovekey"></a><a name="removekey"></a>キーの割り当て::キーの削除

キーを指定して、オブジェクトから要素を`CAtlMap`削除します。

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>パラメーター

*key*<br/>
削除する要素ペアに対応するキー。

### <a name="return-value"></a>戻り値

キーが見つかり、削除された場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="example"></a>例

[CAtlMap::CAtlMap](#catlmap)の例を参照してください。

## <a name="catlmapsetat"></a><a name="setat"></a>カトルマップ::セットアット

マップに要素ペアを挿入します。

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
オブジェクトに追加するキー値`CAtlMap`。

*value*<br/>
オブジェクトに追加する`CAtlMap`値。

### <a name="return-value"></a>戻り値

オブジェクト内のキー/値要素ペアの位置を`CAtlMap`返します。

### <a name="remarks"></a>解説

`SetAt`一致するキーが見つかった場合は、既存の要素を置き換えます。 キーが見つからない場合は、新しいキー/値ペアが作成されます。

## <a name="catlmapsetoptimalload"></a><a name="setoptimalload"></a>カトルマップ::設定最適なロード

`CAtlMap`オブジェクトの最適な負荷を設定します。

```cpp
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
最適な負荷比。

*フロしきい値*<br/>
負荷率の下限しきい値。

*フヒスレッショルド*<br/>
負荷率の上限しきい値。

*今すぐ*<br/>
ハッシュ テーブルを再計算する必要があるかどうかを示すフラグ。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトの最適な荷重値`CAtlMap`を再定義します。 さまざまなパラメーターの説明については[、CAtlMap::CAtlMap](#catlmap)を参照してください。 *bRehashNow*が true で、要素の数が最小値と最大値の範囲外である場合、ハッシュ テーブルが再計算されます。

## <a name="catlmapsetvalueat"></a><a name="setvalueat"></a>カトルマップ::セットバリューアット

`CAtlMap`オブジェクト内の指定した位置に格納されている値を変更します。

```cpp
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置カウンター [:::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition).

*value*<br/>
オブジェクトに追加する`CAtlMap`値。

### <a name="remarks"></a>解説

オブジェクト内の指定された位置に格納されている値要素`CAtlMap`を変更します。

## <a name="catlmapvinargtype"></a><a name="vinargtype"></a>カトルマップ::ヴィナーグタイプ

値が入力引数として渡されるときに使用される型。

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="catlmapvoutargtype"></a><a name="voutargtype"></a>カトルマップ::ヴートアルグタイプ

値が出力引数として渡されるときに使用される型。

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="catlmapcpairm_key"></a><a name="m_key"></a>カトルマップ::ペア:m_key

キー要素を格納するデータ メンバー。

```
const K m_key;
```

### <a name="parameters"></a>パラメーター

*K*<br/>
キー要素の型。

## <a name="catlmapcpairm_value"></a><a name="m_value"></a>カトルマップ::コペア::m_value

値要素を格納するデータ メンバー。

```
V  m_value;
```

### <a name="parameters"></a>パラメーター

*V*<br/>
値要素の型。

## <a name="see-also"></a>関連項目

[マーキーサンプル](../../overview/visual-cpp-samples.md)<br/>
[アップデートPV サンプル](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
