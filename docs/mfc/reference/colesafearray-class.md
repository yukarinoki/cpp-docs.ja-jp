---
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
ms.openlocfilehash: a7be9910b573cb5bc430d6608e75ce6661b71bc2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374865"
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
|[::コレセーフアレイ](#colesafearray)|`COleSafeArray` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を指定します。](#accessdata)|配列データへのポインターを取得します。|
|[コントロールアレイ::オロックデータ](#allocdata)|配列のメモリを割り当てます。|
|[::オレクト記述子](#allocdescriptor)|セーフ配列記述子のメモリを割り当てます。|
|[コレセーフアレイ::アタッチ](#attach)|オブジェクトに対して既存`VARIANT`の配列を`COleSafeArray`制御します。|
|[コレセーフアレイ::クリア](#clear)|基になる`VARIANT`のデータをすべて解放します。|
|[コレセーフアレイ::コピー](#copy)|既存の配列のコピーを作成します。|
|[作成](#create)|セーフ配列を作成します。|
|[コレセーフアレイ::作成ワンディム](#createonedim)|1 次元`COleSafeArray`オブジェクトを作成します。|
|[コレセーフアレイ::Dエストロイ](#destroy)|既存の配列を破棄します。|
|[コレセーフアレイ::Dエストロイデータ](#destroydata)|安全な配列のデータを破棄します。|
|[コレセーフアレイ::Dエストロイ記述子](#destroydescriptor)|セーフ配列の記述子を破棄します。|
|[コレセーフアレイ::Dエタッハ](#detach)|オブジェクトからバリアント型 (VARIANT) 配列を`COleSafeArray`デタッチします (データが解放されないようにします)。|
|[を指定します。](#getbytearray)|セーフ配列の内容を[CByteArray](../../mfc/reference/cbytearray-class.md)にコピーします。|
|[コレセーフアレイ::ゲットディム](#getdim)|配列内の次元数を返します。|
|[を指定します。](#getelement)|セーフ配列の単一の要素を取得します。|
|[::ゲテレムサイズ](#getelemsize)|セーフ配列内の 1 つの要素のサイズ (バイト単位) を返します。|
|[を指定します。](#getlbound)|セーフ配列の任意の次元の下限を返します。|
|[::1つのディムサイズ](#getonedimsize)|1 次元`COleSafeArray`オブジェクトの要素数を返します。|
|[を指定します。](#getubound)|セーフ配列の任意の次元の上限を返します。|
|[コントロールアレイ::ロック](#lock)|配列のロックカウントをインクリメントし、配列記述子の配列データへのポインタを配置します。|
|[:Pトローインデックス](#ptrofindex)|インデックス付き要素へのポインターを返します。|
|[を指定 :Pします。](#putelement)|1 つの要素を配列に割り当てます。|
|[コレセーフアレイ::レディム](#redim)|セーフ配列の最下位 (右端) の境界を変更します。|
|[::リサイズワンディム](#resizeonedim)|1 次元`COleSafeArray`オブジェクトの要素数を変更します。|
|[::アクセスデータの取得](#unaccessdata)|配列のロックカウントを減算し、 によって`AccessData`取得されたポインターを無効にします。|
|[コレセーフアレイ::ロック解除](#unlock)|配列のロックカウントを減算して、配列を解放またはサイズ変更できるようにします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[コントロールアレイ::演算子 LPC変](#operator_lpcvariant)|オブジェクトの基になる`VARIANT`構造に`COleSafeArray`アクセスします。|
|[コントロールアレイ::演算子 LP 変](#operator_lpvariant)|オブジェクトの基になる`VARIANT`構造に`COleSafeArray`アクセスします。|
|[コントロールアレイ::演算子 =](#operator_eq)|値を`COleSafeArray`オブジェクト (`SAFEARRAY`、 `VARIANT` `COleVariant`、、`COleSafeArray`配列 ) にコピーします。|
|[コントロールアレイ::演算子 ==](#operator_eq_eq)|2 つのバリアント配列 (`SAFEARRAY` `VARIANT`, `COleVariant`, `COleSafeArray` , ,, ) を比較します。|
|[コントロールアレイ::演算子&lt;&lt;](#operator_lt_lt)|オブジェクトの内容を`COleSafeArray`ダンプ コンテキストに出力します。|

## <a name="remarks"></a>解説

`COleSafeArray`は OLE`VARIANT`構造体から派生します。 OLE`SAFEARRAY`メンバー関数は、`COleSafeArray`を通じて使用できるだけでなく、バイトの 1 次元配列用に特別に設計された一連のメンバー関数も使用できます。

## <a name="inheritance-hierarchy"></a>継承階層

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="colesafearrayaccessdata"></a><a name="accessdata"></a>を指定します。

配列データへのポインターを取得します。

```
void AccessData(void** ppvData);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
配列データへのポインターへのポインター。

### <a name="remarks"></a>解説

エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

## <a name="colesafearrayallocdata"></a><a name="allocdata"></a>コントロールアレイ::オロックデータ

セーフ配列のメモリを割り当てます。

```
void AllocData();
```

### <a name="remarks"></a>解説

エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

## <a name="colesafearrayallocdescriptor"></a><a name="allocdescriptor"></a>::オレクト記述子

セーフ配列の記述子にメモリを割り当てます。

```
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>パラメーター

*ドフディム*<br/>
セーフ配列内の次元数。

### <a name="remarks"></a>解説

エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

## <a name="colesafearrayattach"></a><a name="attach"></a>コレセーフアレイ::アタッチ

オブジェクトに対して既存`VARIANT`の配列のデータを制御`COleSafeArray`します。

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>パラメーター

*varSrc*<br/>
`VARIANT` オブジェクト。 *varSrc*パラメーターには VARTYPE [VT_ARRAY](/windows/win32/api/wtypes/ne-wtypes-varenum)が必要です。

### <a name="remarks"></a>解説

ソース`VARIANT`の型がVT_EMPTYに設定されています。 この関数は、現在の配列データがあればクリアします。

### <a name="example"></a>例

  の例[を](#accessdata)参照してください。

## <a name="colesafearrayclear"></a><a name="clear"></a>コレセーフアレイ::クリア

セーフ配列をクリアします。

```
void Clear();
```

### <a name="remarks"></a>解説

この関数は、オブジェクトの を`VARTYPE`VT_EMPTY に設定して、セーフ配列をクリアします。 現在の内容が解放され、配列が解放されます。

## <a name="colesafearraycolesafearray"></a><a name="colesafearray"></a>::コレセーフアレイ

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

*サスルク*<br/>
既存`COleSafeArray`のオブジェクト、`SAFEARRAY`または新しい`COleSafeArray`オブジェクトにコピーするオブジェクト。

*vtSrc*<br/>
新しい`COleSafeArray`オブジェクトの VARTYPE。

*psaSrc*<br/>
新しい`COleSafeArray`オブジェクトに`SAFEARRAY`コピーする a へのポインター。

*varSrc*<br/>
新しい`VARIANT``COleSafeArray`オブジェクト`COleVariant`にコピーされる既存のオブジェクトまたはオブジェクト。

*pSrc*<br/>
新しい`VARIANT``COleSafeArray`オブジェクトにコピーされるオブジェクトへのポインター。

### <a name="remarks"></a>解説

これらのコンストラクターはすべて、新しい`COleSafeArray`オブジェクトを作成します。 パラメータがない場合は、空`COleSafeArray`のオブジェクトが作成されます (VT_EMPTY)。 VARTYPE`COleSafeArray`が暗黙的に認識されている別の`COleSafeArray`配列 ( 、 、 `COleVariant`、 `VARIANT`、 ) から コピーされた場合、ソース配列の VARTYPE は保持され、指定する必要はありません。 VARTYPE`COleSafeArray`が不明な別の配列から コピーされる場合は`SAFEARRAY`、 *vtSrc*パラメーターに VARTYPE を指定する必要があります。

エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

## <a name="colesafearraycopy"></a><a name="copy"></a>コレセーフアレイ::コピー

既存のセーフ配列のコピーを作成します。

```
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>パラメーター

*ppsa*<br/>
新しい配列記述子を返す位置へのポインター。

### <a name="remarks"></a>解説

エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

## <a name="colesafearraycreate"></a><a name="create"></a>作成

配列のデータを割り当てて初期化します。

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
配列の基本型 (配列の各要素の VARTYPE)。 VARTYPE は、バリアント型のサブセットに制限されます。 VT_ARRAYもVT_BYREFフラグも設定できません。 VT_EMPTYとVT_NULLは、配列の有効な基本型ではありません。 その他のタイプはすべて合法です。

*ドフディム*<br/>
配列内の次元数。 これは、配列が[Redim](#redim)で作成された後に変更できます。

*rg要素*<br/>
配列内の各次元の要素数の配列へのポインター。

*rgsabounds*<br/>
配列に割り当てる境界のベクトル (各次元に 1 つ) へのポインター。

### <a name="remarks"></a>解説

この関数は、必要に応じて現在の配列データをクリアします。 エラーが発生すると、関数は[CMemoryException](../../mfc/reference/cmemoryexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraycreateonedim"></a><a name="createonedim"></a>コレセーフアレイ::作成ワンディム

新しい 1 次元`COleSafeArray`オブジェクトを作成します。

```
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>パラメーター

*vtSrc*<br/>
配列の基本型 (配列の各要素の VARTYPE)。

*dw要素*<br/>
配列内の要素の数。 これは、配列が[ResizeOneDim](#resizeonedim)で作成された後に変更できます。

*データ*<br/>
配列にコピーするデータへのポインター。

*nLバウンド*<br/>
配列の下限。

### <a name="remarks"></a>解説

この関数は、配列のデータを割り当てて初期化し、ポインター *pvSrcData*が NULL でない場合に指定されたデータをコピーします。

エラーが発生すると、関数は[CMemoryException](../../mfc/reference/cmemoryexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

## <a name="colesafearraydestroy"></a><a name="destroy"></a>コレセーフアレイ::Dエストロイ

既存の配列記述子と配列内のすべてのデータを破棄します。

```
void Destroy();
```

### <a name="remarks"></a>解説

オブジェクトが配列に格納されている場合、各オブジェクトは解放されます。 エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

## <a name="colesafearraydestroydata"></a><a name="destroydata"></a>コレセーフアレイ::Dエストロイデータ

安全な配列内のすべてのデータを破棄します。

```
void DestroyData();
```

### <a name="remarks"></a>解説

オブジェクトが配列に格納されている場合、各オブジェクトは解放されます。 エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

## <a name="colesafearraydestroydescriptor"></a><a name="destroydescriptor"></a>コレセーフアレイ::Dエストロイ記述子

セーフ配列の記述子を破棄します。

```
void DestroyDescriptor();
```

### <a name="remarks"></a>解説

エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

## <a name="colesafearraydetach"></a><a name="detach"></a>コレセーフアレイ::Dエタッハ

オブジェクトからデータ`VARIANT`をデタッチ`COleSafeArray`します。

```
VARIANT Detach();
```

### <a name="return-value"></a>戻り値

`COleSafeArray`オブジェクトの基になる`VARIANT`値。

### <a name="remarks"></a>解説

この関数は、オブジェクトの VARTYPE をVT_EMPTYに設定することにより、セーフ配列内のデータをデタッチします。 Windows 関数バリアント[クリア](/windows/win32/api/oleauto/nf-oleauto-variantclear)を呼び出すことによって配列を解放する呼び出し元の責任です。

エラーが発生すると、関数は[COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

  の例[:P](#putelement)を参照してください。

## <a name="colesafearraygetbytearray"></a><a name="getbytearray"></a>を指定します。

セーフ配列の内容を`CByteArray`にコピーします。

```
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>パラメーター

*バイト*<br/>
[オブジェクト](../../mfc/reference/cbytearray-class.md)への参照。

## <a name="colesafearraygetdim"></a><a name="getdim"></a>コレセーフアレイ::ゲットディム

オブジェクト内の次元の数を`COleSafeArray`返します。

```
DWORD GetDim();
```

### <a name="return-value"></a>戻り値

セーフ配列内の次元数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraygetelement"></a><a name="getelement"></a>を指定します。

セーフ配列の単一の要素を取得します。

```
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>パラメーター

*rgインデックス*<br/>
インデックスの配列へのポインター (配列の次元ごと)。

*pv データ*<br/>
配列の要素を配置する位置へのポインター。

### <a name="remarks"></a>解説

この関数は、要素を取得`SafeArrayLock`する`SafeArrayUnlock`前後に、自動的にウィンドウ関数を呼び出します。 データ要素が文字列、オブジェクト、またはバリアントである場合、関数は正しい方法で要素をコピーします。 pvData*pvData*パラメーターは、要素を格納するのに十分な大きさのバッファーを指す必要があります。

エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

## <a name="colesafearraygetelemsize"></a><a name="getelemsize"></a>::ゲテレムサイズ

オブジェクト内の要素のサイズを`COleSafeArray`取得します。

```
DWORD GetElemSize();
```

### <a name="return-value"></a>戻り値

セーフ配列の要素のサイズ (バイト単位)。

## <a name="colesafearraygetlbound"></a><a name="getlbound"></a>を指定します。

オブジェクトの任意の次元の下限を`COleSafeArray`返します。

```
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>パラメーター

*ドフディム*<br/>
下限を取得する配列の次元。

*pLバウンド*<br/>
下限を返す位置へのポインター。

### <a name="remarks"></a>解説

エラーが発生すると、関数は[COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

## <a name="colesafearraygetonedimsize"></a><a name="getonedimsize"></a>::1つのディムサイズ

1 次元`COleSafeArray`オブジェクトの要素数を返します。

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>戻り値

1 次元セーフ配列内の要素の数。

### <a name="example"></a>例

  の例を参照[してください。](#createonedim)

## <a name="colesafearraygetubound"></a><a name="getubound"></a>を指定します。

セーフ配列の任意の次元の上限を返します。

```
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>パラメーター

*ドフディム*<br/>
上限を取得する配列の次元。

*pUバウンド*<br/>
上限を返す位置へのポインター。

### <a name="remarks"></a>解説

エラーが発生すると、関数は[COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

## <a name="colesafearraylock"></a><a name="lock"></a>コントロールアレイ::ロック

配列のロックカウントをインクリメントし、配列記述子の配列データへのポインタを配置します。

```
void Lock();
```

### <a name="remarks"></a>解説

エラーが発生すると[、COleException](../../mfc/reference/coleexception-class.md)がスローされます。

配列記述子内のポインターは、呼び`Unlock`出されるまで有効です。 呼び`Lock`出しは入れ子にできます。同じ数の呼び`Unlock`出しが必要です。

ロックされている間は、アレイを削除できません。

## <a name="colesafearrayoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>コントロールアレイ::演算子 LPC変

このキャスト演算子を呼び出して`VARIANT`、この`COleSafeArray`オブジェクトの基になる構造体にアクセスします。

```
operator LPCVARIANT() const;
```

## <a name="colesafearrayoperator-lpvariant"></a><a name="operator_lpvariant"></a>コントロールアレイ::演算子 LP 変

このキャスト演算子を呼び出して`VARIANT`、この`COleSafeArray`オブジェクトの基になる構造体にアクセスします。

```
operator LPVARIANT();
```

### <a name="remarks"></a>解説

この関数によって返されるポインターが`VARIANT`アクセスする構造体の値を変更すると、この`COleSafeArray`オブジェクトの値が変更されることに注意してください。

## <a name="colesafearrayoperator-"></a><a name="operator_eq"></a>コントロールアレイ::演算子 =

これらのオーバーロードされた代入演算子は、ソース値をこの`COleSafeArray`オブジェクトにコピーします。

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>解説

各演算子の簡単な説明を次に示します。

- 演算子 *=(saSrc)* **)** **operator =(** 既存`COleSafeArray`のオブジェクトをこのオブジェクトにコピーします。

- 演算子 *=(varSrc)* **)** **operator =(** 既存`VARIANT`の配列または`COleVariant`配列をこのオブジェクトにコピーします。

- 演算子 *=(pSrc)* **)** **operator =(**`VARIANT` *pSrc*によってアクセスされた配列オブジェクトをこのオブジェクトにコピーします。

## <a name="colesafearrayoperator-"></a><a name="operator_eq_eq"></a>コントロールアレイ::演算子 ==

この演算子は、2 つの配列`SAFEARRAY` `VARIANT`( `COleVariant`, `COleSafeArray` , , , 配列) を比較し、等しい場合は 0 以外を返します。それ以外の場合は 0。

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>解説

2 つの配列は、次元数が等しく、各次元のサイズが等しく、要素値が等しい場合に等しくなります。

## <a name="colesafearrayoperator-ltlt"></a><a name="operator_lt_lt"></a>コントロールアレイ::演算子&lt;&lt;

挿入`COleSafeArray`(<<) 演算子は、診断ダンプと`COleSafeArray`オブジェクトのアーカイブへの保管をサポートします。

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

## <a name="colesafearrayptrofindex"></a><a name="ptrofindex"></a>:Pトローインデックス

インデックス値で指定された要素へのポインターを返します。

```
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>パラメーター

*rgインデックス*<br/>
配列の要素を識別するインデックス値の配列。 要素のすべてのインデックスを指定する必要があります。

*を使用します。*<br/>
戻り値の場合は、 *rgIndices*の値で識別される要素へのポインター。

## <a name="colesafearrayputelement"></a><a name="putelement"></a>を指定 :Pします。

1 つの要素を配列に割り当てます。

```
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>パラメーター

*rgインデックス*<br/>
インデックスの配列へのポインター (配列の次元ごと)。

*pv データ*<br/>
配列に割り当てるデータへのポインター。 VT_DISPATCH、VT_UNKNOWN、およびVT_BSTRバリアント型はポインターであり、別のレベルの間接参照を必要としません。

### <a name="remarks"></a>解説

この関数は、要素を割り当てる前と後に Windows 関数[セーフアレイロック](/windows/win32/api/oleauto/nf-oleauto-safearraylock)と[セーフアレイ ロックを](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock)自動的に呼び出します。 データ要素が文字列、オブジェクト、バリアントの場合は、関数によって適切にコピーされ、既存の要素が文字列、オブジェクト、バリアントの場合は、関数によって適切にクリアされます。

配列は多重にロックできるため、配列が別の操作によってロックされている間に要素を配列に配置できることに注意してください。

エラーが発生すると、関数は[C メモリ例外](../../mfc/reference/cmemoryexception-class.md)または[COleException を](../../mfc/reference/coleexception-class.md)スローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

## <a name="colesafearrayredim"></a><a name="redim"></a>コレセーフアレイ::レディム

セーフ配列の最下位 (右端) の境界を変更します。

```
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>パラメーター

*psaboundNew*<br/>
バインドされた新しい配列を含む新しいセーフ配列のバインドされた構造体へのポインター。 配列の最下位次元のみが変更できます。

### <a name="remarks"></a>解説

エラーが発生すると、関数は[COleException](../../mfc/reference/coleexception-class.md)をスローします。

## <a name="colesafearrayresizeonedim"></a><a name="resizeonedim"></a>::リサイズワンディム

1 次元`COleSafeArray`オブジェクトの要素数を変更します。

```
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>パラメーター

*dw要素*<br/>
1 次元セーフ配列内の要素の数。

### <a name="remarks"></a>解説

エラーが発生すると、関数は[COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

  の例を参照[してください。](#createonedim)

## <a name="colesafearrayunaccessdata"></a><a name="unaccessdata"></a>::アクセスデータの取得

配列のロックカウントを減算し、 によって`AccessData`取得されたポインターを無効にします。

```
void UnaccessData();
```

### <a name="remarks"></a>解説

エラーが発生すると、関数は[COleException](../../mfc/reference/coleexception-class.md)をスローします。

### <a name="example"></a>例

  の例[を](#accessdata)参照してください。

## <a name="colesafearrayunlock"></a><a name="unlock"></a>コレセーフアレイ::ロック解除

配列のロックカウントを減算して、配列を解放またはサイズ変更できるようにします。

```
void Unlock();
```

### <a name="remarks"></a>解説

この関数は、配列内のデータへのアクセスが終了した後に呼び出されます。 エラーが発生すると[、COleException](../../mfc/reference/coleexception-class.md)がスローされます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleVariant クラス](../../mfc/reference/colevariant-class.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)<br/>
[クラス](../../mfc/reference/cdatabase-class.md)<br/>
