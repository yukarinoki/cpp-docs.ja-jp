---
title: COleSafeArray クラス
ms.date: 08/27/2018
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
ms.openlocfilehash: 0833dca9311689063c2ebeadd3942d9f5ce376e2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267161"
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
|[COleSafeArray::COleSafeArray](#colesafearray)|`COleSafeArray` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleSafeArray::AccessData](#accessdata)|配列データへのポインターを取得します。|
|[COleSafeArray::AllocData](#allocdata)|配列のメモリを割り当てます。|
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|セーフ配列記述子のメモリを割り当てます。|
|[COleSafeArray::Attach](#attach)|既存の制御`VARIANT`配列を`COleSafeArray`オブジェクト。|
|[COleSafeArray::Clear](#clear)|基になるすべてのデータを解放`VARIANT`します。|
|[COleSafeArray::Copy](#copy)|既存の配列のコピーを作成します。|
|[COleSafeArray::Create](#create)|セーフ配列を作成します。|
|[COleSafeArray::CreateOneDim](#createonedim)|1 次元作成`COleSafeArray`オブジェクト。|
|[COleSafeArray::Destroy](#destroy)|既存の配列を破棄します。|
|[COleSafeArray::DestroyData](#destroydata)|セーフ配列内のデータを破棄します。|
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|セーフ配列記述子を破棄します。|
|[COleSafeArray::Detach](#detach)|バリアント配列からのデタッチ、`COleSafeArray`オブジェクト (そのデータは解放されません)。|
|[COleSafeArray::GetByteArray](#getbytearray)|セーフ配列の内容をコピー、 [CByteArray](../../mfc/reference/cbytearray-class.md)します。|
|[COleSafeArray::GetDim](#getdim)|配列内の次元数を返します。|
|[Colesafearray::getelement](#getelement)|セーフ配列の 1 つの要素を取得します。|
|[COleSafeArray::GetElemSize](#getelemsize)|セーフ配列の 1 つの要素のバイト単位のサイズを返します。|
|[COleSafeArray::GetLBound](#getlbound)|セーフ配列の任意の次元の下限の境界を返します。|
|[COleSafeArray::GetOneDimSize](#getonedimsize)|1 次元内の要素の数を返します`COleSafeArray`オブジェクト。|
|[COleSafeArray::GetUBound](#getubound)|セーフ配列の任意の次元の上限の境界を返します。|
|[COleSafeArray::Lock](#lock)|配列のロック カウントをインクリメントし、配列のデータへのポインターを配列記述子に配置します。|
|[COleSafeArray::PtrOfIndex](#ptrofindex)|インデックス付けされた要素へのポインターを返します。|
|[COleSafeArray::PutElement](#putelement)|1 つの要素を配列に割り当てます。|
|[COleSafeArray::Redim](#redim)|セーフ配列の最下位 (右端) の境界を変更します。|
|[COleSafeArray::ResizeOneDim](#resizeonedim)|1 次元の要素の数を変更`COleSafeArray`オブジェクト。|
|[COleSafeArray::UnaccessData](#unaccessdata)|デクリメント、ロックは、配列のカウントし、によって取得されたポインターを無効に`AccessData`します。|
|[COleSafeArray::Unlock](#unlock)|ロック カウントをデクリメント、配列の解放やサイズを変更できるようにします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|基になるにアクセスする`VARIANT`の構造、`COleSafeArray`オブジェクト。|
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|基になるにアクセスする`VARIANT`の構造、`COleSafeArray`オブジェクト。|
|[COleSafeArray::operator =](#operator_eq)|値をコピー、`COleSafeArray`オブジェクト (`SAFEARRAY`、 `VARIANT`、 `COleVariant`、または`COleSafeArray`配列)。|
|[COleSafeArray::operator = =](#operator_eq_eq)|2 つのバリアント型の配列を比較します (`SAFEARRAY`、 `VARIANT`、 `COleVariant`、または`COleSafeArray`配列)。|
|[COleSafeArray::operator &lt;&lt;](#operator_lt_lt)|内容を出力する`COleSafeArray`ダンプ コンテキスト オブジェクト。|

## <a name="remarks"></a>Remarks

`COleSafeArray` OLE から派生した`VARIANT`構造体。 OLE`SAFEARRAY`メンバー関数を利用`COleSafeArray`同様、一連のバイトの 1 次元配列用にデザインされたメンバー関数として。

## <a name="inheritance-hierarchy"></a>継承階層

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

##  <a name="accessdata"></a>  COleSafeArray::AccessData

配列データへのポインターを取得します。

```
void AccessData(void** ppvData);
```

### <a name="parameters"></a>パラメーター

*ppvData*<br/>
配列データへのポインターへのポインター。

### <a name="remarks"></a>Remarks

エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

##  <a name="allocdata"></a>  COleSafeArray::AllocData

セーフ配列にメモリを割り当てます。

```
void AllocData();
```

### <a name="remarks"></a>Remarks

エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

##  <a name="allocdescriptor"></a>  COleSafeArray::AllocDescriptor

メモリのセーフ配列記述子を割り当てます。

```
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>パラメーター

*dwDims*<br/>
セーフ配列の次元数。

### <a name="remarks"></a>Remarks

エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

##  <a name="attach"></a>  COleSafeArray::Attach

既存のデータの制御`VARIANT`配列を`COleSafeArray`オブジェクト。

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>パラメーター

*varSrc*<br/>
`VARIANT` オブジェクト。 *VarSrc* VARTYPE パラメーターでなければなりません[VT_ARRAY](/windows/desktop/api/wtypes/ne-wtypes-varenum)します。

### <a name="remarks"></a>Remarks

ソース`VARIANT`の種類が VT_EMPTY に設定します。 この関数は、存在する場合に、現在の配列のデータをクリアします。

### <a name="example"></a>例

  例をご覧ください[COleSafeArray::AccessData](#accessdata)します。

##  <a name="clear"></a>  COleSafeArray::Clear

セーフ配列をクリアします。

```
void Clear();
```

### <a name="remarks"></a>Remarks

関数は、セーフ配列を設定してクリアします、 `VARTYPE` VT_EMPTY にオブジェクトの。 現在の内容がリリースされ、配列が解放されます。

##  <a name="colesafearray"></a>  COleSafeArray::COleSafeArray

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
既存の`COleSafeArray`オブジェクトまたは`SAFEARRAY`新しいにコピーされる`COleSafeArray`オブジェクト。

*vtSrc*<br/>
新しい VARTYPE`COleSafeArray`オブジェクト。

*psaSrc*<br/>
ポインターを`SAFEARRAY`新しいにコピーされる`COleSafeArray`オブジェクト。

*varSrc*<br/>
既存の`VARIANT`または`COleVariant`新しいにコピーされるオブジェクト`COleSafeArray`オブジェクト。

*pSrc*<br/>
ポインターを`VARIANT`新しいにコピーされるオブジェクト`COleSafeArray`オブジェクト。

### <a name="remarks"></a>Remarks

これらのコンス トラクターのすべてが新規作成`COleSafeArray`オブジェクト。 空のパラメーターがない場合`COleSafeArray`オブジェクトが作成されます (VT_EMPTY)。 場合、`COleSafeArray`が VARTYPE が暗黙的に呼ばれる別の配列からコピーされます (、 `COleSafeArray`、 `COleVariant`、または`VARIANT`)、ソース配列の VARTYPE は保持され、指定する必要はありません。 場合、`COleSafeArray`が VARTYPE がわからない場合は別の配列からコピーされます (`SAFEARRAY`)、VARTYPE を指定する必要があります、 *vtSrc*パラメーター。

エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

##  <a name="copy"></a>  COleSafeArray::Copy

既存のセーフ配列のコピーを作成します。

```
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>パラメーター

*ppsa*<br/>
新しい配列記述子を返す場所へのポインター。

### <a name="remarks"></a>Remarks

エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

##  <a name="create"></a>  COleSafeArray::Create

割り当て、配列にデータを初期化します。

```
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
配列 (つまり、配列の各要素の VARTYPE) の基本型。 VARTYPE は、バリアント型のサブセットに限定されます。 VT_ARRAY も VT_BYREF フラグを設定することができます。 VT_EMPTY、VT_ は、配列の有効なの基本型ではありません。 その他のすべての種類は有効です。

*dwDims*<br/>
配列の次元の数。 配列の作成後に変更できます[Redim](#redim)します。

*rgElements*<br/>
配列内の各ディメンションの要素の数の配列へのポインター。

*rgsabounds*<br/>
境界 (ディメンションごとに 1 つ) のベクターへのポインター、配列を割り当てられません。

### <a name="remarks"></a>Remarks

この関数は、必要に応じて、現在の配列のデータがクリアされます。 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="createonedim"></a>  COleSafeArray::CreateOneDim

新しい 1 次元`COleSafeArray`オブジェクト。

```
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>パラメーター

*vtSrc*<br/>
配列 (つまり、配列の各要素の VARTYPE) の基本型。

*dwElements*<br/>
配列内の要素の数。 配列の作成後に変更できます[でも](#resizeonedim)します。

*pvSrcData*<br/>
配列にコピーするデータへのポインター。

*nLBound*<br/>
配列の下限値です。

### <a name="remarks"></a>Remarks

関数は、割り当て、場合に、指定されたデータをコピーして、配列のデータを初期化しますポインター *pvSrcData*が NULL でないです。

エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

##  <a name="destroy"></a>  COleSafeArray::Destroy

既存の配列記述子と、配列内のすべてのデータを破棄します。

```
void Destroy();
```

### <a name="remarks"></a>Remarks

オブジェクトが配列に格納されている場合は、各オブジェクトが解放されます。 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

##  <a name="destroydata"></a>  COleSafeArray::DestroyData

セーフ配列のすべてのデータを破棄します。

```
void DestroyData();
```

### <a name="remarks"></a>Remarks

オブジェクトが配列に格納されている場合は、各オブジェクトが解放されます。 エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

##  <a name="destroydescriptor"></a>  COleSafeArray::DestroyDescriptor

セーフ配列記述子を破棄します。

```
void DestroyDescriptor();
```

### <a name="remarks"></a>Remarks

エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

##  <a name="detach"></a>  COleSafeArray::Detach

デタッチ、`VARIANT`からデータを`COleSafeArray`オブジェクト。

```
VARIANT Detach();
```

### <a name="return-value"></a>戻り値

基になる`VARIANT`値、`COleSafeArray`オブジェクト。

### <a name="remarks"></a>Remarks

関数は、オブジェクトの VARTYPE を VT_EMPTY に設定して、セーフ配列内のデータをデタッチします。 Windows 関数を呼び出すことによって、配列を解放する呼び出し元の責任[VariantClear](/windows/desktop/api/oleauto/nf-oleauto-variantclear)します。

エラー、関数、 [COleException](../../mfc/reference/coleexception-class.md)します。

### <a name="example"></a>例

  例をご覧ください[COleSafeArray::PutElement](#putelement)します。

##  <a name="getbytearray"></a>  COleSafeArray::GetByteArray

セーフ配列の内容をコピー、`CByteArray`します。

```
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>パラメーター

*バイト数*<br/>
参照を[CByteArray](../../mfc/reference/cbytearray-class.md)オブジェクト。

##  <a name="getdim"></a>  COleSafeArray::GetDim

内のディメンションの数を返します、`COleSafeArray`オブジェクト。

```
DWORD GetDim();
```

### <a name="return-value"></a>戻り値

セーフ配列の次元数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="getelement"></a>  COleSafeArray::GetElement

セーフ配列の 1 つの要素を取得します。

```
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>パラメーター

*rgIndices*<br/>
インデックスの配列へのポインター (配列の次元ごと)。

*pvData*<br/>
配列の要素を配置する場所へのポインター。

### <a name="remarks"></a>Remarks

この関数は、windows の関数を自動的に呼び出します`SafeArrayLock`と`SafeArrayUnlock`前に、と後、要素を取得します。 データ要素が文字列、オブジェクト、またはバリアントの場合、関数は、適切な方法で要素をコピーします。 パラメーター *pvData*要素を格納するための十分なバッファーの大きなをポイントする必要があります。

エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

##  <a name="getelemsize"></a>  COleSafeArray::GetElemSize

内の要素のサイズを取得、`COleSafeArray`オブジェクト。

```
DWORD GetElemSize();
```

### <a name="return-value"></a>戻り値

セーフ配列の要素のバイト単位のサイズ。

##  <a name="getlbound"></a>  COleSafeArray::GetLBound

任意の次元の下限の境界を返します、`COleSafeArray`オブジェクト。

```
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>パラメーター

*dwDim*<br/>
下限の境界を取得する対象の配列の次元。

*pLBound*<br/>
下限の境界を返す場所へのポインター。

### <a name="remarks"></a>Remarks

エラー、関数、 [COleException](../../mfc/reference/coleexception-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

##  <a name="getonedimsize"></a>  COleSafeArray::GetOneDimSize

1 次元内の要素の数を返します`COleSafeArray`オブジェクト。

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>戻り値

1 次元のセーフ配列の要素の数。

### <a name="example"></a>例

  例をご覧ください[COleSafeArray::CreateOneDim](#createonedim)します。

##  <a name="getubound"></a>  COleSafeArray::GetUBound

セーフ配列の任意の次元の上限の境界を返します。

```
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>パラメーター

*dwDim*<br/>
上限を取得する対象の配列の次元。

*pUBound*<br/>
上限の境界を返す場所へのポインター。

### <a name="remarks"></a>Remarks

エラー、関数、 [COleException](../../mfc/reference/coleexception-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

##  <a name="lock"></a>  COleSafeArray::Lock

配列と、配列のデータの配列記述子へのポインターの場所のロック カウントをインクリメントします。

```
void Lock();
```

### <a name="remarks"></a>Remarks

エラーがスロー、 [COleException](../../mfc/reference/coleexception-class.md)します。

配列記述子のポインターは有効期限`Unlock`が呼び出されます。 呼び出す`Lock`入れ子にできます。 への呼び出しの数が等しい`Unlock`が必要です。

ロックされている配列を削除できません。

##  <a name="operator_lpcvariant"></a>  COleSafeArray::operator LPCVARIANT

このキャスト演算子を呼び出す`VARIANT`この構造体`COleSafeArray`オブジェクト。

```
operator LPCVARIANT() const;
```

##  <a name="operator_lpvariant"></a>  COleSafeArray::operator LPVARIANT

このキャスト演算子を呼び出す`VARIANT`この構造体`COleSafeArray`オブジェクト。

```
operator LPVARIANT();
```

### <a name="remarks"></a>Remarks

値を変更することに注意してください、`VARIANT`これの値を変更する構造体のこの関数によって返されたポインターによってアクセス`COleSafeArray`オブジェクト。

##  <a name="operator_eq"></a>  COleSafeArray::operator =

これらのオーバー ロードされた代入演算子はコピー元の値をこの`COleSafeArray`オブジェクト。

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
  COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Remarks

各演算子の簡単な説明に従います。

- **operator = (** *saSrc* **)** 、既存のコピー`COleSafeArray`オブジェクトをこのオブジェクトにします。

- **operator = (** *varSrc* **)** 、既存のコピー`VARIANT`または`COleVariant`このオブジェクトの配列。

- **operator = (** *pSrc* **)** コピー、`VARIANT`からアクセスされるオブジェクトの配列*pSrc*このオブジェクトにします。

##  <a name="operator_eq_eq"></a>  COleSafeArray::operator = =

この演算子は、2 つの配列を比較します (`SAFEARRAY`、 `VARIANT`、 `COleVariant`、または`COleSafeArray`配列) し、それ以外の場合 0 以外の場合、0 以外の値を返します。

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Remarks

2 つの配列は同じ数のディメンション、各ディメンション、および要素値のサイズを持つ場合に等価です。

##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;

`COleSafeArray`挿入 (<<) 演算子は、診断ダンプと格納をサポートしています、`COleSafeArray`オブジェクトをアーカイブします。

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex

インデックス値によって指定された要素へのポインターを返します。

```
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>パラメーター

*rgIndices*<br/>
配列の要素を識別するインデックス値の配列。 要素のすべてのインデックスを指定する必要があります。

*ppvData*<br/>
内の値によって識別された要素に戻り、ポインターで*返す時*します。

##  <a name="putelement"></a>  COleSafeArray::PutElement

1 つの要素を配列に割り当てます。

```
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>パラメーター

*rgIndices*<br/>
インデックスの配列へのポインター (配列の次元ごと)。

*pvData*<br/>
配列に割り当てるデータへのポインター。 バリアント型が VT_DISPATCH、VT_UNKNOWN、および VT_BSTR ポインターは、別のレベルの間接参照を必要としません。

### <a name="remarks"></a>Remarks

この関数は、Windows の機能を自動的に呼び出します[SafeArrayLock](/windows/desktop/api/oleauto/nf-oleauto-safearraylock)と[SafeArrayUnlock](/windows/desktop/api/oleauto/nf-oleauto-safearrayunlock)前に、と後、要素を割り当てます。 データ要素が文字列、オブジェクト、バリアントの場合は、関数によって適切にコピーされ、既存の要素が文字列、オブジェクト、バリアントの場合は、関数によって適切にクリアされます。

配列は多重にロックできるため、配列が別の操作によってロックされている間に要素を配列に配置できることに注意してください。

エラー、関数、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)または[COleException](../../mfc/reference/coleexception-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

##  <a name="redim"></a>  COleSafeArray::Redim

セーフ配列の最下位 (右端) の境界を変更します。

```
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>パラメーター

*psaboundNew*<br/>
新しいセーフ配列へのポインターには、バインドされた新しい配列を含む構造体がバインドされています。 最下位の次元の配列のみを変更することがあります。

### <a name="remarks"></a>Remarks

エラー、関数、 [COleException](../../mfc/reference/coleexception-class.md)します。

##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim

1 次元の要素の数を変更`COleSafeArray`オブジェクト。

```
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>パラメーター

*dwElements*<br/>
1 次元のセーフ配列の要素の数。

### <a name="remarks"></a>Remarks

エラー、関数、 [COleException](../../mfc/reference/coleexception-class.md)します。

### <a name="example"></a>例

  例をご覧ください[COleSafeArray::CreateOneDim](#createonedim)します。

##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData

デクリメント、ロックは、配列のカウントし、によって取得されたポインターを無効に`AccessData`します。

```
void UnaccessData();
```

### <a name="remarks"></a>Remarks

エラー、関数、 [COleException](../../mfc/reference/coleexception-class.md)します。

### <a name="example"></a>例

  例をご覧ください[COleSafeArray::AccessData](#accessdata)します。

##  <a name="unlock"></a>  COleSafeArray::Unlock

ロック カウントをデクリメント、配列の解放やサイズを変更できるようにします。

```
void Unlock();
```

### <a name="remarks"></a>Remarks

配列内のデータへのアクセスが完了したら、この関数が呼び出されます。 エラーがスロー、 [COleException](../../mfc/reference/coleexception-class.md)します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleVariant クラス](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase クラス](../../mfc/reference/cdatabase-class.md)<br/>
