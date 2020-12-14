---
description: '詳細情報: CMFCFilterChunkValueImpl クラス'
title: CMFCFilterChunkValueImpl クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
ms.openlocfilehash: f2db7fdf6d6d24cb906b3190d34310e1f6724194
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265468"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl クラス

これは、チャンクとプロパティ値のペアのロジックを簡略化するクラスです。

## <a name="syntax"></a>構文

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|オブジェクトを Destructs します。|
|[CMFCFilterChunkValueImpl:: CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: Clear](#clear)|ChunkValue をクリアします。|
|[CMFCFilterChunkValueImpl:: CopyChunk](#copychunk)|チャンクの特性を記述する構造体にこのチャンクをコピーします。|
|[CMFCFilterChunkValueImpl:: CopyFrom](#copyfrom)|このチャンク値をもう一方の値から初期化します。|
|[CMFCFilterChunkValueImpl:: GetChunkGUID](#getchunkguid)|チャンク GUID を取得します。|
|[CMFCFilterChunkValueImpl:: GetChunkPID](#getchunkpid)|チャンク PID (プロパティ ID) を取得します。|
|[CMFCFilterChunkValueImpl:: GetChunkType](#getchunktype)|チャンクの種類を取得します。|
|[CMFCFilterChunkValueImpl:: GetString](#getstring)|文字列値を取得します。|
|[CMFCFilterChunkValueImpl:: GetValue](#getvalue)|割り当てられた propvariant として値を取得します。|
|[CMFCFilterChunkValueImpl:: Getvalu/Alloc](#getvaluenoalloc)|割り当てられていない (内部値) 値を返します。|
|[CMFCFilterChunkValueImpl:: IsValid](#isvalid)|このプロパティ値が有効かどうかを確認します。|
|[CMFCFilterChunkValueImpl:: Setブール値](#setboolvalue)|オーバーロードされます。 プロパティをキーでブール値に設定します。|
|[CMFCFilterChunkValueImpl:: SetDwordValue](#setdwordvalue)|キーによってプロパティを DWORD に設定します。|
|[CMFCFilterChunkValueImpl:: SetFileTimeValue](#setfiletimevalue)|キーによってプロパティを filetime に設定します。|
|[CMFCFilterChunkValueImpl:: SetInt64Value](#setint64value)|キーによってプロパティを int64 に設定します。|
|[CMFCFilterChunkValueImpl:: SetIntValue](#setintvalue)|キーによってプロパティを int に設定します。|
|[CMFCFilterChunkValueImpl:: SetLongValue](#setlongvalue)|キーによってプロパティを LONG に設定します。|
|[CMFCFilterChunkValueImpl:: SetSystemTimeValue](#setsystemtimevalue)|キーによってプロパティを SystemTime に設定します。|
|[CMFCFilterChunkValueImpl:: SetTextValue](#settextvalue)|キーによってプロパティを Unicode 文字列に設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: SetChunk](#setchunk)|チャンクの共通プロパティを設定するヘルパー関数。|

## <a name="remarks"></a>解説

を使用するには、適切な種類の CMFCFilterChunkValueImpl クラスを作成するだけです。

例:

CMFCFilterChunkValueImpl チャンク。

hr = チャンク。Setブール値 (PKEY_IsAttachment、true)。

または

hr = チャンク。SetFileTimeValue (PKEY_ItemDate, ftLastModified);

## <a name="inheritance-hierarchy"></a>継承階層

`ATL::IFilterChunkValue`

[CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cmfcfilterchunkvalueimplclear"></a><a name="clear"></a> CMFCFilterChunkValueImpl:: Clear

ChunkValue をクリアします。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="cmfcfilterchunkvalueimpl"></a> CMFCFilterChunkValueImpl:: CMFCFilterChunkValueImpl

オブジェクトを構築します。

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="_dtorcmfcfilterchunkvalueimpl"></a> CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl

オブジェクトを Destructs します。

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplcopychunk"></a><a name="copychunk"></a> CMFCFilterChunkValueImpl:: CopyChunk

チャンクの特性を記述する構造体にこのチャンクをコピーします。

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>パラメーター

*pStatChunk*<br/>
チャンクの特性を記述するターゲット値へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplcopyfrom"></a><a name="copyfrom"></a> CMFCFilterChunkValueImpl:: CopyFrom

このチャンク値をもう一方の値から初期化します。

```cpp
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>パラメーター

*pValue*<br/>
コピー元のソース値を指定します。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetchunkguid"></a><a name="getchunkguid"></a> CMFCFilterChunkValueImpl:: GetChunkGUID

チャンク GUID を取得します。

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>戻り値

チャンクを識別する GUID への参照。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetchunkpid"></a><a name="getchunkpid"></a> CMFCFilterChunkValueImpl:: GetChunkPID

チャンク PID (プロパティ ID) を取得します。

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>戻り値

プロパティ ID を含む DWORD 値です。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetchunktype"></a><a name="getchunktype"></a> CMFCFilterChunkValueImpl:: GetChunkType

チャンクの種類を取得します。

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>戻り値

現在のチャンクがテキスト型プロパティであるか、値型プロパティであるかを指定する CHUNKSTATE 列挙値。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetstring"></a><a name="getstring"></a> CMFCFilterChunkValueImpl:: GetString

文字列値を取得します。

```
CString &GetString();
```

### <a name="return-value"></a>戻り値

チャンク値を格納している文字列。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetvalue"></a><a name="getvalue"></a> CMFCFilterChunkValueImpl:: GetValue

割り当てられた propvariant として値を取得します。

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>パラメーター

*ppPropVariant*<br/>
関数からが返された場合、このパラメーターにはチャンク値が格納されます。

### <a name="return-value"></a>戻り値

PROPVARIANT が正常に割り当てられ、チャンク値が *Pppropvariant* に正常にコピーされたかどうかを S_OK します。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetvaluenoalloc"></a><a name="getvaluenoalloc"></a> CMFCFilterChunkValueImpl:: Getvalu/Alloc

割り当てられていない (内部値) 値を返します。

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>戻り値

現在のチャンク値を返します。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplisvalid"></a><a name="isvalid"></a> CMFCFilterChunkValueImpl:: IsValid

このプロパティ値が有効かどうかを確認します。

```
BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

現在のチャンク値が有効である場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetboolvalue"></a><a name="setboolvalue"></a> CMFCFilterChunkValueImpl:: Setブール値

オーバーロードされます。 プロパティをキーでブール値に設定します。

```
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    VARIANT_BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>パラメーター

*pkey*<br/>
プロパティキーを指定します。

*bVal*<br/>
設定するチャンク値を指定します。

*chunkType*<br/>
フラグは、このチャンクにテキスト型または値型のプロパティが含まれているかどうかを示します。 フラグの値は、CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語およびサブ言語。 チャンクロケールは、テキストの適切な単語区切りを実行するためにドキュメントインデクサーによって使用されます。 チャンクがテキスト型でも、データ型 VT_LPWSTR、VT_LPSTR、または VT_BSTR を持つ値型でもない場合、このフィールドは無視されます。

*cwcLenSource*<br/>
現在のチャンクの派生元であるソーステキストの長さ (文字数)。 0の値は、ソーステキストと派生テキストの文字単位の対応を示します。 0以外の値は、そのような直接の対応が存在しないことを意味します。

*cwcStartSource*<br/>
ソースチャンクの派生チャンクのソーステキストの開始位置を示すオフセット。

*chunkBreakType*<br/>
前のチャンクと現在のチャンクを区切る中断の種類。 値は CHUNK_BREAKTYPE 列挙体からのものです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetchunk"></a><a name="setchunk"></a> CMFCFilterChunkValueImpl:: SetChunk

チャンクの共通プロパティを設定するヘルパー関数。

```
HRESULT SetChunk(
    REFPROPERTYKEY pkey,
    CHUNKSTATE chunkType=CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>パラメーター

*pkey*<br/>
プロパティキーを指定します。

*chunkType*<br/>
フラグは、このチャンクにテキスト型または値型のプロパティが含まれているかどうかを示します。 フラグの値は、CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語およびサブ言語。 チャンクロケールは、テキストの適切な単語区切りを実行するためにドキュメントインデクサーによって使用されます。 チャンクがテキスト型でも、データ型 VT_LPWSTR、VT_LPSTR、または VT_BSTR を持つ値型でもない場合、このフィールドは無視されます。

*cwcLenSource*<br/>
現在のチャンクの派生元であるソーステキストの長さ (文字数)。 0の値は、ソーステキストと派生テキストの文字単位の対応を示します。 0以外の値は、そのような直接の対応が存在しないことを意味します。

*cwcStartSource*<br/>
ソースチャンクの派生チャンクのソーステキストの開始位置を示すオフセット。

*chunkBreakType*<br/>
前のチャンクと現在のチャンクを区切る中断の種類。 値は CHUNK_BREAKTYPE 列挙体からのものです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合はエラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetdwordvalue"></a><a name="setdwordvalue"></a> CMFCFilterChunkValueImpl:: SetDwordValue

キーを使ってプロパティを DWORD に設定します。

```
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,
    DWORD dwVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>パラメーター

*pkey*<br/>
プロパティキーを指定します。

*dwVal*<br/>
設定するチャンク値を指定します。

*chunkType*<br/>
フラグは、このチャンクにテキスト型または値型のプロパティが含まれているかどうかを示します。 フラグの値は、CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語およびサブ言語。 チャンクロケールは、テキストの適切な単語区切りを実行するためにドキュメントインデクサーによって使用されます。 チャンクがテキスト型でも、データ型 VT_LPWSTR、VT_LPSTR、または VT_BSTR を持つ値型でもない場合、このフィールドは無視されます。

*cwcLenSource*<br/>
現在のチャンクの派生元であるソーステキストの長さ (文字数)。 0の値は、ソーステキストと派生テキストの文字単位の対応を示します。 0以外の値は、そのような直接の対応が存在しないことを意味します。

*cwcStartSource*<br/>
ソースチャンクの派生チャンクのソーステキストの開始位置を示すオフセット。

*chunkBreakType*<br/>
前のチャンクと現在のチャンクを区切る中断の種類。 値は CHUNK_BREAKTYPE 列挙体からのものです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetfiletimevalue"></a><a name="setfiletimevalue"></a> CMFCFilterChunkValueImpl:: SetFileTimeValue

プロパティをキーで filetime に設定します。

```
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,
    FILETIME dtVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>パラメーター

*pkey*<br/>
プロパティキーを指定します。

*dtVal*<br/>
設定するチャンク値を指定します。

*chunkType*<br/>
フラグは、このチャンクにテキスト型または値型のプロパティが含まれているかどうかを示します。 フラグの値は、CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語およびサブ言語。 チャンクロケールは、テキストの適切な単語区切りを実行するためにドキュメントインデクサーによって使用されます。 チャンクがテキスト型でも、データ型 VT_LPWSTR、VT_LPSTR、または VT_BSTR を持つ値型でもない場合、このフィールドは無視されます。

*cwcLenSource*<br/>
現在のチャンクの派生元であるソーステキストの長さ (文字数)。 0の値は、ソーステキストと派生テキストの文字単位の対応を示します。 0以外の値は、そのような直接の対応が存在しないことを意味します。

*cwcStartSource*<br/>
ソースチャンクの派生チャンクのソーステキストの開始位置を示すオフセット。

*chunkBreakType*<br/>
前のチャンクと現在のチャンクを区切る中断の種類。 値は CHUNK_BREAKTYPE 列挙体からのものです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetint64value"></a><a name="setint64value"></a> CMFCFilterChunkValueImpl:: SetInt64Value

プロパティをキーで int64 に設定します。

```
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,
    __int64 nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>パラメーター

*pkey*<br/>
プロパティキーを指定します。

*nVal*<br/>
設定するチャンク値を指定します。

*chunkType*<br/>
フラグは、このチャンクにテキスト型または値型のプロパティが含まれているかどうかを示します。 フラグの値は、CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語およびサブ言語。 チャンクロケールは、テキストの適切な単語区切りを実行するためにドキュメントインデクサーによって使用されます。 チャンクがテキスト型でも、データ型 VT_LPWSTR、VT_LPSTR、または VT_BSTR を持つ値型でもない場合、このフィールドは無視されます。

*cwcLenSource*<br/>
現在のチャンクの派生元であるソーステキストの長さ (文字数)。 0の値は、ソーステキストと派生テキストの文字単位の対応を示します。 0以外の値は、そのような直接の対応が存在しないことを意味します。

*cwcStartSource*<br/>
ソースチャンクの派生チャンクのソーステキストの開始位置を示すオフセット。

*chunkBreakType*<br/>
前のチャンクと現在のチャンクを区切る中断の種類。 値は CHUNK_BREAKTYPE 列挙体からのものです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetintvalue"></a><a name="setintvalue"></a> CMFCFilterChunkValueImpl:: SetIntValue

プロパティをキーで int に設定します。

```
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,
    int nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>パラメーター

*pkey*<br/>
プロパティキーを指定します。

*nVal*<br/>
設定するチャンク値を指定します。

*chunkType*<br/>
フラグは、このチャンクにテキスト型または値型のプロパティが含まれているかどうかを示します。 フラグの値は、CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語およびサブ言語。 チャンクロケールは、テキストの適切な単語区切りを実行するためにドキュメントインデクサーによって使用されます。 チャンクがテキスト型でも、データ型 VT_LPWSTR、VT_LPSTR、または VT_BSTR を持つ値型でもない場合、このフィールドは無視されます。

*cwcLenSource*<br/>
現在のチャンクの派生元であるソーステキストの長さ (文字数)。 0の値は、ソーステキストと派生テキストの文字単位の対応を示します。 0以外の値は、そのような直接の対応が存在しないことを意味します。

*cwcStartSource*<br/>
ソースチャンクの派生チャンクのソーステキストの開始位置を示すオフセット。

*chunkBreakType*<br/>
前のチャンクと現在のチャンクを区切る中断の種類。 値は CHUNK_BREAKTYPE 列挙体からのものです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetlongvalue"></a><a name="setlongvalue"></a> CMFCFilterChunkValueImpl:: SetLongValue

プロパティをキーによって LONG に設定します。

```
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,
    long lVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>パラメーター

*pkey*<br/>
プロパティキーを指定します。

*lVal*<br/>
設定するチャンク値を指定します。

*chunkType*<br/>
フラグは、このチャンクにテキスト型または値型のプロパティが含まれているかどうかを示します。 フラグの値は、CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語およびサブ言語。 チャンクロケールは、テキストの適切な単語区切りを実行するためにドキュメントインデクサーによって使用されます。 チャンクがテキスト型でも、データ型 VT_LPWSTR、VT_LPSTR、または VT_BSTR を持つ値型でもない場合、このフィールドは無視されます。

*cwcLenSource*<br/>
現在のチャンクの派生元であるソーステキストの長さ (文字数)。 0の値は、ソーステキストと派生テキストの文字単位の対応を示します。 0以外の値は、そのような直接の対応が存在しないことを意味します。

*cwcStartSource*<br/>
ソースチャンクの派生チャンクのソーステキストの開始位置を示すオフセット。

*chunkBreakType*<br/>
前のチャンクと現在のチャンクを区切る中断の種類。 値は CHUNK_BREAKTYPE 列挙体からのものです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetsystemtimevalue"></a><a name="setsystemtimevalue"></a> CMFCFilterChunkValueImpl:: SetSystemTimeValue

キーによってプロパティを SystemTime に設定します。

```
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,
    const SYSTEMTIME& systemTime,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>パラメーター

*pkey*<br/>
プロパティキーを指定します。

*systemTime*<br/>
設定するチャンク値を指定します。

*chunkType*<br/>
フラグは、このチャンクにテキスト型または値型のプロパティが含まれているかどうかを示します。 フラグの値は、CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語およびサブ言語。 チャンクロケールは、テキストの適切な単語区切りを実行するためにドキュメントインデクサーによって使用されます。 チャンクがテキスト型でも、データ型 VT_LPWSTR、VT_LPSTR、または VT_BSTR を持つ値型でもない場合、このフィールドは無視されます。

*cwcLenSource*<br/>
現在のチャンクの派生元であるソーステキストの長さ (文字数)。 0の値は、ソーステキストと派生テキストの文字単位の対応を示します。 0以外の値は、そのような直接の対応が存在しないことを意味します。

*cwcStartSource*<br/>
ソースチャンクの派生チャンクのソーステキストの開始位置を示すオフセット。

*chunkBreakType*<br/>
前のチャンクと現在のチャンクを区切る中断の種類。 値は CHUNK_BREAKTYPE 列挙体からのものです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsettextvalue"></a><a name="settextvalue"></a> CMFCFilterChunkValueImpl:: SetTextValue

キーによってプロパティを Unicode 文字列に設定します。

```
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,
    LPCTSTR pszValue,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>パラメーター

*pkey*<br/>
プロパティキーを指定します。

*pszValue*<br/>
設定するチャンク値を指定します。

*chunkType*<br/>
フラグは、このチャンクにテキスト型または値型のプロパティが含まれているかどうかを示します。 フラグの値は、CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語およびサブ言語。 チャンクロケールは、テキストの適切な単語区切りを実行するためにドキュメントインデクサーによって使用されます。 チャンクがテキスト型でも、データ型 VT_LPWSTR、VT_LPSTR、または VT_BSTR を持つ値型でもない場合、このフィールドは無視されます。

*cwcLenSource*<br/>
現在のチャンクの派生元であるソーステキストの長さ (文字数)。 0の値は、ソーステキストと派生テキストの文字単位の対応を示します。 0以外の値は、そのような直接の対応が存在しないことを意味します。

*cwcStartSource*<br/>
ソースチャンクの派生チャンクのソーステキストの開始位置を示すオフセット。

*chunkBreakType*<br/>
前のチャンクと現在のチャンクを区切る中断の種類。 値は CHUNK_BREAKTYPE 列挙体からのものです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーコード。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
