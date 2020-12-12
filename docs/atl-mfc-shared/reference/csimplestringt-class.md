---
description: '詳細情報: CSimpleStringT クラス'
title: CSimpleStringT クラス
ms.date: 10/18/2018
f1_keywords:
- CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::PCXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::PXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::Append
- ATLSIMPSTR/ATL::CSimpleStringT::AppendChar
- ATLSIMPSTR/ATL::CSimpleStringT::CopyChars
- ATLSIMPSTR/ATL::CSimpleStringT::CopyCharsOverlapped
- ATLSIMPSTR/ATL::CSimpleStringT::Empty
- ATLSIMPSTR/ATL::CSimpleStringT::FreeExtra
- ATLSIMPSTR/ATL::CSimpleStringT::GetAllocLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetAt
- ATLSIMPSTR/ATL::CSimpleStringT::GetBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::GetBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetManager
- ATLSIMPSTR/ATL::CSimpleStringT::GetString
- ATLSIMPSTR/ATL::CSimpleStringT::IsEmpty
- ATLSIMPSTR/ATL::CSimpleStringT::LockBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::Preallocate
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::SetAt
- ATLSIMPSTR/ATL::CSimpleStringT::SetManager
- ATLSIMPSTR/ATL::CSimpleStringT::SetString
- ATLSIMPSTR/ATL::CSimpleStringT::StringLength
- ATLSIMPSTR/ATL::CSimpleStringT::Truncate
- ATLSIMPSTR/ATL::CSimpleStringT::UnlockBuffer
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
ms.openlocfilehash: fd2ddf79e94827ad42411eeec71dde2fce28bd8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166656"
---
# <a name="csimplestringt-class"></a>CSimpleStringT クラス

このクラスは、 `CSimpleStringT` オブジェクトを表します。

## <a name="syntax"></a>構文

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>パラメーター

*BaseType*<br/>
文字列クラスの文字型。 以下のいずれかを指定できます。

- **`char`** (ANSI 文字列の場合)。

- **`wchar_t`** (Unicode 文字列の場合)。

- TCHAR (ANSI 文字列と Unicode 文字列の両方)。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CSimpleStringT::P CXSTR](#pcxstr)|定数文字列へのポインター。|
|[CSimpleStringT::P XSTR](#pxstr)|文字列へのポインター。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSimpleStringT::CSimpleStringT](#ctor)|`CSimpleStringT`さまざまな方法でオブジェクトを構築します。|
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleStringT:: Append](#append)|オブジェクトを `CSimpleStringT` 既存のオブジェクトに追加 `CSimpleStringT` します。|
|[CSimpleStringT:: AppendChar](#appendchar)|既存のオブジェクトに文字を追加 `CSimpleStringT` します。|
|[CSimpleStringT:: CopyChars](#copychars)|1つまたは複数の文字を別の文字列にコピーします。|
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|バッファーが重なる別の文字列に1つまたは複数の文字をコピーします。|
|[CSimpleStringT:: Empty](#empty)|文字列の長さを強制的に0にします。|
|[CSimpleStringT:: FreeExtra](#freeextra)|文字列オブジェクトによって以前に割り当てられた余分なメモリを解放します。|
|[CSimpleStringT::GetAllocLength](#getalloclength)|オブジェクトの割り当てられた長さを取得し `CSimpleStringT` ます。|
|[CSimpleStringT:: GetAt](#getat)|指定された位置にある文字を返します。|
|[CSimpleStringT:: GetBuffer](#getbuffer)|内の文字へのポインターを返し `CSimpleStringT` ます。|
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|内の文字へのポインターを返し `CSimpleStringT` ます。指定された長さに切り捨てます。|
|[CSimpleStringT:: GetLength](#getlength)|オブジェクト内の文字数を返し `CSimpleStringT` ます。|
|[CSimpleStringT:: GetManager](#getmanager)|オブジェクトのメモリマネージャーを取得し `CSimpleStringT` ます。|
|[CSimpleStringT:: GetString](#getstring)|文字列を取得します。|
|[CSimpleStringT:: IsEmpty](#isempty)|`CSimpleStringT`オブジェクトに文字が含まれていないかどうかをテストします。|
|[CSimpleStringT:: LockBuffer](#lockbuffer)|参照カウントを無効にし、バッファー内の文字列を保護します。|
|[CSimpleStringT::P 再割り当て](#preallocate)|文字バッファーに特定の量のメモリを割り当てます。|
|[CSimpleStringT:: ReleaseBuffer](#releasebuffer)|によって返されたバッファーの制御を解放 `GetBuffer` します。|
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|によって返されたバッファーの制御を解放 `GetBuffer` します。|
|[CSimpleStringT:: SetAt](#setat)|指定された位置に文字を設定します。|
|[CSimpleStringT:: SetManager](#setmanager)|オブジェクトのメモリマネージャーを設定 `CSimpleStringT` します。|
|[CSimpleStringT:: SetString](#setstring)|オブジェクトの文字列を設定 `CSimpleStringT` します。|
|[CSimpleStringT:: StringLength](#stringlength)|指定された文字列内の文字数を返します。|
|[CSimpleStringT:: Truncate](#truncate)|文字列を指定された長さに切り捨てます。|
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|参照カウントを有効にし、バッファー内の文字列を解放します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CSimpleStringT:: operator PCXSTR](#operator_pcxstr)|`CSimpleStringT`C スタイルの文字列としてオブジェクトに格納されている文字に直接アクセスします。|
|[CSimpleStringT::operator\[\]](#operator_at)|指定された位置にある文字を返します (の演算子の代入) `GetAt` 。|
|[CSimpleStringT:: operator + =](#operator_add_eq)|新しい文字列を既存の文字列の末尾に連結します。|
|[CSimpleStringT:: operator =](#operator_eq)|オブジェクトに新しい値を割り当て `CSimpleStringT` ます。|

### <a name="remarks"></a>解説

`CSimpleStringT` は、Visual C++ によってサポートされるさまざまな文字列クラスの基本クラスです。 文字列オブジェクトと基本的なバッファー操作のメモリ管理に対する最小限のサポートが提供されます。 より高度な文字列オブジェクトについては、「 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)」を参照してください。

### <a name="requirements"></a>要件

**ヘッダー:** atl. h

## <a name="csimplestringtappend"></a><a name="append"></a> CSimpleStringT:: Append

オブジェクトを `CSimpleStringT` 既存のオブジェクトに追加 `CSimpleStringT` します。

### <a name="syntax"></a>構文

```cpp
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>パラメーター

*strSrc*<br/>
`CSimpleStringT`追加されるオブジェクト。

*pszSrc*<br/>
追加される文字を格納している文字列へのポインター。

*nLength*<br/>
追加する文字数。

### <a name="remarks"></a>解説

既存の `CSimpleStringT` オブジェクトを別のオブジェクトに追加するには、このメソッドを呼び出し `CSimpleStringT` ます。

### <a name="example"></a>例

次の例は、`CSimpleStringT::Append` の使い方を示しています。

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

## <a name="csimplestringtappendchar"></a><a name="appendchar"></a> CSimpleStringT:: AppendChar

既存のオブジェクトに文字を追加 `CSimpleStringT` します。

### <a name="syntax"></a>構文

```cpp
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>パラメーター

*ハーフ*<br/>
追加される文字

### <a name="remarks"></a>解説

この関数を呼び出して、指定した文字を既存のオブジェクトの末尾に追加し `CSimpleStringT` ます。

## <a name="csimplestringtcopychars"></a><a name="copychars"></a> CSimpleStringT:: CopyChars

1つまたは複数の文字をオブジェクトにコピー `CSimpleStringT` します。

### <a name="syntax"></a>構文

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>パラメーター

*pchDest*<br/>
文字列へのポインター。

*pchSrc*<br/>
コピーされる文字を格納している文字列へのポインター。

*nChars*<br/>
コピーする *Pchsrc* 文字の数。

### <a name="remarks"></a>解説

*Pchsrc* から *pchsrc* 文字列に文字をコピーするには、このメソッドを呼び出します。

### <a name="example"></a>例

次の例は、`CSimpleStringT::CopyChars` の使い方を示しています。

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

## <a name="csimplestringtcopycharsoverlapped"></a><a name="copycharsoverlapped"></a> CSimpleStringT::CopyCharsOverlapped

1つまたは複数の文字をオブジェクトにコピー `CSimpleStringT` します。

### <a name="syntax"></a>構文

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>パラメーター

*pchDest*<br/>
文字列へのポインター。

*pchSrc*<br/>
コピーされる文字を格納している文字列へのポインター。

*nChars*<br/>
コピーする *Pchsrc* 文字の数。

### <a name="remarks"></a>解説

*Pchsrc* から *pchsrc* 文字列に文字をコピーするには、このメソッドを呼び出します。 とは異なり `CopyChars` 、は、 `CopyCharsOverlapped` 重複している可能性のある文字バッファーからコピーするための安全なメソッドを提供します。

### <a name="example"></a>例

[CSimpleStringT:: CopyChars](#copychars)の例、またはのソースコード `CSimpleStringT::SetString` (atlにある) を参照してください。

## <a name="csimplestringtcsimplestringt"></a><a name="ctor"></a> CSimpleStringT::CSimpleStringT

`CSimpleStringT` オブジェクトを構築します。

### <a name="syntax"></a>構文

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>パラメーター

*strSrc*<br/>
`CSimpleStringT`このオブジェクトにコピーされる既存のオブジェクト `CSimpleStringT` 。

*pchSrc*<br/>
長さが *nlength* の文字の配列へのポインターであり、null で終了していません。

*pszSrc*<br/>
このオブジェクトにコピーされる null で終わる文字列 `CSimpleStringT` 。

*nLength*<br/>
内の文字数のカウント `pch` 。

*pStringMgr*<br/>
オブジェクトのメモリマネージャーへのポインター `CSimpleStringT` 。 とのメモリ管理の詳細について `IAtlStringMgr` `CSimpleStringT` は、「 [メモリ管理と CStringT](../memory-management-with-cstringt.md)」を参照してください。

### <a name="remarks"></a>解説

新しい `CSimpleStringT` オブジェクトを構築します。 コンストラクターは、割り当てられた新しいストレージに入力データをコピーするので、メモリ例外が発生する可能性があります。

### <a name="example"></a>例

ATL を使用したの使用例を次に示し `CSimpleStringT::CSimpleStringT` **`typedef`** `CSimpleString` ます。 `CSimpleString` は、広く使用されているクラステンプレートの特殊化です `CSimpleStringT` 。

```cpp
CSimpleString s1(pMgr);
// Empty string
CSimpleString s2(_T("cat"), pMgr);
// From a C string literal

CSimpleString s3(s2);
// Copy constructor
CSimpleString s4(s2 + _T(" ") + s3);

// From a string expression
CSimpleString s5(_T("xxxxxx"), 6, pMgr);
// s5 = "xxxxxx"
```

## <a name="csimplestringtempty"></a><a name="empty"></a> CSimpleStringT:: Empty

この `CSimpleStringT` オブジェクトを空の文字列にし、必要に応じてメモリを解放します。

### <a name="syntax"></a>構文

```cpp
void Empty() throw();
```

### <a name="remarks"></a>解説

詳細については、「 [文字列: CString 例外のクリーンアップ](../cstring-exception-cleanup.md)」を参照してください。

### <a name="example"></a>例

次の例は、`CSimpleStringT::Empty` の使い方を示しています。

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtfreeextra"></a><a name="freeextra"></a> CSimpleStringT:: FreeExtra

以前に文字列によって割り当てられた余分なメモリを解放しますが、不要になりました。

### <a name="syntax"></a>構文

```cpp
void FreeExtra();
```

### <a name="remarks"></a>解説

これにより、string オブジェクトによって消費されるメモリのオーバーヘッドが軽減されます。 メソッドは、 [GetLength](#getlength)によって返される正確な長さにバッファーを再割り当てします。

### <a name="example"></a>例

```cpp
CAtlString basestr;
IAtlStringMgr* pMgr;

pMgr= basestr.GetManager();
ASSERT(pMgr != NULL);

// Create a CSimpleString with 28 characters
CSimpleString str(_T("Many sports are fun to play."), 28, pMgr);
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// Assigning a smaller string won't cause CSimpleString to free its
// memory, because it assumes the string will grow again anyway.
str = _T("Soccer is best!");
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// This call forces CSimpleString to release the extra
// memory it doesn't need.
str.FreeExtra();
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());
```

### <a name="remarks"></a>解説

この例の出力は次のとおりです。

```Output
Alloc length is 1031, String length is 1024
Alloc length is 1031, String length is 15
Alloc length is 15, String length is 15
```

## <a name="csimplestringtgetalloclength"></a><a name="getalloclength"></a> CSimpleStringT::GetAllocLength

オブジェクトの割り当てられた長さを取得し `CSimpleStringT` ます。

### <a name="syntax"></a>構文

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトに割り当てられた文字数。

### <a name="remarks"></a>解説

このオブジェクトに割り当てられた文字数を確認するには、このメソッドを呼び出し `CSimpleStringT` ます。 この関数を呼び出す例については、「 [Freeextra](#freeextra) 」を参照してください。

## <a name="csimplestringtgetat"></a><a name="getat"></a> CSimpleStringT:: GetAt

オブジェクトから1つの文字を返し `CSimpleStringT` ます。

### <a name="syntax"></a>構文

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>パラメーター

*iChar*<br/>
オブジェクト内の文字の0から始まるインデックス `CSimpleStringT` 。 *IChar* パラメーターには、0以上、 [GetLength](#getlength)によって返される値より小さい値を指定する必要があります。 それ以外の場合、 `GetAt` は例外を生成します。

### <a name="return-value"></a>戻り値

`XCHAR`文字列内の指定した位置にある文字を格納している。

### <a name="remarks"></a>解説

*IChar* によって指定された1つの文字を返すには、このメソッドを呼び出します。 オーバーロードされた添字 (**[]**) 演算子は、の便利なエイリアスです `GetAt` 。 Null 終端文字は、を使用して例外を生成することなく、アドレス指定 `GetAt` できます。 ただし、によってカウントされることはなく、 `GetLength` 返される値は0です。

### <a name="example"></a>例

を使用する方法を次の例に示し `CSimpleStringT::GetAt` ます。

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

## <a name="csimplestringtgetbuffer"></a><a name="getbuffer"></a> CSimpleStringT:: GetBuffer

オブジェクトの内部文字バッファーへのポインターを返し `CSimpleStringT` ます。

### <a name="syntax"></a>構文

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>パラメーター

*nMinBufferLength*<br/>
文字バッファーが保持できる最小文字数。 この値には、null 終端文字のスペースは含まれません。

*Nminbufferlength* が現在のバッファーの長さよりも大きい場合、は `GetBuffer` 現在のバッファーを破棄し、要求されたサイズのバッファーで置き換え、オブジェクト参照カウントを0にリセットします。 このバッファーに対して既に [Lockbuffer](#lockbuffer) を呼び出している場合、バッファーロックは失われます。

### <a name="return-value"></a>戻り値

`PXSTR`オブジェクトの (null で終わる) 文字バッファーへのポインター。

### <a name="remarks"></a>解説

オブジェクトのバッファーの内容を返すには、このメソッドを呼び出し `CSimpleStringT` ます。 返されるは `PXSTR` 定数ではないため、内容を直接変更でき `CSimpleStringT` ます。

によって返されたポインターを使用して文字列の内容を変更する場合は `GetBuffer` 、他のメンバーメソッドを使用する前に [releasebuffer](#releasebuffer) を呼び出す必要があり `CSimpleStringT` ます。

によって返されるアドレスは、 `GetBuffer` を呼び出した後に有効でない可能性があります。これは、追加の操作によってバッファーが再 `ReleaseBuffer` `CSimpleStringT` 割り当てされる可能性があるため `CSimpleStringT` です。 の長さを変更しない場合、バッファーは再割り当てされません `CSimpleStringT` 。

バッファーメモリは、オブジェクトが破棄されると自動的に解放され `CSimpleStringT` ます。

文字列の長さを自分で追跡する場合は、終端の null 文字を追加しないでください。 ただし、を使用してバッファーを解放する場合は、最終的な文字列長を指定する必要があり `ReleaseBuffer` ます。 終端の null 文字を追加する場合は、長さに-1 (既定値) を渡す必要があります。 `ReleaseBuffer` は、バッファーの長さを決定します。

要求を満たすのに十分なメモリがない場合 `GetBuffer` 、このメソッドは CMemoryException * をスローします。

### <a name="example"></a>例

```cpp
CSimpleString s(_T("abcd"), pMgr);
LPTSTR pBuffer = s.GetBuffer(10);
int sizeOfBuffer = s.GetAllocLength();

// Directly access CSimpleString buffer
_tcscpy_s(pBuffer, sizeOfBuffer, _T("Hello"));
ASSERT(_tcscmp(s, _T("Hello")) == 0);
s.ReleaseBuffer();
```

## <a name="csimplestringtgetbuffersetlength"></a><a name="getbuffersetlength"></a> CSimpleStringT::GetBufferSetLength

オブジェクトの内部文字バッファーへのポインターを返し `CSimpleStringT` ます。 *nlength* で指定した長さと正確に一致するように、必要に応じてその長さを切り捨てたり、長くしたりします。

### <a name="syntax"></a>構文

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>パラメーター

*nLength*<br/>
文字バッファーの正確なサイズ `CSimpleStringT` (文字数)。

### <a name="return-value"></a>戻り値

`PXSTR`オブジェクトの (null で終わる) 文字バッファーへのポインター。

### <a name="remarks"></a>解説

オブジェクトの内部バッファーの指定された長さを取得するには、このメソッドを呼び出し `CSimpleStringT` ます。 返される `PXSTR` ポインターはではない **`const`** ため、内容を直接変更することができ `CSimpleStringT` ます。

[GetBufferSetLength](#getbuffersetlength)から返されたポインターを使用して文字列の内容を変更する場合は、を呼び出して、 `ReleaseBuffer` `CsimpleStringT` 他のメソッドを使用する前にの内部状態を更新し `CSimpleStringT` ます。

によって返されるアドレスは、 `GetBufferSetLength` を呼び出した後に有効でない可能性があります。これは、追加の操作によってバッファーが再 `ReleaseBuffer` `CSimpleStringT` 割り当てされる可能性があるため `CSimpleStringT` です。 の長さを変更しない場合、バッファーは再割り当てされません `CSimpleStringT` 。

バッファーメモリは、オブジェクトが破棄されると自動的に解放され `CSimpleStringT` ます。

文字列の長さを自分で追跡する場合は、終端の null 文字を追加しないでください。 を使用してバッファーを解放する場合は、最終的な文字列長を指定する必要があり `ReleaseBuffer` ます。 を呼び出したときに終端の null 文字を追加する場合は、の `ReleaseBuffer` 長さに-1 (既定値) を渡し、 `ReleaseBuffer` はバッファーに対してを実行して `ReleaseBuffer` `strlen` その長さを決定します。

参照カウントの詳細については、次の記事を参照してください。

- Windows SDK の[参照カウントによるオブジェクトの有効期間の管理](/windows/win32/com/managing-object-lifetimes-through-reference-counting)。

- Windows SDK での[参照カウントの実装](/windows/win32/com/implementing-reference-counting)。

- Windows SDK の[参照カウントを管理するための規則](/windows/win32/com/rules-for-managing-reference-counts)。

### <a name="example"></a>例

次の例は、`CSimpleStringT::GetBufferSetLength` の使い方を示しています。

```cpp
CSimpleString str(pMgr);
LPTSTR pstr = str.GetBufferSetLength(3);
pstr[0] = _T('C');
pstr[1] = _T('u');
pstr[2] = _T('p');

// No need for trailing zero or call to ReleaseBuffer()
// because GetBufferSetLength() set it for us.

str += _T(" soccer is best!");
ASSERT(_tcscmp(str, _T("Cup soccer is best!")) == 0);
```

## <a name="csimplestringtgetlength"></a><a name="getlength"></a> CSimpleStringT:: GetLength

オブジェクト内の文字数を返し `CSimpleStringT` ます。

### <a name="syntax"></a>構文

```
int GetLength() const throw();
```

### <a name="return-value"></a>戻り値

文字列内の文字の数。

### <a name="remarks"></a>解説

オブジェクト内の文字数を返すには、このメソッドを呼び出します。 このカウントには null 終端文字は含まれません。

マルチバイト文字セット (MBCS) の場合、は `GetLength` 8 ビットの各文字をカウントします。つまり、1つのマルチバイト文字の先頭バイトと末尾バイトは2バイトとしてカウントされます。 この関数を呼び出す例については、「 [Freeextra](#freeextra) 」を参照してください。

## <a name="csimplestringtgetmanager"></a><a name="getmanager"></a> CSimpleStringT:: GetManager

オブジェクトのメモリマネージャーを取得し `CSimpleStringT` ます。

### <a name="syntax"></a>構文

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトのメモリマネージャーへのポインター `CSimpleStringT` 。

### <a name="remarks"></a>解説

オブジェクトによって使用されるメモリマネージャーを取得するには、このメソッドを呼び出し `CSimpleStringT` ます。 メモリマネージャーと文字列オブジェクトの詳細については、「 [メモリ管理と CStringT](../memory-management-with-cstringt.md)」を参照してください。

## <a name="csimplestringtgetstring"></a><a name="getstring"></a> CSimpleStringT:: GetString

文字列を取得します。

### <a name="syntax"></a>構文

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>戻り値

Null で終わる文字列へのポインター。

### <a name="remarks"></a>解説

オブジェクトに関連付けられた文字列を取得するには、このメソッドを呼び出し `CSimpleStringT` ます。

> [!NOTE]
> 返される `PCXSTR` ポインターはで、 **`const`** 内容を直接変更することはできません `CSimpleStringT` 。

### <a name="example"></a>例

次の例は、`CSimpleStringT::GetString` の使い方を示しています。

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

## <a name="csimplestringtisempty"></a><a name="isempty"></a> CSimpleStringT:: IsEmpty

オブジェクトの `CSimpleStringT` 空の条件をテストします。

### <a name="syntax"></a>構文

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの長さが0の場合は TRUE、それ以外の場合は FALSE を返し `CSimpleStringT` ます。

### <a name="remarks"></a>解説

このメソッドを呼び出して、オブジェクトに空の文字列が含まれているかどうかを確認します。

### <a name="example"></a>例

次の例は、`CSimpleStringT::IsEmpty` の使い方を示しています。

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtlockbuffer"></a><a name="lockbuffer"></a> CSimpleStringT:: LockBuffer

参照カウントを無効にし、バッファー内の文字列を保護します。

### <a name="syntax"></a>構文

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>戻り値

`CSimpleStringT`オブジェクトまたは null で終わる文字列へのポインター。

### <a name="remarks"></a>解説

オブジェクトのバッファーをロックするには、このメソッドを呼び出し `CSimpleStringT` ます。 を呼び出して `LockBuffer` 、文字列のコピーを作成します。参照カウントには-1 を指定します。 参照カウントの値が-1 の場合、バッファー内の文字列は "locked" 状態と見なされます。 ロック状態の場合、文字列は次の2つの方法で保護されます。

- その文字列がロックされた文字列に割り当てられている場合でも、他の文字列では、ロックされた文字列内のデータへの参照を取得することはできません。

- ロックされた文字列は、他の文字列がロックされた文字列にコピーされた場合でも、他の文字列を参照しません。

バッファー内の文字列をロックすることによって、バッファーに対する文字列の排他保持がそのまま維持されるようにすることができます。

を終了したら `LockBuffer` 、 [UnlockBuffer](#unlockbuffer) を呼び出して参照カウントを1にリセットします。

> [!NOTE]
> ロックされたバッファーで [GetBuffer](#getbuffer) を呼び出し、パラメーターを `GetBuffer` `nMinBufferLength` 現在のバッファーの長さよりも大きい値に設定すると、バッファーロックは失われます。 このような呼び出しは、 `GetBuffer` 現在のバッファーを破棄し、要求されたサイズのバッファーで置き換え、参照カウントを0にリセットします。

参照カウントの詳細については、次の記事を参照してください。

- Windows SDK での[参照カウントによるオブジェクトの有効期間の管理](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

- Windows SDK での[参照カウントの実装](/windows/win32/com/implementing-reference-counting)

- Windows SDK の[参照カウントを管理するための規則](/windows/win32/com/rules-for-managing-reference-counts)

### <a name="example"></a>例

次の例は、`CSimpleStringT::LockBuffer` の使い方を示しています。

```cpp
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```

## <a name="csimplestringtoperator"></a><a name="operator_at"></a> CSimpleStringT:: operator\[\]

文字配列の1つの文字にアクセスするには、この関数を呼び出します。

### <a name="syntax"></a>構文

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>パラメーター

*iChar*<br/>
文字列内の文字の0から始まるインデックス。

### <a name="remarks"></a>解説

オーバーロードされた添字 (**[]**) 演算子は、 *iChar* の0から始まるインデックスで指定された単一の文字を返します。 この演算子は、 [GetAt](#getat) メンバー関数に代わる便利な代替手段です。

> [!NOTE]
> 添字 (**[]**) 演算子を使用すると、内の文字の値を取得できますが、の文字の値を `CSimpleStringT` 変更することはできません `CSimpleStringT` 。

### <a name="example"></a>例

次の例は、`CSimpleStringT::operator []` の使い方を示しています。

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="csimplestringtoperator-"></a><a name="operator_at"></a> CSimpleStringT:: operator \[\]

文字配列の1つの文字にアクセスするには、この関数を呼び出します。

### <a name="syntax"></a>構文

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>パラメーター

*iChar*<br/>
文字列内の文字の0から始まるインデックス。

### <a name="remarks"></a>解説

オーバーロードされた添字 (**[]**) 演算子は、 *iChar* の0から始まるインデックスで指定された単一の文字を返します。 この演算子は、 [GetAt](#getat) メンバー関数に代わる便利な代替手段です。

> [!NOTE]
> 添字 (**[]**) 演算子を使用すると、内の文字の値を取得できますが、の文字の値を `CSimpleStringT` 変更することはできません `CSimpleStringT` 。

## <a name="csimplestringtoperator-"></a><a name="operator_add_eq"></a> CSimpleStringT:: operator + =

新しい文字列または文字を既存の文字列の末尾に結合します。

### <a name="syntax"></a>構文

```
CSimpleStringT& operator +=(PCXSTR pszSrc);
CSimpleStringT& operator +=(const CSimpleStringT& strSrc);
template<int t_nSize>
CSimpleStringT& operator+=(const CStaticString< XCHAR, t_nSize >& strSrc);
CSimpleStringT& operator +=(char ch);
CSimpleStringT& operator +=(unsigned char ch);
CSimpleStringT& operator +=(wchar_t ch);
```

#### <a name="parameters"></a>パラメーター

*pszSrc*<br/>
Null で終わる文字列へのポインター。

*strSrc*<br/>
既存のオブジェクトへのポインター `CSimpleStringT` 。

*ハーフ*<br/>
追加される文字。

### <a name="remarks"></a>解説

演算子は、別の `CSimpleStringT` オブジェクトまたは文字を受け入れます。 この連結演算子を使用すると、このオブジェクトに追加された文字に対して新しいストレージが割り当てられる可能性があるため、メモリ例外が発生する可能性があることに注意して `CSimpleStringT` ください。

### <a name="example"></a>例

次の例は、`CSimpleStringT::operator +=` の使い方を示しています。

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

## <a name="csimplestringtoperator-"></a><a name="operator_eq"></a> CSimpleStringT:: operator =

オブジェクトに新しい値を割り当て `CSimpleStringT` ます。

### <a name="syntax"></a>構文

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>パラメーター

*pszSrc*<br/>
Null で終わる文字列へのポインター。

*strSrc*<br/>
既存のオブジェクトへのポインター `CSimpleStringT` 。

### <a name="remarks"></a>解説

コピー先の文字列 (左側) が新しいデータを格納するのに十分な大きさである場合、新しいメモリ割り当ては実行されません。 新しいストレージは多くの場合、結果のオブジェクトを保持するために割り当てられるため、代入演算子を使用するたびにメモリ例外が発生する可能性があることに注意して `CSimpleStringT` ください。

### <a name="example"></a>例

次の例は、`CSimpleStringT::operator =` の使い方を示しています。

```cpp
CSimpleString s1(pMgr), s2(pMgr);
// Empty CSimpleStringT objects

s1 = _T("cat");
// s1 = "cat"
ASSERT(_tcscmp(s1, _T("cat")) == 0);

s2 = s1;               // s1 and s2 each = "cat"
ASSERT(_tcscmp(s2, _T("cat")) == 0);

s1 = _T("the ") + s1;
// Or expressions
ASSERT(_tcscmp(s1, _T("the cat")) == 0);

s1 = _T("x");
// Or just individual characters
ASSERT(_tcscmp(s1, _T("x")) == 0);
```

## <a name="csimplestringtoperator-pcxstr"></a><a name="operator_pcxstr"></a> CSimpleStringT:: operator PCXSTR

`CSimpleStringT`C スタイルの文字列としてオブジェクトに格納されている文字に直接アクセスします。

### <a name="syntax"></a>構文

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>戻り値

文字列のデータへの文字ポインター。

### <a name="remarks"></a>解説

文字はコピーされません。ポインターだけが返されます。 この演算子に注意してください。 `CString`文字ポインターを取得した後にオブジェクトを変更すると、ポインターを無効にするメモリの再割り当てが発生する可能性があります。

### <a name="example"></a>例

次の例は、`CSimpleStringT::operator PCXSTR` の使い方を示しています。

```cpp
// If the prototype of a function is known to the compiler,
// the PCXSTR cast operator may be invoked implicitly.

CSimpleString strSports(L"Soccer is Best!", pMgr);
WCHAR sz[1024];

wcscpy_s(sz, strSports);

// If the prototype isn't known or is a va_arg prototype,
// you must invoke the cast operator explicitly. For example,
// the va_arg part of a call to swprintf_s() needs the cast:

swprintf_s(sz, 1024, L"I think that %s!\n", (PCWSTR)strSports);

// While the format parameter is known to be an PCXSTR and
// therefore doesn't need the cast:

swprintf_s(sz, 1024, strSports);

// Note that some situations are ambiguous. This line will
// put the address of the strSports object to stdout:

wcout << strSports;

// while this line will put the content of the string out:

wcout << (PCWSTR)strSports;
```

## <a name="csimplestringtpcxstr"></a><a name="pcxstr"></a> CSimpleStringT::P CXSTR

定数文字列へのポインター。

### <a name="syntax"></a>構文

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

## <a name="csimplestringtpreallocate"></a><a name="preallocate"></a> CSimpleStringT::P 再割り当て

オブジェクトの特定の量のバイトを割り当て `CSimpleStringT` ます。

### <a name="syntax"></a>構文

```cpp
void Preallocate( int nLength);
```

#### <a name="parameters"></a>パラメーター

*nLength*<br/>
文字バッファーの正確なサイズ `CSimpleStringT` (文字数)。

### <a name="remarks"></a>解説

オブジェクトの特定のバッファーサイズを割り当てるには、このメソッドを呼び出し `CSimpleStringT` ます。

`CSimpleStringT` では、文字バッファーに領域を割り当てられない場合、STATUS_NO_MEMORY 例外が生成されます。 既定では、メモリ割り当ては WIN32 API 関数またはによって実行され `HeapAlloc` `HeapReAlloc` ます。

### <a name="example"></a>例

次の例は、`CSimpleStringT::Preallocate` の使い方を示しています。

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

## <a name="csimplestringtpxstr"></a><a name="pxstr"></a> CSimpleStringT::P XSTR

文字列へのポインター。

### <a name="syntax"></a>構文

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

## <a name="csimplestringtreleasebuffer"></a><a name="releasebuffer"></a> CSimpleStringT:: ReleaseBuffer

[GetBuffer](#getbuffer)によって割り当てられたバッファーの制御を解放します。

### <a name="syntax"></a>構文

```cpp
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>パラメーター

*nNewLength*<br/>
Null 終端文字を含まない、文字列の新しい長さ (文字数)。 文字列が null で終了した場合、-1 の既定値 `CSimpleStringT` によってサイズが文字列の現在の長さに設定されます。

### <a name="remarks"></a>解説

このメソッドを呼び出して、文字列オブジェクトのバッファーを再割り当てまたは解放します。 バッファー内の文字列が null で終了したことがわかっている場合は、 *Nnewlength* 引数を省略できます。 文字列が null で終了していない場合は、 *Nnewlength* を使用して長さを指定します。 [](#getbuffer) `ReleaseBuffer` またはその他の操作を呼び出した後、GetBuffer によって返されたアドレスが無効です `CSimpleStringT` 。

### <a name="example"></a>例

次の例は、`CSimpleStringT::ReleaseBuffer` の使い方を示しています。

```cpp
const int bufferSize = 1024;
CSimpleString s(_T("abc"), pMgr);
LPTSTR p = s.GetBuffer(bufferSize);
_tcscpy_s(p, bufferSize, _T("abc"));

// use the buffer directly
ASSERT(s.GetLength() == 3);

// String length = 3
s.ReleaseBuffer();

// Surplus memory released, p is now invalid.
ASSERT(s.GetLength() == 3);

// Length still 3
```

## <a name="csimplestringtreleasebuffersetlength"></a><a name="releasebuffersetlength"></a> CSimpleStringT::ReleaseBufferSetLength

[GetBuffer](#getbuffer)によって割り当てられたバッファーの制御を解放します。

### <a name="syntax"></a>構文

```cpp
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>パラメーター

*nNewLength*<br/>
解放される文字列の長さ

### <a name="remarks"></a>解説

この関数は [Releasebuffer](#releasebuffer) と機能的に似ていますが、文字列オブジェクトの有効な長さを渡す必要がある点が異なります。

## <a name="csimplestringtsetat"></a><a name="setat"></a> CSimpleStringT:: SetAt

オブジェクトから1つの文字を設定 `CSimpleStringT` します。

### <a name="syntax"></a>構文

```cpp
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>パラメーター

*iChar*<br/>
オブジェクト内の文字の0から始まるインデックス `CSimpleStringT` 。 *IChar* パラメーターには、0以上、 [GetLength](#getlength)によって返される値より小さい値を指定する必要があります。

*ハーフ*<br/>
新しい文字。

### <a name="remarks"></a>解説

*IChar* にある文字を上書きするには、このメソッドを呼び出します。 *IChar* が既存の文字列の境界を超えている場合、このメソッドは文字列を拡大しません。

### <a name="example"></a>例

次の例は、`CSimpleStringT::SetAt` の使い方を示しています。

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

## <a name="csimplestringtsetmanager"></a><a name="setmanager"></a> CSimpleStringT:: SetManager

オブジェクトのメモリマネージャーを指定し `CSimpleStringT` ます。

### <a name="syntax"></a>構文

```cpp
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>パラメーター

*pStringMgr*<br/>
新しいメモリマネージャーへのポインター。

### <a name="remarks"></a>解説

オブジェクトによって使用される新しいメモリマネージャーを指定するには、このメソッドを呼び出し `CSimpleStringT` ます。 メモリマネージャーと文字列オブジェクトの詳細については、「 [メモリ管理と CStringT](../memory-management-with-cstringt.md)」を参照してください。

### <a name="example"></a>例

次の例は、`CSimpleStringT::SetManager` の使い方を示しています。

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

## <a name="csimplestringtsetstring"></a><a name="setstring"></a> CSimpleStringT:: SetString

オブジェクトの文字列を設定 `CSimpleStringT` します。

### <a name="syntax"></a>構文

```cpp
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>パラメーター

*pszSrc*<br/>
Null で終わる文字列へのポインター。

*nLength*<br/>
*Pszsrc* 内の文字数のカウント。

### <a name="remarks"></a>解説

文字列をオブジェクトにコピー `CSimpleStringT` します。 `SetString` バッファー内の古い文字列データを上書きします。

の両方のバージョンで、 `SetString` *pszsrc* が null ポインターであるかどうかを確認し、存在する場合は E_INVALIDARG エラーをスローします。

の1つのパラメーターのバージョンでは、 `SetString` *pszsrc* が null で終わる文字列を指すことが想定されています。

の2つのパラメーターのバージョンでは、 `SetString` *pszsrc* を null で終わる文字列にする必要もあります。 最初に null ターミネータが検出されない限り、文字列の長さとして *Nlength* を使用します。

の2つのパラメーターのバージョンでは、 `SetString` *pszsrc* がの現在のバッファー内の場所を指しているかどうかもチェックされ `CSimpleStringT` ます。 この特別な場合、では、文字列データを `SetString` バッファーにコピーするときに文字列データを上書きしないメモリコピー関数が使用されます。

### <a name="example"></a>例

次の例は、`CSimpleStringT::SetString` の使い方を示しています。

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

## <a name="csimplestringtstringlength"></a><a name="stringlength"></a> CSimpleStringT:: StringLength

指定された文字列内の文字数を返します。

### <a name="syntax"></a>構文

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```

#### <a name="parameters"></a>パラメーター

*psz*<br/>
Null で終わる文字列へのポインター。

### <a name="return-value"></a>戻り値

*Psz* の文字数。null 終端文字をカウントしません。

### <a name="remarks"></a>解説

*Psz* によって示される文字列の文字数を取得するには、このメソッドを呼び出します。

### <a name="example"></a>例

次の例は、`CSimpleStringT::StringLength` の使い方を示しています。

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

## <a name="csimplestringttruncate"></a><a name="truncate"></a> CSimpleStringT:: Truncate

文字列を新しい長さに切り詰めます。

### <a name="syntax"></a>構文

```cpp
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>パラメーター

*nNewLength*<br/>
文字列の新しい長さ。

### <a name="remarks"></a>解説

文字列の内容を新しい長さに切り詰めるには、このメソッドを呼び出します。

> [!NOTE]
> これは、割り当てられたバッファーの長さには影響しません。 現在のバッファーを増減するには、「 [Freeextra](#freeextra) 」と「事前に割り当てる」を参照し[てください。](#preallocate)

### <a name="example"></a>例

次の例は、`CSimpleStringT::Truncate` の使い方を示しています。

```cpp
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
```

## <a name="csimplestringtunlockbuffer"></a><a name="unlockbuffer"></a> CSimpleStringT::UnlockBuffer

オブジェクトのバッファーのロックを解除 `CSimpleStringT` します。

### <a name="syntax"></a>構文

```cpp
void UnlockBuffer() throw();
```

### <a name="remarks"></a>解説

文字列の参照カウントを1にリセットするには、このメソッドを呼び出します。

デストラクターは、 `CSimpleStringT` `UnlockBuffer` デストラクターが呼び出されたときにバッファーがロックされていないことを確認するために、自動的にを呼び出します。 このメソッドの例については、「 [Lockbuffer](#lockbuffer)」を参照してください。

## <a name="csimplestringtcsimplestringt"></a><a name="dtor"></a> CSimpleStringT:: ~ CSimpleStringT

`CSimpleStringT` オブジェクトを破棄します。

### <a name="syntax"></a>構文

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>解説

オブジェクトを破棄するには、このメソッドを呼び出し `CSimpleStringT` ます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
