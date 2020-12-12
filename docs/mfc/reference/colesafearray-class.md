---
description: '詳細情報: COleSafeArray クラス'
title: COleSafeArray クラス
ms.date: 08/29/2019
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
ms.openlocfilehash: 6c33f58f71167c492883a25b05fce6bb8fb09916
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226702"
---
# <a name="colesafearray-class"></a>COleSafeArray クラス

任意の型および次元の配列を扱うクラスです。

## <a name="syntax"></a>構文

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleSafeArray:: COleSafeArray](#colesafearray)|`COleSafeArray` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleSafeArray:: AccessData](#accessdata)|配列データへのポインターを取得します。|
|[COleSafeArray:: AllocData](#allocdata)|配列にメモリを割り当てます。|
|[COleSafeArray:: AllocDescriptor](#allocdescriptor)|セーフ配列記述子にメモリを割り当てます。|
|[COleSafeArray:: Attach](#attach)|`VARIANT`オブジェクトに対する既存の配列の制御を提供 `COleSafeArray` します。|
|[COleSafeArray:: Clear](#clear)|基になるのすべてのデータを解放 `VARIANT` します。|
|[COleSafeArray:: Copy](#copy)|既存の配列のコピーを作成します。|
|[COleSafeArray:: Create](#create)|セーフ配列を作成します。|
|[COleSafeArray:: CreateOneDim](#createonedim)|1次元のオブジェクトを作成し `COleSafeArray` ます。|
|[COleSafeArray::D estroy](#destroy)|既存の配列を破棄します。|
|[COleSafeArray::D estroyData](#destroydata)|安全な配列のデータを破棄します。|
|[COleSafeArray::D estroyDescriptor](#destroydescriptor)|セーフ配列の記述子を破棄します。|
|[COleSafeArray::D etach](#detach)|オブジェクトから VARIANT 配列をデタッチし `COleSafeArray` ます (データが解放されないようにするため)。|
|[COleSafeArray:: GetByteArray](#getbytearray)|セーフ配列の内容を [CByteArray](../../mfc/reference/cbytearray-class.md)にコピーします。|
|[COleSafeArray:: GetDim](#getdim)|配列内の次元数を返します。|
|[COleSafeArray:: GetElement](#getelement)|セーフ配列の1つの要素を取得します。|
|[COleSafeArray:: GetElemSize](#getelemsize)|セーフ配列内の1つの要素のサイズ (バイト単位) を返します。|
|[COleSafeArray:: GetLBound](#getlbound)|セーフ配列の任意の次元の下限を返します。|
|[COleSafeArray:: GetOneDimSize](#getonedimsize)|1次元のオブジェクト内の要素の数を返し `COleSafeArray` ます。|
|[COleSafeArray:: GetUBound](#getubound)|セーフ配列の任意の次元の上限を返します。|
|[COleSafeArray:: Lock](#lock)|配列のロックカウントをインクリメントし、配列データへのポインターを配列記述子に配置します。|
|[COleSafeArray::P trOfIndex](#ptrofindex)|インデックス付き要素へのポインターを返します。|
|[COleSafeArray::P utElement](#putelement)|1 つの要素を配列に割り当てます。|
|[COleSafeArray:: Redim](#redim)|セーフ配列の最上位 (右端) の下限を変更します。|
|[COleSafeArray:: ResizeOneDim](#resizeonedim)|1次元のオブジェクト内の要素の数を変更 `COleSafeArray` します。|
|[COleSafeArray:: UnaccessData](#unaccessdata)|配列のロックカウントをデクリメントし、によって取得されたポインターを無効にし `AccessData` ます。|
|[COleSafeArray:: Unlock](#unlock)|配列のロックカウントをデクリメントして、解放またはサイズ変更できるようにします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[COleSafeArray:: operator LPCVARIANT](#operator_lpcvariant)|オブジェクトの基になる構造にアクセスし `VARIANT` `COleSafeArray` ます。|
|[COleSafeArray:: operator LPVARIANT](#operator_lpvariant)|オブジェクトの基になる構造にアクセスし `VARIANT` `COleSafeArray` ます。|
|[COleSafeArray:: operator =](#operator_eq)|値を `COleSafeArray` オブジェクト (、、 `SAFEARRAY` `VARIANT` `COleVariant` 、または `COleSafeArray` 配列) にコピーします。|
|[COleSafeArray:: operator = =](#operator_eq_eq)|2つの variant 配列 ( `SAFEARRAY` 、、 `VARIANT` `COleVariant` 、または `COleSafeArray` 配列) を比較します。|
|[COleSafeArray:: operator &lt;&lt;](#operator_lt_lt)|オブジェクトの内容を `COleSafeArray` ダンプコンテキストに出力します。|

## <a name="remarks"></a>解説

`COleSafeArray` OLE `VARIANT` 構造体から派生します。 OLE `SAFEARRAY` メンバー関数は、を介して使用でき `COleSafeArray` ます。また、1次元のバイト配列専用に設計された一連のメンバー関数も使用できます。

## <a name="inheritance-hierarchy"></a>継承階層

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>要件

**ヘッダー :** afxdisp.h

## <a name="colesafearrayaccessdata"></a><a name="accessdata"></a> COleSafeArray:: AccessData

配列データへのポインターを取得します。

```cpp
void AccessData(void** ppvData);
```

### <a name="parameters"></a>パラメーター

*ppvData*<br/>
配列データへのポインターへのポインター。

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

## <a name="colesafearrayallocdata"></a><a name="allocdata"></a> COleSafeArray:: AllocData

セーフ配列にメモリを割り当てます。

```cpp
void AllocData();
```

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="colesafearrayallocdescriptor"></a><a name="allocdescriptor"></a> COleSafeArray:: AllocDescriptor

セーフ配列の記述子にメモリを割り当てます。

```cpp
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>パラメーター

*dwDims*<br/>
セーフ配列内の次元の数。

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="colesafearrayattach"></a><a name="attach"></a> COleSafeArray:: Attach

既存の配列内のデータの制御 `VARIANT` をオブジェクトに提供し `COleSafeArray` ます。

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>パラメーター

*varSrc*<br/>
`VARIANT` オブジェクト。 *Varsrc* パラメーターには、VARTYPE [VT_ARRAY](/windows/win32/api/wtypes/ne-wtypes-varenum)が必要です。

### <a name="remarks"></a>解説

ソース `VARIANT` の種類が VT_EMPTY に設定されています。 この関数は、現在の配列データ (存在する場合) をクリアします。

### <a name="example"></a>例

  [COleSafeArray:: AccessData](#accessdata)の例を参照してください。

## <a name="colesafearrayclear"></a><a name="clear"></a> COleSafeArray:: Clear

セーフ配列をクリアします。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

関数は、オブジェクトのを VT_EMPTY に設定することによって、セーフ配列をクリアし `VARTYPE` ます。 現在の内容が解放され、配列が解放されます。

## <a name="colesafearraycolesafearray"></a><a name="colesafearray"></a> COleSafeArray:: COleSafeArray

`COleSafeArray` オブジェクトを構築します。

```
COleSafeArray();

COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);

COleSafeArray(const COleSafeArray& saSrc);
COleSafeArray(const VARIANT& varSrc);
COleSafeArray(LPCVARIANT pSrc);
COleSafeArray(const COleVariant& varSrc);
```

### <a name="parameters"></a>パラメーター

*saSrc*<br/>
新しいオブジェクト `COleSafeArray` `SAFEARRAY` にコピーされる既存のオブジェクトまたは `COleSafeArray` 。

*vtSrc*<br/>
新しいオブジェクトの VARTYPE `COleSafeArray` 。

*psaSrc*<br/>
`SAFEARRAY`新しいオブジェクトにコピーされるへのポインター `COleSafeArray` 。

*varSrc*<br/>
`VARIANT` `COleVariant` 新しいオブジェクトにコピーされる既存のまたはオブジェクト `COleSafeArray` 。

*.Psrc*<br/>
`VARIANT`新しいオブジェクトにコピーされるオブジェクトへのポインター `COleSafeArray` 。

### <a name="remarks"></a>解説

これらのコンストラクターはすべて、新しい `COleSafeArray` オブジェクトを作成します。 パラメーターがない場合は、空の `COleSafeArray` オブジェクトが作成されます (VT_EMPTY)。 が暗黙的に認識されている `COleSafeArray` 別の配列 (、、または) からがコピーされた場合 `COleSafeArray` `COleVariant` `VARIANT` 、ソース配列の vartype は保持されるため、指定する必要はありません。 が認識され `COleSafeArray` ていない別の配列 () からコピーされた場合は、 `SAFEARRAY` *vtsrc* パラメーターで vartype を指定する必要があります。

エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="colesafearraycopy"></a><a name="copy"></a> COleSafeArray:: Copy

既存のセーフ配列のコピーを作成します。

```cpp
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>パラメーター

*ppsa*<br/>
新しい配列記述子を返す位置へのポインター。

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="colesafearraycreate"></a><a name="create"></a> COleSafeArray:: Create

配列のデータを割り当てて初期化します。

```cpp
void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    DWORD* rgElements);

void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    SAFEARRAYBOUND* rgsabounds);
```

### <a name="parameters"></a>パラメーター

*vtSrc*<br/>
配列の基本型 (つまり、配列の各要素の VARTYPE)。 VARTYPE は、バリアント型のサブセットに制限されます。 VT_ARRAY も VT_BYREF フラグも設定できません。 VT_EMPTY と VT_NULL は、配列の有効な基本型ではありません。 それ以外の型はすべて有効です。

*dwDims*<br/>
配列内の次元の数。 これは、 [Redim](#redim)で配列を作成した後に変更できます。

*rgElements*<br/>
配列内の各次元の要素数の配列へのポインター。

*rgsabounds*<br/>
配列に割り当てる境界のベクター (次元ごとに1つ) へのポインター。

### <a name="remarks"></a>解説

この関数は、必要に応じて現在の配列データをクリアします。 エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraycreateonedim"></a><a name="createonedim"></a> COleSafeArray:: CreateOneDim

新しい1次元オブジェクトを作成し `COleSafeArray` ます。

```cpp
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>パラメーター

*vtSrc*<br/>
配列の基本型 (つまり、配列の各要素の VARTYPE)。

*dwElements*<br/>
配列内の要素の数。 これは、 [ResizeOneDim](#resizeonedim)を使用して配列を作成した後に変更できます。

*pvSrcData*<br/>
配列にコピーするデータへのポインター。

*nLBound*<br/>
配列の下限。

### <a name="remarks"></a>解説

関数は、配列のデータを割り当てて初期化し、ポインターの *Pvsrcdata* が NULL でない場合に、指定されたデータをコピーします。

エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

## <a name="colesafearraydestroy"></a><a name="destroy"></a> COleSafeArray::D estroy

既存の配列記述子と配列内のすべてのデータを破棄します。

```cpp
void Destroy();
```

### <a name="remarks"></a>解説

オブジェクトが配列に格納されている場合は、各オブジェクトが解放されます。 エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="colesafearraydestroydata"></a><a name="destroydata"></a> COleSafeArray::D estroyData

セーフ配列内のすべてのデータを破棄します。

```cpp
void DestroyData();
```

### <a name="remarks"></a>解説

オブジェクトが配列に格納されている場合は、各オブジェクトが解放されます。 エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="colesafearraydestroydescriptor"></a><a name="destroydescriptor"></a> COleSafeArray::D estroyDescriptor

セーフ配列の記述子を破棄します。

```cpp
void DestroyDescriptor();
```

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="colesafearraydetach"></a><a name="detach"></a> COleSafeArray::D etach

`VARIANT`オブジェクトからデータをデタッチし `COleSafeArray` ます。

```
VARIANT Detach();
```

### <a name="return-value"></a>戻り値

オブジェクトの基 `VARIANT` になる値 `COleSafeArray` 。

### <a name="remarks"></a>解説

関数は、オブジェクトの VARTYPE を VT_EMPTY に設定することによって、データをセーフ配列にデタッチします。 Windows 関数 [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear)を呼び出すことによって、配列を解放するのは呼び出し元の責任です。

エラーが発生した場合、関数は [COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

  [COleSafeArray::P utElement](#putelement)の例を参照してください。

## <a name="colesafearraygetbytearray"></a><a name="getbytearray"></a> COleSafeArray:: GetByteArray

セーフ配列の内容をにコピー `CByteArray` します。

```cpp
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>パラメーター

*bytes*<br/>
[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクトへの参照。

## <a name="colesafearraygetdim"></a><a name="getdim"></a> COleSafeArray:: GetDim

オブジェクトの次元数を返し `COleSafeArray` ます。

```
DWORD GetDim();
```

### <a name="return-value"></a>戻り値

セーフ配列内の次元の数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraygetelement"></a><a name="getelement"></a> COleSafeArray:: GetElement

セーフ配列の1つの要素を取得します。

```cpp
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>パラメーター

*rgIndices*<br/>
インデックスの配列へのポインター (配列の次元ごと)。

*pvData*<br/>
配列の要素を配置する位置へのポインター。

### <a name="remarks"></a>解説

この関数は、 `SafeArrayLock` `SafeArrayUnlock` 要素を取得する前と後に、windows の関数を自動的に呼び出します。 データ要素が文字列、オブジェクト、またはバリアントの場合、関数は正しい方法で要素をコピーします。 パラメーター *Pvdata* は、要素を格納するのに十分な大きさのバッファーを指している必要があります。

エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

## <a name="colesafearraygetelemsize"></a><a name="getelemsize"></a> COleSafeArray:: GetElemSize

オブジェクト内の要素のサイズを取得し `COleSafeArray` ます。

```
DWORD GetElemSize();
```

### <a name="return-value"></a>戻り値

セーフ配列の要素のサイズ (バイト単位)。

## <a name="colesafearraygetlbound"></a><a name="getlbound"></a> COleSafeArray:: GetLBound

オブジェクトの任意の次元の下限を返し `COleSafeArray` ます。

```cpp
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>パラメーター

*dwDim*<br/>
下限を取得する対象の配列の次元。

*pLBound*<br/>
下限を返す位置へのポインター。

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

## <a name="colesafearraygetonedimsize"></a><a name="getonedimsize"></a> COleSafeArray:: GetOneDimSize

1次元のオブジェクト内の要素の数を返し `COleSafeArray` ます。

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>戻り値

1次元のセーフ配列内の要素の数。

### <a name="example"></a>例

  [COleSafeArray:: CreateOneDim](#createonedim)の例を参照してください。

## <a name="colesafearraygetubound"></a><a name="getubound"></a> COleSafeArray:: GetUBound

セーフ配列の任意の次元の上限を返します。

```cpp
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>パラメーター

*dwDim*<br/>
上限を取得する対象の配列の次元。

*pUBound*<br/>
上限を返す位置へのポインター。

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

## <a name="colesafearraylock"></a><a name="lock"></a> COleSafeArray:: Lock

配列のロックカウントをインクリメントし、配列データへのポインターを配列記述子に配置します。

```cpp
void Lock();
```

### <a name="remarks"></a>解説

エラーが発生した場合、 [COleException](../../mfc/reference/coleexception-class.md)をスローします。

配列記述子内のポインターは、が呼び出されるまで有効です `Unlock` 。 の呼び出しは入れ子にする `Lock` ことができます。の呼び出しの数は同じである `Unlock` 必要があります。

配列はロックされている間は削除できません。

## <a name="colesafearrayoperator-lpcvariant"></a><a name="operator_lpcvariant"></a> COleSafeArray:: operator LPCVARIANT

このキャスト演算子を呼び出して、このオブジェクトの基になる構造体にアクセスし `VARIANT` `COleSafeArray` ます。

```
operator LPCVARIANT() const;
```

## <a name="colesafearrayoperator-lpvariant"></a><a name="operator_lpvariant"></a> COleSafeArray:: operator LPVARIANT

このキャスト演算子を呼び出して、このオブジェクトの基になる構造体にアクセスし `VARIANT` `COleSafeArray` ます。

```
operator LPVARIANT();
```

### <a name="remarks"></a>解説

`VARIANT`この関数によって返されるポインターによってアクセスされる構造体の値を変更すると、このオブジェクトの値が変更されることに注意 `COleSafeArray` してください。

## <a name="colesafearrayoperator-"></a><a name="operator_eq"></a> COleSafeArray:: operator =

これらのオーバーロードされた代入演算子は、source 値をこのオブジェクトにコピー `COleSafeArray` します。

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>解説

各演算子の簡単な説明を次に示します。

- **operator = (** *saSrc* **)** 既存 `COleSafeArray` のオブジェクトをこのオブジェクトにコピーします。

- **operator = (** *varsrc* **)** 既存 `VARIANT` のまたは `COleVariant` 配列をこのオブジェクトにコピーします。

- **operator = (** *psrc* **)**`VARIANT` *Psrc* によってアクセスされる配列オブジェクトをこのオブジェクトにコピーします。

## <a name="colesafearrayoperator-"></a><a name="operator_eq_eq"></a> COleSafeArray:: operator = =

この演算子は、2つ `SAFEARRAY` の配列 (、、 `VARIANT` `COleVariant` 、または `COleSafeArray` 配列) を比較し、等しい場合は0以外の値を返します。それ以外の場合は0を返します。

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>解説

2つの配列は、次元数が等しい場合、各次元のサイズが等しい場合、および要素値が等しい場合に等しくなります。

## <a name="colesafearrayoperator-ltlt"></a><a name="operator_lt_lt"></a> COleSafeArray:: operator &lt;&lt;

`COleSafeArray`挿入 (<<) 演算子は、アーカイブへのオブジェクトの診断ダンプと保存をサポートし `COleSafeArray` ます。

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

## <a name="colesafearrayptrofindex"></a><a name="ptrofindex"></a> COleSafeArray::P trOfIndex

インデックス値によって指定された要素へのポインターを返します。

```cpp
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>パラメーター

*rgIndices*<br/>
配列の要素を識別するインデックス値の配列。 要素のすべてのインデックスを指定する必要があります。

*ppvData*<br/>
返されるときに、 *rgIndices* 内の値によって識別される要素へのポインター。

## <a name="colesafearrayputelement"></a><a name="putelement"></a> COleSafeArray::P utElement

1 つの要素を配列に割り当てます。

```cpp
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>パラメーター

*rgIndices*<br/>
インデックスの配列へのポインター (配列の次元ごと)。

*pvData*<br/>
配列に割り当てるデータへのポインター。 VT_DISPATCH、VT_UNKNOWN、および VT_BSTR バリアント型はポインターであり、別のレベルの間接参照を必要としません。

### <a name="remarks"></a>解説

この関数は、要素を割り当てる前と後に、Windows 関数 [SafeArrayLock](/windows/win32/api/oleauto/nf-oleauto-safearraylock) と [SafeArrayUnlock](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock) を自動的に呼び出します。 データ要素が文字列、オブジェクト、バリアントの場合は、関数によって適切にコピーされ、既存の要素が文字列、オブジェクト、バリアントの場合は、関数によって適切にクリアされます。

配列は多重にロックできるため、配列が別の操作によってロックされている間に要素を配列に配置できることに注意してください。

エラーが発生した場合、関数は [CMemoryException](../../mfc/reference/cmemoryexception-class.md) または [COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

## <a name="colesafearrayredim"></a><a name="redim"></a> COleSafeArray:: Redim

セーフ配列の最上位 (右端) の下限を変更します。

```cpp
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>パラメーター

*psaboundNew*<br/>
新しい配列のバインドを含む新しいセーフ配列のバインドされた構造体へのポインター。 配列の最下位次元のみが変更される可能性があります。

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="colesafearrayresizeonedim"></a><a name="resizeonedim"></a> COleSafeArray:: ResizeOneDim

1次元のオブジェクト内の要素の数を変更 `COleSafeArray` します。

```cpp
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>パラメーター

*dwElements*<br/>
1次元セーフ配列内の要素の数。

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

  [COleSafeArray:: CreateOneDim](#createonedim)の例を参照してください。

## <a name="colesafearrayunaccessdata"></a><a name="unaccessdata"></a> COleSafeArray:: UnaccessData

配列のロックカウントをデクリメントし、によって取得されたポインターを無効にし `AccessData` ます。

```cpp
void UnaccessData();
```

### <a name="remarks"></a>解説

エラーが発生した場合、関数は [COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

  [COleSafeArray:: AccessData](#accessdata)の例を参照してください。

## <a name="colesafearrayunlock"></a><a name="unlock"></a> COleSafeArray:: Unlock

配列のロックカウントをデクリメントして、解放またはサイズ変更できるようにします。

```cpp
void Unlock();
```

### <a name="remarks"></a>解説

この関数は、配列内のデータへのアクセスが終了した後に呼び出されます。 エラーが発生した場合、 [COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleVariant クラス](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase クラス](../../mfc/reference/cdatabase-class.md)<br/>
