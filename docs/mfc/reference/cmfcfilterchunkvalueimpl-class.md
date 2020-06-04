---
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
ms.openlocfilehash: c89d41f7db43d9504bfc22cbf35a59fcceb511e2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752364"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl クラス

これは、チャンクとプロパティ値のペアロジックの両方を簡素化するクラスです。

## <a name="syntax"></a>構文

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を指定します。](#_dtorcmfcfilterchunkvalueimpl)|オブジェクトを破棄します。|
|[を指定します。](#cmfcfilterchunkvalueimpl)|オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を返す](#clear)|チャンク値をクリアします。|
|[を指定します。](#copychunk)|チャンクの特性を記述する構造体にこのチャンクをコピーします。|
|[を返す](#copyfrom)|このチャンク値を他の値から初期化します。|
|[を返す](#getchunkguid)|チャンク GUID を取得します。|
|[を指定します。](#getchunkpid)|チャンク PID (プロパティ ID) を取得します。|
|[を返す](#getchunktype)|チャンクの種類を取得します。|
|[を返す](#getstring)|文字列値を取得します。|
|[を返す](#getvalue)|割り当てられた propvariant として値を取得します。|
|[を指定します。](#getvaluenoalloc)|割り当てられていない (内部値) 値を返します。|
|[を指定します。](#isvalid)|このプロパティ値が有効かどうかをチェックします。|
|[を指定します。](#setboolvalue)|オーバーロードされます。 プロパティをキーでブール値に設定します。|
|[を指定します。](#setdwordvalue)|プロパティをキーごとに DWORD に設定します。|
|[を指定します。](#setfiletimevalue)|キーによってプロパティをファイル時間に設定します。|
|[を指定します。](#setint64value)|プロパティをキーによって int64 に設定します。|
|[を指定します。](#setintvalue)|プロパティを int に設定します。|
|[を指定します。](#setlongvalue)|プロパティをキーで LONG に設定します。|
|[を設定します。](#setsystemtimevalue)|プロパティをキーごとに設定します。|
|[を指定します。](#settextvalue)|プロパティをキーで Unicode 文字列に設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[を指定します。](#setchunk)|チャンクの共通プロパティを設定するヘルパー関数。|

## <a name="remarks"></a>解説

使用するには、適切な種類の CMFCFilter チャンク値Impl クラスを作成するだけです。

例:

チャンクをチャンクします。

hr = チャンク。値を設定します(PKEY_IsAttachment、真)。

or

hr = チャンク。ファイルタイム値(PKEY_ItemDate、ftLastModified)。

## <a name="inheritance-hierarchy"></a>継承階層

`ATL::IFilterChunkValue`

[を指定します。](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cmfcfilterchunkvalueimplclear"></a><a name="clear"></a>を返す

チャンク値をクリアします。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="cmfcfilterchunkvalueimpl"></a>を指定します。

オブジェクトを構築します。

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="_dtorcmfcfilterchunkvalueimpl"></a>を指定します。

オブジェクトを破棄します。

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplcopychunk"></a><a name="copychunk"></a>を指定します。

チャンクの特性を記述する構造体にこのチャンクをコピーします。

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>パラメーター

*チャンク*<br/>
チャンクの特性を記述する宛先値へのポインター。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplcopyfrom"></a><a name="copyfrom"></a>を返す

このチャンク値を他の値から初期化します。

```cpp
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>パラメーター

*pValue*<br/>
コピー元の値を指定します。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetchunkguid"></a><a name="getchunkguid"></a>を返す

チャンク GUID を取得します。

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>戻り値

チャンクを識別する GUID への参照。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetchunkpid"></a><a name="getchunkpid"></a>を指定します。

チャンク PID (プロパティ ID) を取得します。

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>戻り値

プロパティ ID を含む DWORD 値。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetchunktype"></a><a name="getchunktype"></a>を返す

チャンクの種類を取得します。

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>戻り値

現在のチャンクがテキスト型プロパティか値型プロパティかを指定する CHUNKSTATE 列挙値。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetstring"></a><a name="getstring"></a>を返す

文字列値を取得します。

```
CString &GetString();
```

### <a name="return-value"></a>戻り値

チャンク値を含む文字列。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetvalue"></a><a name="getvalue"></a>を返す

割り当てられた propvariant として値を取得します。

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>パラメーター

*を変更します。*<br/>
関数が返されるときに、このパラメーターにはチャンク値が含まれます。

### <a name="return-value"></a>戻り値

propVariant が正常に割り当てられ、チャンク値が*ppPropVariant*に正常にコピーされた場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplgetvaluenoalloc"></a><a name="getvaluenoalloc"></a>を指定します。

割り当てられていない (内部値) 値を返します。

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>戻り値

現在のチャンク値を返します。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplisvalid"></a><a name="isvalid"></a>を指定します。

このプロパティ値が有効かどうかをチェックします。

```
BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

現在のチャンク値が有効な場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetboolvalue"></a><a name="setboolvalue"></a>を指定します。

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
プロパティ キーを指定します。

*bVal*<br/>
設定するチャンク値を指定します。

*チャンクタイプ*<br/>
フラグは、このチャンクにテキスト型または値型プロパティが含まれているかどうかを示します。 フラグ値は CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語とサブ言語。 チャンク ロケールは、テキストの適切な単語区切り処理を実行するために、ドキュメント インデクサーによって使用されます。 チャンクがテキスト型でも、データ型VT_LPWSTR値型でも、VT_LPSTR、またはVT_BSTRの場合、このフィールドは無視されます。

*cwcLen ソース*<br/>
現在のチャンクの派生元となるソース テキストの長さ (文字数)。 ゼロの値は、ソース テキストと派生テキストの文字ごとの対応を示します。 ゼロ以外の値は、そのような直接対応が存在することを意味します。

*ソースを開始します。*<br/>
派生チャンクのソース テキストがソース チャンクで開始するオフセット。

*チャンクブレークタイプ*<br/>
前のチャンクと現在のチャンクを分離するブレークのタイプ。 値は、CHUNK_BREAKTYPE列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetchunk"></a><a name="setchunk"></a>を指定します。

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
プロパティ キーを指定します。

*チャンクタイプ*<br/>
フラグは、このチャンクにテキスト型または値型プロパティが含まれているかどうかを示します。 フラグ値は CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語とサブ言語。 チャンク ロケールは、テキストの適切な単語区切り処理を実行するために、ドキュメント インデクサーによって使用されます。 チャンクがテキスト型でも、データ型VT_LPWSTR値型でも、VT_LPSTR、またはVT_BSTRの場合、このフィールドは無視されます。

*cwcLen ソース*<br/>
現在のチャンクの派生元となるソース テキストの長さ (文字数)。 ゼロの値は、ソース テキストと派生テキストの文字ごとの対応を示します。 ゼロ以外の値は、そのような直接対応が存在することを意味します。

*ソースを開始します。*<br/>
派生チャンクのソース テキストがソース チャンクで開始するオフセット。

*チャンクブレークタイプ*<br/>
前のチャンクと現在のチャンクを分離するブレークのタイプ。 値は、CHUNK_BREAKTYPE列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetdwordvalue"></a><a name="setdwordvalue"></a>を指定します。

プロパティをキーごとに DWORD に設定します。

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
プロパティ キーを指定します。

*ドヴァル*<br/>
設定するチャンク値を指定します。

*チャンクタイプ*<br/>
フラグは、このチャンクにテキスト型または値型プロパティが含まれているかどうかを示します。 フラグ値は CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語とサブ言語。 チャンク ロケールは、テキストの適切な単語区切り処理を実行するために、ドキュメント インデクサーによって使用されます。 チャンクがテキスト型でも、データ型VT_LPWSTR値型でも、VT_LPSTR、またはVT_BSTRの場合、このフィールドは無視されます。

*cwcLen ソース*<br/>
現在のチャンクの派生元となるソース テキストの長さ (文字数)。 ゼロの値は、ソース テキストと派生テキストの文字ごとの対応を示します。 ゼロ以外の値は、そのような直接対応が存在することを意味します。

*ソースを開始します。*<br/>
派生チャンクのソース テキストがソース チャンクで開始するオフセット。

*チャンクブレークタイプ*<br/>
前のチャンクと現在のチャンクを分離するブレークのタイプ。 値は、CHUNK_BREAKTYPE列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetfiletimevalue"></a><a name="setfiletimevalue"></a>を指定します。

キーでプロパティをファイル時間に設定します。

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
プロパティ キーを指定します。

*dtVal*<br/>
設定するチャンク値を指定します。

*チャンクタイプ*<br/>
フラグは、このチャンクにテキスト型または値型プロパティが含まれているかどうかを示します。 フラグ値は CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語とサブ言語。 チャンク ロケールは、テキストの適切な単語区切り処理を実行するために、ドキュメント インデクサーによって使用されます。 チャンクがテキスト型でも、データ型VT_LPWSTR値型でも、VT_LPSTR、またはVT_BSTRの場合、このフィールドは無視されます。

*cwcLen ソース*<br/>
現在のチャンクの派生元となるソース テキストの長さ (文字数)。 ゼロの値は、ソース テキストと派生テキストの文字ごとの対応を示します。 ゼロ以外の値は、そのような直接対応が存在することを意味します。

*ソースを開始します。*<br/>
派生チャンクのソース テキストがソース チャンクで開始するオフセット。

*チャンクブレークタイプ*<br/>
前のチャンクと現在のチャンクを分離するブレークのタイプ。 値は、CHUNK_BREAKTYPE列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetint64value"></a><a name="setint64value"></a>を指定します。

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
プロパティ キーを指定します。

*nVal*<br/>
設定するチャンク値を指定します。

*チャンクタイプ*<br/>
フラグは、このチャンクにテキスト型または値型プロパティが含まれているかどうかを示します。 フラグ値は CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語とサブ言語。 チャンク ロケールは、テキストの適切な単語区切り処理を実行するために、ドキュメント インデクサーによって使用されます。 チャンクがテキスト型でも、データ型VT_LPWSTR値型でも、VT_LPSTR、またはVT_BSTRの場合、このフィールドは無視されます。

*cwcLen ソース*<br/>
現在のチャンクの派生元となるソース テキストの長さ (文字数)。 ゼロの値は、ソース テキストと派生テキストの文字ごとの対応を示します。 ゼロ以外の値は、そのような直接対応が存在することを意味します。

*ソースを開始します。*<br/>
派生チャンクのソース テキストがソース チャンクで開始するオフセット。

*チャンクブレークタイプ*<br/>
前のチャンクと現在のチャンクを分離するブレークのタイプ。 値は、CHUNK_BREAKTYPE列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetintvalue"></a><a name="setintvalue"></a>を指定します。

プロパティを int に設定します。

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
プロパティ キーを指定します。

*nVal*<br/>
設定するチャンク値を指定します。

*チャンクタイプ*<br/>
フラグは、このチャンクにテキスト型または値型プロパティが含まれているかどうかを示します。 フラグ値は CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語とサブ言語。 チャンク ロケールは、テキストの適切な単語区切り処理を実行するために、ドキュメント インデクサーによって使用されます。 チャンクがテキスト型でも、データ型VT_LPWSTR値型でも、VT_LPSTR、またはVT_BSTRの場合、このフィールドは無視されます。

*cwcLen ソース*<br/>
現在のチャンクの派生元となるソース テキストの長さ (文字数)。 ゼロの値は、ソース テキストと派生テキストの文字ごとの対応を示します。 ゼロ以外の値は、そのような直接対応が存在することを意味します。

*ソースを開始します。*<br/>
派生チャンクのソース テキストがソース チャンクで開始するオフセット。

*チャンクブレークタイプ*<br/>
前のチャンクと現在のチャンクを分離するブレークのタイプ。 値は、CHUNK_BREAKTYPE列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetlongvalue"></a><a name="setlongvalue"></a>を指定します。

プロパティをキーで LONG に設定します。

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
プロパティ キーを指定します。

*lヴァル*<br/>
設定するチャンク値を指定します。

*チャンクタイプ*<br/>
フラグは、このチャンクにテキスト型または値型プロパティが含まれているかどうかを示します。 フラグ値は CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語とサブ言語。 チャンク ロケールは、テキストの適切な単語区切り処理を実行するために、ドキュメント インデクサーによって使用されます。 チャンクがテキスト型でも、データ型VT_LPWSTR値型でも、VT_LPSTR、またはVT_BSTRの場合、このフィールドは無視されます。

*cwcLen ソース*<br/>
現在のチャンクの派生元となるソース テキストの長さ (文字数)。 ゼロの値は、ソース テキストと派生テキストの文字ごとの対応を示します。 ゼロ以外の値は、そのような直接対応が存在することを意味します。

*ソースを開始します。*<br/>
派生チャンクのソース テキストがソース チャンクで開始するオフセット。

*チャンクブレークタイプ*<br/>
前のチャンクと現在のチャンクを分離するブレークのタイプ。 値は、CHUNK_BREAKTYPE列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsetsystemtimevalue"></a><a name="setsystemtimevalue"></a>を設定します。

プロパティをキーごとに設定します。

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
プロパティ キーを指定します。

*システム時刻*<br/>
設定するチャンク値を指定します。

*チャンクタイプ*<br/>
フラグは、このチャンクにテキスト型または値型プロパティが含まれているかどうかを示します。 フラグ値は CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語とサブ言語。 チャンク ロケールは、テキストの適切な単語区切り処理を実行するために、ドキュメント インデクサーによって使用されます。 チャンクがテキスト型でも、データ型VT_LPWSTR値型でも、VT_LPSTR、またはVT_BSTRの場合、このフィールドは無視されます。

*cwcLen ソース*<br/>
現在のチャンクの派生元となるソース テキストの長さ (文字数)。 ゼロの値は、ソース テキストと派生テキストの文字ごとの対応を示します。 ゼロ以外の値は、そのような直接対応が存在することを意味します。

*ソースを開始します。*<br/>
派生チャンクのソース テキストがソース チャンクで開始するオフセット。

*チャンクブレークタイプ*<br/>
前のチャンクと現在のチャンクを分離するブレークのタイプ。 値は、CHUNK_BREAKTYPE列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cmfcfilterchunkvalueimplsettextvalue"></a><a name="settextvalue"></a>を指定します。

プロパティをキーで Unicode 文字列に設定します。

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
プロパティ キーを指定します。

*値*<br/>
設定するチャンク値を指定します。

*チャンクタイプ*<br/>
フラグは、このチャンクにテキスト型または値型プロパティが含まれているかどうかを示します。 フラグ値は CHUNKSTATE 列挙体から取得されます。

*locale*<br/>
テキストのチャンクに関連付けられている言語とサブ言語。 チャンク ロケールは、テキストの適切な単語区切り処理を実行するために、ドキュメント インデクサーによって使用されます。 チャンクがテキスト型でも、データ型VT_LPWSTR値型でも、VT_LPSTR、またはVT_BSTRの場合、このフィールドは無視されます。

*cwcLen ソース*<br/>
現在のチャンクの派生元となるソース テキストの長さ (文字数)。 ゼロの値は、ソース テキストと派生テキストの文字ごとの対応を示します。 ゼロ以外の値は、そのような直接対応が存在することを意味します。

*ソースを開始します。*<br/>
派生チャンクのソース テキストがソース チャンクで開始するオフセット。

*チャンクブレークタイプ*<br/>
前のチャンクと現在のチャンクを分離するブレークのタイプ。 値は、CHUNK_BREAKTYPE列挙体から取得されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
