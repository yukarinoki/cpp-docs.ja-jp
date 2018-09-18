---
title: CComSafeArray クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 411b8f58b38d2b35c1353d1ff446407026977d66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030145"
---
# <a name="ccomsafearray-class"></a>CComSafeArray クラス

このクラスは、のラッパー、`SAFEARRAY`構造体。

## <a name="syntax"></a>構文

```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
配列に格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComSafeArray::CComSafeArray](#ccomsafearray)|コンストラクターです。|
|[CComSafeArray:: ~ CComSafeArray](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Ccomsafearray::add](#add)|1 つまたは複数の要素を追加または`SAFEARRAY`構造体、`CComSafeArray`します。|
|[CComSafeArray::Attach](#attach)|アタッチを`SAFEARRAY`構造体を`CComSafeArray`オブジェクト。|
|[:Copyfrom](#copyfrom)|内容をコピー、`SAFEARRAY`に構造体、`CComSafeArray`オブジェクト。|
|[CComSafeArray::CopyTo](#copyto)|`CComSafeArray` オブジェクトのコピーを作成します。|
|[オブジェクトは、](#create)|`CComSafeArray` オブジェクトを作成します。|
|[CComSafeArray::Destroy](#destroy)|`CComSafeArray` オブジェクトを破棄します。|
|[Ccomsafearray::detach](#detach)|デタッチ、`SAFEARRAY`から、`CComSafeArray`オブジェクト。|
|[CComSafeArray::GetAt](#getat)|1 次元配列から 1 つの要素を取得します。|
|[CComSafeArray::GetCount](#getcount)|配列内の要素の数を返します。|
|[CComSafeArray::GetDimensions](#getdimensions)|配列内の次元数を返します。|
|[CComSafeArray::GetLowerBound](#getlowerbound)|配列の指定した次元の下限を返します。|
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|`m_psa` データ メンバーのアドレスを返します。|
|[CComSafeArray::GetType](#gettype)|配列に格納されているデータの型を返します。|
|[CComSafeArray::GetUpperBound](#getupperbound)|配列の任意の次元の上限を返します。|
|[CComSafeArray::IsSizable](#issizable)|`CComSafeArray` オブジェクトのサイズを変更できるかどうかをテストします。|
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|多次元配列から 1 つの要素を取得します。|
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|多次元配列の要素の値を設定します。|
|[CComSafeArray::Resize](#resize)|`CComSafeArray` オブジェクトのサイズを変更します。|
|[:Setat](#setat)|1 次元配列の要素の値を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|値にキャスト、`SAFEARRAY`ポインター。|
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|配列から要素を取得します。|
|[CComSafeArray::operator =](#operator_eq)|代入演算子。|  

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComSafeArray::m_psa](#m_psa)|このデータ メンバーのアドレスを保持する、`SAFEARRAY`構造体。|

## <a name="remarks"></a>Remarks

`CComSafeArray` ラッパーを提供、 [SAFEARRAY Data Type](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearray)クラスを簡単に作成し、ほぼすべてのバリアント サポート型の 1 次元または多次元の配列を管理できるようにします。

`CComSafeArray` によりプロセス間での配列の受け渡しが単純化され、配列インデックスの値を上限と下限に照合することでセキュリティがさらに向上します。

`CComSafeArray` の下限は任意のユーザー定義値で開始できますが、C++ を通じてアクセスされる配列の下限は 0 にする必要があります。 Visual Basic などの他の言語では、別の境界値 (たとえば、-10 ～ 10) を使用できます。

[オブジェクトは、](#create) CComSafeArray::Create `CComSafeArray` を使用して作成し、 [CComSafeArray::Destroy](#destroy) を使用して削除します。

`CComSafeArray` には、VARIANT データ型の次のサブセットを格納できます。

|VARTYPE|説明|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|10 進ポインター|
|VT_VARIANT|バリアント ポインター|
|VT_CY|Currency データ型|

## <a name="requirements"></a>要件

**ヘッダー:** atlsafe.h

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

##  <a name="add"></a>  Ccomsafearray::add

1 つまたは複数の要素を追加または`SAFEARRAY`構造体、`CComSafeArray`します。

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>パラメーター

*psaSrc*<br/>
ポインターを`SAFEARRAY`オブジェクト。

*ulCount*<br/>
配列に追加するオブジェクトの数。

*pT*<br/>
配列に追加する 1 つまたは複数のオブジェクトへのポインター。

*t*<br/>
配列に追加するオブジェクトへの参照。

*bCopy*<br/>
データのコピーを作成するかどうかを示します。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

新しいオブジェクトは、既存の末尾に追加されます`SAFEARRAY`オブジェクト。 多次元オブジェクトに追加する`SAFEARRAY`オブジェクトはサポートされていません。 既存のオブジェクトの配列を追加するときに、両方の配列は同じ型の要素を含める必要があります。

*BCopy*フラグは BSTR や VARIANT 型の要素が配列に追加されたときに考慮されます。 既定値は TRUE により、配列に要素が追加されたときに、データの新しいコピーが行われるようになります。

##  <a name="attach"></a>  CComSafeArray::Attach

アタッチを`SAFEARRAY`構造体を`CComSafeArray`オブジェクト。

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>パラメーター

*psaSrc*<br/>
ポインター、`SAFEARRAY`構造体。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

アタッチを`SAFEARRAY`構造体を`CComSafeArray`オブジェクト、既存の`CComSafeArray`使用可能なメソッドです。

##  <a name="ccomsafearray"></a>  CComSafeArray::CComSafeArray

コンストラクターです。

```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>パラメーター

*バインドされています。*<br/>
`SAFEARRAYBOUND` 構造。

*ulCount*<br/>
配列の要素数。

*lLBound*<br/>
下限値。つまり、配列の最初の要素のインデックス。

*pBound*<br/>
ポインター、`SAFEARRAYBOUND`構造体。

*uDims*<br/>
配列の次元の数。

*saSrc*<br/>
参照を`SAFEARRAY`構造または`CComSafeArray`オブジェクト。 いずれの場合も、コンス トラクターは作成した後、配列は参照しないように、配列のコピーを作成するのにこの参照を使用します。

*psaSrc*<br/>
ポインター、`SAFEARRAY`構造体。 コンス トラクターは、作成した後、配列は参照しないように、配列のコピーを作成するのにこのアドレスを使用します。

### <a name="remarks"></a>Remarks

`CComSafeArray` オブジェクトを作成します。

##  <a name="dtor"></a>  CComSafeArray:: ~ CComSafeArray

デストラクターです。

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>Remarks

割り当てられているすべてのリソースを解放します。

##  <a name="copyfrom"></a>  :Copyfrom

内容をコピー、`SAFEARRAY`に構造体、`CComSafeArray`オブジェクト。

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>パラメーター

*ppArray*<br/>
ポインター、`SAFEARRAY`にコピーします。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

このメソッドの内容をコピーする、`SAFEARRAY`を現在`CComSafeArray`オブジェクト。 配列の既存の内容は置き換えられます。

##  <a name="copyto"></a>  CComSafeArray::CopyTo

`CComSafeArray` オブジェクトのコピーを作成します。

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>パラメーター

*ppArray*<br/>
新しいを作成するための場所へのポインター`SAFEARRAY`します。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

このメソッドの内容をコピーする、`CComSafeArray`オブジェクトを`SAFEARRAY`構造体。

##  <a name="create"></a>  オブジェクトは、

`CComSafeArray` を作成します。

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>パラメーター

*pBound*<br/>
ポインターを`SAFEARRAYBOUND`オブジェクト。

*uDims*<br/>
配列の次元の数。

*ulCount*<br/>
配列の要素数。

*lLBound*<br/>
下限値。つまり、配列の最初の要素のインデックス。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

A`CComSafeArray`既存のオブジェクトを作成できる`SAFEARRAYBOUND`構造体、または、配列と下限の境界内の要素の数を指定することで、ディメンションの数。 配列は、Visual C からアクセスするのには、下限が 0 になります。 他の言語は、下限の境界 (たとえば、-10 ~ 10 などの範囲を持つ要素を Visual Basic のサポート配列) の他の値を許可する可能性があります。

##  <a name="destroy"></a>  CComSafeArray::Destroy

`CComSafeArray` オブジェクトを破棄します。

```
HRESULT Destroy();
```

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

既存の破棄`CComSafeArray`オブジェクトとすべてのデータが含まれています。

##  <a name="detach"></a>  Ccomsafearray::detach

デタッチ、`SAFEARRAY`から、`CComSafeArray`オブジェクト。

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>戻り値

ポインターを返します、`SAFEARRAY`オブジェクト。

### <a name="remarks"></a>Remarks

このメソッドのデタッチ、`SAFEARRAY`オブジェクトから、`CComSafeArray`オブジェクト。

##  <a name="getat"></a>  CComSafeArray::GetAt

1 次元配列から 1 つの要素を取得します。

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>パラメーター

*lIndex*<br/>
返される配列内の値のインデックス番号。

### <a name="return-value"></a>戻り値

必要な配列の要素への参照を返します。

##  <a name="getcount"></a>  CComSafeArray::GetCount

配列内の要素の数を返します。

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>パラメーター

*uDim*<br/>
配列の次元。

### <a name="return-value"></a>戻り値

配列内の要素の数を返します。

### <a name="remarks"></a>Remarks

多次元配列を併用すると、このメソッドは特定のディメンションのみでの要素の数を返します。

##  <a name="getdimensions"></a>  CComSafeArray::GetDimensions

配列内の次元数を返します。

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>戻り値

配列内の次元数を返します。

##  <a name="getlowerbound"></a>  CComSafeArray::GetLowerBound

配列の指定した次元の下限を返します。

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>パラメーター

*uDim*<br/>
下限の境界を取得する対象の配列の次元。 省略した場合、既定値は 0 です。

### <a name="return-value"></a>戻り値

下限の境界を返します。

### <a name="remarks"></a>Remarks

下限が 0 の場合の最初の要素が要素番号が 0 の C のような配列を示します。 エラーが発生した場合など、ディメンションの無効な引数では、このメソッドは`AtlThrow`HRESULT エラーを説明するとします。

##  <a name="getsafearrayptr"></a>  CComSafeArray::GetSafeArrayPtr

`m_psa` データ メンバーのアドレスを返します。

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>戻り値

ポインターを返します、 [CComSafeArray::m_psa](#m_psa)データ メンバー。

##  <a name="gettype"></a>  CComSafeArray::GetType

配列に格納されているデータの型を返します。

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>戻り値

次の種類のいずれかである可能性があると、配列に格納されたデータの型を返します。

|VARTYPE|説明|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|10 進ポインター|
|VT_VARIANT|バリアント ポインター|
|VT_CY|Currency データ型|

##  <a name="getupperbound"></a>  CComSafeArray::GetUpperBound

配列の任意の次元の上限を返します。

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>パラメーター

*uDim*<br/>
上限を取得する対象の配列の次元。 省略した場合、既定値は 0 です。

### <a name="return-value"></a>戻り値

上限の境界を返します。 この値は、このディメンションの有効な最大のインデックス。

### <a name="remarks"></a>Remarks

エラーが発生した場合など、ディメンションの無効な引数では、このメソッドは`AtlThrow`HRESULT エラーを説明するとします。

##  <a name="issizable"></a>  CComSafeArray::IsSizable

`CComSafeArray` オブジェクトのサイズを変更できるかどうかをテストします。

```
bool IsSizable() const;
```

### <a name="return-value"></a>戻り値

True の場合、`CComSafeArray`サイズを変更できる、FALSE できない場合。

##  <a name="m_psa"></a>  CComSafeArray::m_psa

アドレスを保持、`SAFEARRAY`構造体にアクセスします。

```
LPSAFEARRAY m_psa;
```

##  <a name="multidimgetat"></a>  CComSafeArray::MultiDimGetAt

多次元配列から 1 つの要素を取得します。

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>パラメーター

*alIndex*<br/>
配列内の各ディメンションのインデックスのベクターへのポインター。 (最上位) の一番左の次元は`alIndex[0]`します。

*t*<br/>
返されるデータへの参照。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

##  <a name="multidimsetat"></a>  CComSafeArray::MultiDimSetAt

多次元配列の要素の値を設定します。

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>パラメーター

*alIndex*<br/>
配列内の各ディメンションのインデックスのベクターへのポインター。 右端 (最下位) ディメンションが`alIndex`[0]。

*T*<br/>
新しい要素の値を指定します。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

これは、多次元のバージョンの[:setat](#setat)します。

##  <a name="operator_at"></a>  CComSafeArray::operator \[\]

配列から要素を取得します。

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>パラメーター

*lIndex、nIndex*<br/>
配列内の必要な要素のインデックス番号。

### <a name="return-value"></a>戻り値

適切な配列の要素を返します。

### <a name="remarks"></a>Remarks

同様の機能を実行します[CComSafeArray::GetAt](#getat)、この演算子は、1 次元配列でのみ動作します。

##  <a name="operator_eq"></a>  CComSafeArray::operator =

代入演算子。

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>パラメーター

*saSrc*<br/>
`CComSafeArray` オブジェクトへの参照。

*psaSrc*<br/>
ポインターを`SAFEARRAY`オブジェクト。

### <a name="return-value"></a>戻り値

配列に格納されているデータの型を返します。

##  <a name="operator_lpsafearray"></a>  CComSafeArray::operator LPSAFEARRAY

値にキャスト、`SAFEARRAY`ポインター。

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>戻り値

値にキャスト、`SAFEARRAY`ポインター。

##  <a name="resize"></a>  CComSafeArray::Resize

`CComSafeArray` オブジェクトのサイズを変更します。

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>パラメーター

*pBound*<br/>
ポインターを`SAFEARRAYBOUND`要素の数と、配列の下限の境界に情報を含む構造体。

*ulCount*<br/>
要求されたサイズを変更した配列内のオブジェクト数。

*lLBound*<br/>
下限値です。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

このメソッドは、右端の次元のみ変更します。 返す配列サイズがない`IsResizable`false に設定します。

##  <a name="setat"></a>  :Setat

1 次元配列の要素の値を設定します。

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>パラメーター

*lIndex*<br/>
設定する配列要素のインデックス番号。

*t*<br/>
指定した要素の新しい値。

*bCopy*<br/>
データのコピーを作成するかどうかを示します。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

*BCopy*フラグは BSTR や VARIANT 型の要素が配列に追加されたときに考慮されます。 既定値は TRUE により、配列に要素が追加されたときに、データの新しいコピーが行われるようになります。

## <a name="see-also"></a>関連項目

[SAFEARRAY Data Type](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearray)<br/>
[オブジェクトは、](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
