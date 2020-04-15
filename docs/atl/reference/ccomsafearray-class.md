---
title: CComSafeArray クラス
ms.date: 05/06/2019
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
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
ms.openlocfilehash: d1e72d364858ea31541d574ed77bdc8ccca7d748
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327399"
---
# <a name="ccomsafearray-class"></a>CComSafeArray クラス

このクラスは構造体のラッパー`SAFEARRAY`です。

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
|[CComセーフアレイ::Cコムセーフアレイ](#ccomsafearray)|コンストラクターです。|
|[::~CComセーフアレイ](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComセーフアレイ::追加](#add)|1 つ以上の`SAFEARRAY`要素または構造体を`CComSafeArray`に追加します。|
|[ココムセーフアレイ::アタッチ](#attach)|`CComSafeArray`オブジェクトに構造体を`SAFEARRAY`アタッチします。|
|[ココムセーフアレイ::コピーから](#copyfrom)|構造体の内容を`SAFEARRAY`オブジェクトに`CComSafeArray`コピーします。|
|[ココムセーフアレイ::コピート](#copyto)|`CComSafeArray` オブジェクトのコピーを作成します。|
|[オブジェクトは、](#create)|`CComSafeArray` オブジェクトを作成します。|
|[CComSafeArray::Destroy](#destroy)|`CComSafeArray` オブジェクトを破棄します。|
|[ココムセーフアレイ::Dエタッハ](#detach)|オブジェクトから`SAFEARRAY`a をデタッチします。 `CComSafeArray`|
|[コムセーフアレイ::ゲットアット](#getat)|1 次元配列から 1 つの要素を取得します。|
|[を見る](#getcount)|配列内の要素の数を返します。|
|[CComセーフアレイ::ゲットディメンション](#getdimensions)|配列内の次元数を返します。|
|[コムセーフアレイ::ゲットローワーバウンド](#getlowerbound)|配列の指定した次元の下限を返します。|
|[::ゲットセーフアレイプター](#getsafearrayptr)|`m_psa` データ メンバーのアドレスを返します。|
|[次のコマンドを使用します。](#gettype)|配列に格納されているデータの型を返します。|
|[ココムセーフアレイ::ゲットアッパーバウンド](#getupperbound)|配列の任意の次元の上限を返します。|
|[CComセーフアレイ::イシザブル](#issizable)|`CComSafeArray` オブジェクトのサイズを変更できるかどうかをテストします。|
|[ココムセーフアレイ:::マルチディムゲタット](#multidimgetat)|多次元配列から 1 つの要素を取得します。|
|[::マルチディムセットアット](#multidimsetat)|多次元配列の要素の値を設定します。|
|[CComセーフアレイ::サイズ変更](#resize)|`CComSafeArray` オブジェクトのサイズを変更します。|
|[コムセーフアレイ::セットアット](#setat)|1 次元配列の要素の値を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[ココムセーフアレイ::オペレーターLPセーフアレイ](#operator_lpsafearray)|`SAFEARRAY`ポインターに値をキャストします。|
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|配列から要素を取得します。|
|[次の操作を行います。](#operator_eq)|代入演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComセーフアレイ::m_psa](#m_psa)|このデータ メンバーは構造体のアドレス`SAFEARRAY`を保持します。|

## <a name="remarks"></a>解説

`CComSafeArray`[SAFEARRAY データ型](/windows/win32/api/oaidl/ns-oaidl-safearray)クラスのラッパーを提供し、バリアント型でサポートされているほとんどすべての型の単一および多次元配列を簡単に作成および管理できます。

`CComSafeArray` によりプロセス間での配列の受け渡しが単純化され、配列インデックスの値を上限と下限に照合することでセキュリティがさらに向上します。

`CComSafeArray` の下限は任意のユーザー定義値で開始できますが、C++ を通じてアクセスされる配列の下限は 0 にする必要があります。 Visual Basic などの他の言語では、別の境界値 (たとえば、-10 ～ 10) を使用できます。

[オブジェクトは、](#create) CComSafeArray::Create `CComSafeArray` を使用して作成し、 [CComSafeArray::Destroy](#destroy) を使用して削除します。

`CComSafeArray` には、VARIANT データ型の次のサブセットを格納できます。

|VARTYPE|説明|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|INT|
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

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsafe.h

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

## <a name="ccomsafearrayadd"></a><a name="add"></a>CComセーフアレイ::追加

1 つ以上の`SAFEARRAY`要素または構造体を`CComSafeArray`に追加します。

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>パラメーター

*psaSrc*<br/>
`SAFEARRAY` オブジェクトを指すポインターです。

*ウルカウント*<br/>
配列に追加するオブジェクトの数。

*Pt*<br/>
配列に追加する 1 つ以上のオブジェクトへのポインター。

*T*<br/>
配列に追加するオブジェクトへの参照。

*bコピー*<br/>
データのコピーを作成するかどうかを示します。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

新しいオブジェクトは、既存`SAFEARRAY`のオブジェクトの末尾に追加されます。 多次元`SAFEARRAY`オブジェクトへのオブジェクトの追加はサポートされていません。 オブジェクトの既存の配列を追加する場合、両方の配列に同じ型の要素が含まれている必要があります。

*bCopy*フラグは、BSTR 型またはバリアント型の要素が配列に追加されるときに考慮されます。 既定値の TRUE を指定すると、要素が配列に追加されるときに、データの新しいコピーが作成されます。

## <a name="ccomsafearrayattach"></a><a name="attach"></a>ココムセーフアレイ::アタッチ

`CComSafeArray`オブジェクトに構造体を`SAFEARRAY`アタッチします。

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>パラメーター

*psaSrc*<br/>
`SAFEARRAY`構造体へのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

オブジェクトに構造`SAFEARRAY`をアタッチして、既存`CComSafeArray`のメソッドを使用できるようにします。 `CComSafeArray`

## <a name="ccomsafearrayccomsafearray"></a><a name="ccomsafearray"></a>CComセーフアレイ::Cコムセーフアレイ

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

*バインド*<br/>
`SAFEARRAYBOUND` 構造。

*ウルカウント*<br/>
配列の要素数。

*lLバウンド*<br/>
下限値。つまり、配列の最初の要素のインデックスです。

*pバウンド*<br/>
`SAFEARRAYBOUND`構造体へのポインター。

*ユーディム*<br/>
配列内の次元の数。

*サスルク*<br/>
`SAFEARRAY`構造体または`CComSafeArray`オブジェクトへの参照。 どちらの場合も、コンストラクターはこの参照を使用して配列のコピーを作成するため、構築後に配列が参照されません。

*psaSrc*<br/>
`SAFEARRAY`構造体へのポインター。 コンストラクターはこのアドレスを使用して配列のコピーを作成するため、構築後に配列が参照されません。

### <a name="remarks"></a>解説

`CComSafeArray` オブジェクトを作成します。

## <a name="ccomsafearrayccomsafearray"></a><a name="dtor"></a>::~CComセーフアレイ

デストラクターです。

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="ccomsafearraycopyfrom"></a><a name="copyfrom"></a>ココムセーフアレイ::コピーから

構造体の内容を`SAFEARRAY`オブジェクトに`CComSafeArray`コピーします。

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>パラメーター

*を実行する*<br/>
コピーするへの`SAFEARRAY`ポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドは、の内容を`SAFEARRAY`現在`CComSafeArray`のオブジェクトにコピーします。 配列の既存の内容が置き換えられます。

## <a name="ccomsafearraycopyto"></a><a name="copyto"></a>ココムセーフアレイ::コピート

`CComSafeArray` オブジェクトのコピーを作成します。

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>パラメーター

*を実行する*<br/>
新しい`SAFEARRAY`を作成する場所へのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトの内容`CComSafeArray`を構造体に`SAFEARRAY`コピーします。

## <a name="ccomsafearraycreate"></a><a name="create"></a>CComセーフアレイ::作成

`CComSafeArray` を作成します。

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>パラメーター

*pバウンド*<br/>
`SAFEARRAYBOUND` オブジェクトを指すポインターです。

*ユーディム*<br/>
配列の次元数。

*ウルカウント*<br/>
配列の要素数。

*lLバウンド*<br/>
下限値。つまり、配列の最初の要素のインデックスです。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

オブジェクト`CComSafeArray`は、既存`SAFEARRAYBOUND`の構造と次元数から作成することも、配列内の要素数と下限を指定して作成することもできます。 C++ から配列にアクセスする場合、下限は 0 にする必要があります。 他の言語では、下限に他の値を使用できる場合があります (たとえば、Visual Basic では、-10 ~ 10 などの範囲の要素を持つ配列がサポートされています)。

## <a name="ccomsafearraydestroy"></a><a name="destroy"></a>コムセーフアレイ::Dエストロイ

`CComSafeArray` オブジェクトを破棄します。

```
HRESULT Destroy();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

既存`CComSafeArray`のオブジェクトと、そのオブジェクトに含まれるすべてのデータを破棄します。

## <a name="ccomsafearraydetach"></a><a name="detach"></a>ココムセーフアレイ::Dエタッハ

オブジェクトから`SAFEARRAY`a をデタッチします。 `CComSafeArray`

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>戻り値

オブジェクトへのポインターを`SAFEARRAY`返します。

### <a name="remarks"></a>解説

このメソッドは、オブジェクト`SAFEARRAY`からオブジェクトを`CComSafeArray`デタッチします。

## <a name="ccomsafearraygetat"></a><a name="getat"></a>コムセーフアレイ::ゲットアット

1 次元配列から 1 つの要素を取得します。

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>パラメーター

*Lindex*<br/>
返す配列内の値のインデックス番号。

### <a name="return-value"></a>戻り値

必要な配列要素への参照を返します。

## <a name="ccomsafearraygetcount"></a><a name="getcount"></a>を見る

配列内の要素の数を返します。

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>パラメーター

*ユーディム*<br/>
配列の次元。

### <a name="return-value"></a>戻り値

配列内の要素の数を返します。

### <a name="remarks"></a>解説

多次元配列と共に使用する場合、このメソッドは、特定の次元の要素の数のみを返します。

## <a name="ccomsafearraygetdimensions"></a><a name="getdimensions"></a>CComセーフアレイ::ゲットディメンション

配列内の次元数を返します。

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>戻り値

配列内の次元数を返します。

## <a name="ccomsafearraygetlowerbound"></a><a name="getlowerbound"></a>コムセーフアレイ::ゲットローワーバウンド

配列の指定した次元の下限を返します。

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>パラメーター

*ユーディム*<br/>
下限を取得する配列の次元。 省略した場合、デフォルトは 0 です。

### <a name="return-value"></a>戻り値

下限を返します。

### <a name="remarks"></a>解説

下限が 0 の場合、最初の要素が要素番号 0 の C に似た配列を示します。 たとえば、無効なディメンション引数などのエラーが発生した場合、このメソッドはエラーを`AtlThrow`説明する HRESULT を使用して呼び出します。

## <a name="ccomsafearraygetsafearrayptr"></a><a name="getsafearrayptr"></a>::ゲットセーフアレイプター

`m_psa` データ メンバーのアドレスを返します。

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>戻り値

データ メンバーへのポインター [m_psa](#m_psa)返します。

## <a name="ccomsafearraygettype"></a><a name="gettype"></a>次のコマンドを使用します。

配列に格納されているデータの型を返します。

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>戻り値

配列に格納されているデータの型を返します。

|VARTYPE|説明|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|INT|
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

## <a name="ccomsafearraygetupperbound"></a><a name="getupperbound"></a>ココムセーフアレイ::ゲットアッパーバウンド

配列の任意の次元の上限を返します。

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>パラメーター

*ユーディム*<br/>
上限を取得する配列の次元。 省略した場合、デフォルトは 0 です。

### <a name="return-value"></a>戻り値

上限を返します。 この値は、このディメンションの最大有効インデックスである包括的な値です。

### <a name="remarks"></a>解説

たとえば、無効なディメンション引数などのエラーが発生した場合、このメソッドはエラーを`AtlThrow`説明する HRESULT を使用して呼び出します。

## <a name="ccomsafearrayissizable"></a><a name="issizable"></a>CComセーフアレイ::イシザブル

`CComSafeArray` オブジェクトのサイズを変更できるかどうかをテストします。

```
bool IsSizable() const;
```

### <a name="return-value"></a>戻り値

サイズを変更できる`CComSafeArray`場合は TRUE を返し、サイズを変更できない場合は FALSE を返します。

## <a name="ccomsafearraym_psa"></a><a name="m_psa"></a>CComセーフアレイ::m_psa

アクセスされた構造体のアドレス`SAFEARRAY`を保持します。

```
LPSAFEARRAY m_psa;
```

## <a name="ccomsafearraymultidimgetat"></a><a name="multidimgetat"></a>ココムセーフアレイ:::マルチディムゲタット

多次元配列から 1 つの要素を取得します。

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>パラメーター

*アルインデックス*<br/>
配列内の各次元のインデックスのベクトルへのポインター。 最も左の (最も重要`alIndex[0]`な) 次元は です。

*T*<br/>
返されたデータへの参照。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="ccomsafearraymultidimsetat"></a><a name="multidimsetat"></a>::マルチディムセットアット

多次元配列の要素の値を設定します。

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>パラメーター

*アルインデックス*<br/>
配列内の各次元のインデックスのベクトルへのポインター。 最も右側の (最下位)`alIndex`次元は [0] です。

*T*<br/>
新しい要素の値を指定します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

これは[、CComSafeArray::SetAt](#setat)の多次元バージョンです。

## <a name="ccomsafearrayoperator-"></a><a name="operator_at"></a>コントロールアレイ::演算子\[\]

配列から要素を取得します。

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>パラメーター

*lインデックス、nインデックス*<br/>
配列内の必須要素のインデックス番号。

### <a name="return-value"></a>戻り値

適切な配列要素を返します。

### <a name="remarks"></a>解説

[CComSafeArray::GetAt](#getat)と同様の関数を実行しますが、この演算子は 1 次元配列でのみ動作します。

## <a name="ccomsafearrayoperator-"></a><a name="operator_eq"></a>次の操作を行います。

代入演算子。

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>パラメーター

*サスルク*<br/>
`CComSafeArray` オブジェクトへの参照です。

*psaSrc*<br/>
`SAFEARRAY` オブジェクトを指すポインターです。

### <a name="return-value"></a>戻り値

配列に格納されているデータの型を返します。

## <a name="ccomsafearrayoperator-lpsafearray"></a><a name="operator_lpsafearray"></a>ココムセーフアレイ::オペレーターLPセーフアレイ

`SAFEARRAY`ポインターに値をキャストします。

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>戻り値

`SAFEARRAY`ポインターに値をキャストします。

## <a name="ccomsafearrayresize"></a><a name="resize"></a>CComセーフアレイ::サイズ変更

`CComSafeArray` オブジェクトのサイズを変更します。

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>パラメーター

*pバウンド*<br/>
要素の`SAFEARRAYBOUND`数と配列の下限に関する情報を格納する構造体へのポインター。

*ウルカウント*<br/>
サイズ変更された配列内のオブジェクトの要求数。

*lLバウンド*<br/>
下限値です。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドは、右端の寸法のサイズを変更するだけです。 FALSE として返`IsResizable`される配列のサイズは変更されません。

## <a name="ccomsafearraysetat"></a><a name="setat"></a>コムセーフアレイ::セットアット

1 次元配列の要素の値を設定します。

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>パラメーター

*Lindex*<br/>
設定する配列要素のインデックス番号。

*T*<br/>
指定された要素の新しい値。

*bコピー*<br/>
データのコピーを作成するかどうかを示します。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

*bCopy*フラグは、BSTR 型またはバリアント型の要素が配列に追加されるときに考慮されます。 既定値の TRUE を指定すると、要素が配列に追加されるときに、データの新しいコピーが作成されます。

## <a name="see-also"></a>関連項目

[SAFEARRAY Data Type](/windows/win32/api/oaidl/ns-oaidl-safearray)<br/>
[オブジェクトは、](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
