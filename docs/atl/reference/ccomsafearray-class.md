---
description: '詳細情報: CComSafeArray クラス'
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
ms.openlocfilehash: e25719ffb9817595a1c1cc108a9d9ffc91459fe1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142310"
---
# <a name="ccomsafearray-class"></a>CComSafeArray クラス

このクラスは、構造体のラッパーです `SAFEARRAY` 。

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
|[CComSafeArray:: CComSafeArray](#ccomsafearray)|コンストラクターです。|
|[CComSafeArray:: ~ CComSafeArray](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComSafeArray:: Add](#add)|1つ以上の要素 (または `SAFEARRAY` 構造体) をに追加し `CComSafeArray` ます。|
|[CComSafeArray:: Attach](#attach)|`SAFEARRAY`構造体をオブジェクトにアタッチ `CComSafeArray` します。|
|[CComSafeArray:: CopyFrom](#copyfrom)|構造体の内容を `SAFEARRAY` オブジェクトにコピーし `CComSafeArray` ます。|
|[CComSafeArray:: CopyTo](#copyto)|`CComSafeArray` オブジェクトのコピーを作成します。|
|[オブジェクトは、](#create)|`CComSafeArray` オブジェクトを作成します。|
|[CComSafeArray::Destroy](#destroy)|`CComSafeArray` オブジェクトを破棄します。|
|[CComSafeArray::D etach](#detach)|`SAFEARRAY`オブジェクトからをデタッチ `CComSafeArray` します。|
|[CComSafeArray:: GetAt](#getat)|1 次元配列から 1 つの要素を取得します。|
|[CComSafeArray:: GetCount](#getcount)|配列内の要素の数を返します。|
|[CComSafeArray:: GetDimensions](#getdimensions)|配列内の次元数を返します。|
|[CComSafeArray:: Get下限バインド](#getlowerbound)|配列の指定した次元の下限を返します。|
|[CComSafeArray:: Getsaf (Rayptr)](#getsafearrayptr)|`m_psa` データ メンバーのアドレスを返します。|
|[CComSafeArray:: GetType](#gettype)|配列に格納されているデータの型を返します。|
|[CComSafeArray:: System.array.getupperbound](#getupperbound)|配列の任意の次元の上限を返します。|
|[CComSafeArray:: IsSizable](#issizable)|`CComSafeArray` オブジェクトのサイズを変更できるかどうかをテストします。|
|[CComSafeArray:: MultiDimGetAt](#multidimgetat)|多次元配列から 1 つの要素を取得します。|
|[CComSafeArray:: MultiDimSetAt](#multidimsetat)|多次元配列の要素の値を設定します。|
|[CComSafeArray:: Resize](#resize)|`CComSafeArray` オブジェクトのサイズを変更します。|
|[CComSafeArray:: SetAt](#setat)|1 次元配列の要素の値を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CComSafeArray:: operator LPSAFEARRAY](#operator_lpsafearray)|値をポインターにキャスト `SAFEARRAY` します。|
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|配列から要素を取得します。|
|[CComSafeArray:: operator =](#operator_eq)|代入演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComSafeArray:: m_psa](#m_psa)|このデータメンバーは、構造体のアドレスを保持 `SAFEARRAY` します。|

## <a name="remarks"></a>解説

`CComSafeArray`[SAFEARRAY データ型](/windows/win32/api/oaidl/ns-oaidl-safearray)クラスのラッパーを提供し、ほとんどすべてのバリアントサポート型の1次元配列と多次元配列を簡単に作成および管理できるようにします。

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

## <a name="requirements"></a>要件

**ヘッダー:** atlsafe.h

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

## <a name="ccomsafearrayadd"></a><a name="add"></a> CComSafeArray:: Add

1つ以上の要素 (または `SAFEARRAY` 構造体) をに追加し `CComSafeArray` ます。

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>パラメーター

*psaSrc*<br/>
`SAFEARRAY` オブジェクトを指すポインターです。

*ulCount*<br/>
配列に追加するオブジェクトの数。

*未満*<br/>
配列に追加する1つ以上のオブジェクトへのポインター。

*t*<br/>
配列に追加するオブジェクトへの参照。

*bCopy*<br/>
データのコピーを作成する必要があるかどうかを示します。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

新しいオブジェクトは、既存のオブジェクトの末尾に追加され `SAFEARRAY` ます。 多次元オブジェクトへのオブジェクトの追加 `SAFEARRAY` はサポートされていません。 オブジェクトの既存の配列を追加する場合、両方の配列に同じ型の要素が含まれている必要があります。

*Bcopy* フラグは、BSTR 型または VARIANT 型の要素が配列に追加されるときに考慮されます。 既定値の TRUE は、要素が配列に追加されたときに、データの新しいコピーが作成されることを保証します。

## <a name="ccomsafearrayattach"></a><a name="attach"></a> CComSafeArray:: Attach

`SAFEARRAY`構造体をオブジェクトにアタッチ `CComSafeArray` します。

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>パラメーター

*psaSrc*<br/>
構造体へのポインター `SAFEARRAY` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

`SAFEARRAY`構造体をオブジェクトにアタッチし `CComSafeArray` 、既存の `CComSafeArray` メソッドを使用できるようにします。

## <a name="ccomsafearrayccomsafearray"></a><a name="ccomsafearray"></a> CComSafeArray:: CComSafeArray

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

*バインディング*<br/>
`SAFEARRAYBOUND` 構造。

*ulCount*<br/>
配列の要素数。

*lLBound*<br/>
下限値。つまり、配列内の最初の要素のインデックスです。

*pBound*<br/>
構造体へのポインター `SAFEARRAYBOUND` 。

*uDims*<br/>
配列内の次元の数。

*saSrc*<br/>
`SAFEARRAY`構造体またはオブジェクトへの参照 `CComSafeArray` 。 どちらの場合も、コンストラクターはこの参照を使用して配列のコピーを作成するため、配列は構築後に参照されません。

*psaSrc*<br/>
構造体へのポインター `SAFEARRAY` 。 コンストラクターは、このアドレスを使用して配列のコピーを作成するため、配列は構築後に参照されません。

### <a name="remarks"></a>解説

`CComSafeArray` オブジェクトを作成します。

## <a name="ccomsafearrayccomsafearray"></a><a name="dtor"></a> CComSafeArray:: ~ CComSafeArray

デストラクターです。

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="ccomsafearraycopyfrom"></a><a name="copyfrom"></a> CComSafeArray:: CopyFrom

構造体の内容を `SAFEARRAY` オブジェクトにコピーし `CComSafeArray` ます。

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>パラメーター

*ppArray*<br/>
コピーするへのポインター `SAFEARRAY` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このメソッドは、の内容を `SAFEARRAY` 現在のオブジェクトにコピーし `CComSafeArray` ます。 配列の既存の内容が置き換えられます。

## <a name="ccomsafearraycopyto"></a><a name="copyto"></a> CComSafeArray:: CopyTo

`CComSafeArray` オブジェクトのコピーを作成します。

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>パラメーター

*ppArray*<br/>
新しいを作成する場所へのポインター `SAFEARRAY` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトの内容を `CComSafeArray` 構造体にコピーし `SAFEARRAY` ます。

## <a name="ccomsafearraycreate"></a><a name="create"></a> CComSafeArray:: Create

`CComSafeArray` を作成します。

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>パラメーター

*pBound*<br/>
`SAFEARRAYBOUND` オブジェクトを指すポインターです。

*uDims*<br/>
配列の次元数。

*ulCount*<br/>
配列の要素数。

*lLBound*<br/>
下限値。つまり、配列内の最初の要素のインデックスです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

オブジェクトは、 `CComSafeArray` 既存の `SAFEARRAYBOUND` 構造と次元の数から作成することも、配列内の要素の数と下限を指定することによって作成することもできます。 配列に C++ からアクセスする場合、下限は0にする必要があります。 他の言語では、下限に対して他の値が許可される場合があります (たとえば、Visual Basic では、-10 ~ 10 などの範囲の要素を持つ配列がサポートされます)。

## <a name="ccomsafearraydestroy"></a><a name="destroy"></a> CComSafeArray::D estroy

`CComSafeArray` オブジェクトを破棄します。

```
HRESULT Destroy();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

既存 `CComSafeArray` のオブジェクトとそれに含まれるすべてのデータを破棄します。

## <a name="ccomsafearraydetach"></a><a name="detach"></a> CComSafeArray::D etach

`SAFEARRAY`オブジェクトからをデタッチ `CComSafeArray` します。

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>戻り値

オブジェクトへのポインターを返し `SAFEARRAY` ます。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトを `SAFEARRAY` オブジェクトからデタッチし `CComSafeArray` ます。

## <a name="ccomsafearraygetat"></a><a name="getat"></a> CComSafeArray:: GetAt

1 次元配列から 1 つの要素を取得します。

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>パラメーター

*lIndex*<br/>
返される配列内の値のインデックス番号。

### <a name="return-value"></a>戻り値

必須の配列要素への参照を返します。

## <a name="ccomsafearraygetcount"></a><a name="getcount"></a> CComSafeArray:: GetCount

配列内の要素の数を返します。

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>パラメーター

*uDim*<br/>
配列の次元。

### <a name="return-value"></a>戻り値

配列内の要素の数を返します。

### <a name="remarks"></a>解説

多次元配列と共に使用する場合、このメソッドは特定の次元の要素の数のみを返します。

## <a name="ccomsafearraygetdimensions"></a><a name="getdimensions"></a> CComSafeArray:: GetDimensions

配列内の次元数を返します。

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>戻り値

配列内の次元数を返します。

## <a name="ccomsafearraygetlowerbound"></a><a name="getlowerbound"></a> CComSafeArray:: Get下限バインド

配列の指定した次元の下限を返します。

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>パラメーター

*uDim*<br/>
下限を取得する対象の配列の次元。 省略した場合、既定値は0です。

### <a name="return-value"></a>戻り値

下限を返します。

### <a name="remarks"></a>解説

下限が0の場合、これは、最初の要素が要素番号0である C に似た配列を示します。 たとえば、無効なディメンション引数などのエラーが発生した場合、このメソッドは、 `AtlThrow` エラーを説明する HRESULT を使用してを呼び出します。

## <a name="ccomsafearraygetsafearrayptr"></a><a name="getsafearrayptr"></a> CComSafeArray:: Getsaf (Rayptr)

`m_psa` データ メンバーのアドレスを返します。

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>戻り値

[CComSafeArray:: m_psa](#m_psa)データメンバーへのポインターを返します。

## <a name="ccomsafearraygettype"></a><a name="gettype"></a> CComSafeArray:: GetType

配列に格納されているデータの型を返します。

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>戻り値

配列に格納されているデータの型を返します。次のいずれかの型になります。

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

## <a name="ccomsafearraygetupperbound"></a><a name="getupperbound"></a> CComSafeArray:: System.array.getupperbound

配列の任意の次元の上限を返します。

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>パラメーター

*uDim*<br/>
上限を取得する対象の配列の次元。 省略した場合、既定値は0です。

### <a name="return-value"></a>戻り値

上限を返します。 この値は、このディメンションの有効な最大インデックス数を含みます。

### <a name="remarks"></a>解説

たとえば、無効なディメンション引数などのエラーが発生した場合、このメソッドは、 `AtlThrow` エラーを説明する HRESULT を使用してを呼び出します。

## <a name="ccomsafearrayissizable"></a><a name="issizable"></a> CComSafeArray:: IsSizable

`CComSafeArray` オブジェクトのサイズを変更できるかどうかをテストします。

```
bool IsSizable() const;
```

### <a name="return-value"></a>戻り値

の `CComSafeArray` サイズを変更できる場合は TRUE、それができない場合は FALSE を返します。

## <a name="ccomsafearraym_psa"></a><a name="m_psa"></a> CComSafeArray:: m_psa

アクセスされた構造体のアドレスを保持 `SAFEARRAY` します。

```
LPSAFEARRAY m_psa;
```

## <a name="ccomsafearraymultidimgetat"></a><a name="multidimgetat"></a> CComSafeArray:: MultiDimGetAt

多次元配列から 1 つの要素を取得します。

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>パラメーター

*alIndex*<br/>
配列内の各次元のインデックスのベクターへのポインター。 左端 (最上位) のディメンションは `alIndex[0]` です。

*t*<br/>
返されたデータへの参照。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

## <a name="ccomsafearraymultidimsetat"></a><a name="multidimsetat"></a> CComSafeArray:: MultiDimSetAt

多次元配列の要素の値を設定します。

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>パラメーター

*alIndex*<br/>
配列内の各次元のインデックスのベクターへのポインター。 右端 (最下位) のディメンションは `alIndex` [0] です。

*T*<br/>
新しい要素の値を指定します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

これは、 [CComSafeArray:: SetAt](#setat)の多次元バージョンです。

## <a name="ccomsafearrayoperator-"></a><a name="operator_at"></a> CComSafeArray:: operator \[\]

配列から要素を取得します。

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>パラメーター

*lIndex, nIndex*<br/>
配列内の必須要素のインデックス番号。

### <a name="return-value"></a>戻り値

適切な配列要素を返します。

### <a name="remarks"></a>解説

[CComSafeArray:: GetAt](#getat)と同様の関数を実行しますが、この演算子は1次元配列でのみ機能します。

## <a name="ccomsafearrayoperator-"></a><a name="operator_eq"></a> CComSafeArray:: operator =

代入演算子。

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>パラメーター

*saSrc*<br/>
`CComSafeArray` オブジェクトへの参照です。

*psaSrc*<br/>
`SAFEARRAY` オブジェクトを指すポインターです。

### <a name="return-value"></a>戻り値

配列に格納されているデータの型を返します。

## <a name="ccomsafearrayoperator-lpsafearray"></a><a name="operator_lpsafearray"></a> CComSafeArray:: operator LPSAFEARRAY

値をポインターにキャスト `SAFEARRAY` します。

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>戻り値

値をポインターにキャスト `SAFEARRAY` します。

## <a name="ccomsafearrayresize"></a><a name="resize"></a> CComSafeArray:: Resize

`CComSafeArray` オブジェクトのサイズを変更します。

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>パラメーター

*pBound*<br/>
`SAFEARRAYBOUND`配列の要素数と下限値に関する情報を格納している構造体へのポインター。

*ulCount*<br/>
サイズを変更した配列内の、要求されたオブジェクトの数。

*lLBound*<br/>
下限値です。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このメソッドは、右端の次元のサイズのみを変更します。 FALSE として返される配列のサイズは変更されません `IsResizable` 。

## <a name="ccomsafearraysetat"></a><a name="setat"></a> CComSafeArray:: SetAt

1 次元配列の要素の値を設定します。

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>パラメーター

*lIndex*<br/>
設定する配列要素のインデックス番号。

*t*<br/>
指定された要素の新しい値。

*bCopy*<br/>
データのコピーを作成する必要があるかどうかを示します。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

*Bcopy* フラグは、BSTR 型または VARIANT 型の要素が配列に追加されるときに考慮されます。 既定値の TRUE は、要素が配列に追加されたときに、データの新しいコピーが作成されることを保証します。

## <a name="see-also"></a>関連項目

[SAFEARRAY Data Type](/windows/win32/api/oaidl/ns-oaidl-safearray)<br/>
[オブジェクトは、](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
