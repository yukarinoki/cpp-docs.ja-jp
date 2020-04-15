---
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
ms.openlocfilehash: dce33289699b9e7b7484d1feb6335476f93dee9b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317687"
---
# <a name="csimplestringt-class"></a>CSimpleStringT クラス

このクラスはオブジェクト`CSimpleStringT`を表します。

## <a name="syntax"></a>構文

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>パラメーター

*BaseType*<br/>
文字列クラスの文字型。 以下のいずれかを指定できます。

- **char** (ANSI 文字列の場合)。

- **wchar_t** (Unicode 文字列の場合)

- TCHAR (ANSI および Unicode 文字列の両方の場合)。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[をクリックします :P。](#pcxstr)|定数文字列へのポインター。|
|[を:P](#pxstr)|文字列へのポインター。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[をクリックします。](#ctor)|さまざまな方法`CSimpleStringT`でオブジェクトを構築します。|
|[::~シンプルストリング](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を追加します。](#append)|既存`CSimpleStringT`のオブジェクト`CSimpleStringT`にオブジェクトを追加します。|
|[を使用します。](#appendchar)|既存`CSimpleStringT`のオブジェクトに文字を追加します。|
|[CSimple文字列::コピーシャール](#copychars)|文字または文字を別の文字列にコピーします。|
|[オーバーラップした文字のコピー](#copycharsoverlapped)|バッファーが重なる別の文字列に文字をコピーします。|
|[をクリックします。](#empty)|文字列の長さを 0 にします。|
|[Cシンプルストリング::フリーエクストラ](#freeextra)|文字列オブジェクトによって以前に割り当てられた余分なメモリを解放します。|
|[を取得します。](#getalloclength)|`CSimpleStringT`オブジェクトの割り当てられた長さを取得します。|
|[を取得します。](#getat)|指定した位置にある文字を返します。|
|[を取得します。](#getbuffer)|の文字へのポインターを返します`CSimpleStringT`。|
|[を返します。](#getbuffersetlength)|指定した長さに切り捨てる`CSimpleStringT`のに含まれる文字へのポインターを返します。|
|[を取得します。](#getlength)|オブジェクト内の文字数を`CSimpleStringT`返します。|
|[をクリックします。](#getmanager)|オブジェクトのメモリ マネージャーを`CSimpleStringT`取得します。|
|[を取得します。](#getstring)|文字列を取得します。|
|[をクリックします。](#isempty)|オブジェクトに`CSimpleStringT`文字が含まれているかどうかをテストします。|
|[ロックバッファ](#lockbuffer)|参照カウントを無効にし、バッファー内の文字列を保護します。|
|[割り当て:P](#preallocate)|文字バッファーに特定のメモリ量を割り当てます。|
|[をクリックします。](#releasebuffer)|によって`GetBuffer`返されるバッファーの制御を解放します。|
|[を返します。](#releasebuffersetlength)|によって`GetBuffer`返されるバッファーの制御を解放します。|
|[セットアット](#setat)|指定した位置に文字を設定します。|
|[をクリックします。](#setmanager)|オブジェクトのメモリ マネージャを`CSimpleStringT`設定します。|
|[を設定します。](#setstring)|オブジェクトの文字列を`CSimpleStringT`設定します。|
|[文字列の長さ](#stringlength)|指定した文字列の文字数を返します。|
|[切り捨て](#truncate)|文字列を指定した長さに切り捨てます。|
|[をクリックします。](#unlockbuffer)|参照カウントを有効にし、バッファー内の文字列を解放します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[を使用します。](#operator_pcxstr)|オブジェクトに格納されている文字に`CSimpleStringT`C スタイルの文字列として直接アクセスします。|
|[CSimpleStringT::operator\[\]](#operator_at)|指定した位置の文字を返`GetAt`します 。|
|[を指定します。](#operator_add_eq)|新しい文字列を既存の文字列の末尾に連結します。|
|[を指定します。](#operator_eq)|オブジェクトに新しい値を`CSimpleStringT`割り当てます。|

### <a name="remarks"></a>解説

`CSimpleStringT`は、Visual C++ でサポートされる各種の文字列クラスの基本クラスです。 文字列オブジェクトのメモリ管理と基本的なバッファ操作を最小限に抑えることができます。 高度な文字列オブジェクトについては、「 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpstr.h

## <a name="csimplestringtappend"></a><a name="append"></a>を追加します。

既存`CSimpleStringT`のオブジェクト`CSimpleStringT`にオブジェクトを追加します。

### <a name="syntax"></a>構文

```
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>パラメーター

*ストルスク*<br/>
追加`CSimpleStringT`するオブジェクト。

*pszSrc*<br/>
追加する文字を含む文字列へのポインター。

*nレングス*<br/>
追加する文字数。

### <a name="remarks"></a>解説

既存`CSimpleStringT`のオブジェクトを別`CSimpleStringT`のオブジェクトに追加します。

### <a name="example"></a>例

次の例は、`CSimpleStringT::Append` の使い方を示しています。

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

## <a name="csimplestringtappendchar"></a><a name="appendchar"></a>を使用します。

既存`CSimpleStringT`のオブジェクトに文字を追加します。

### <a name="syntax"></a>構文

```
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>パラメーター

*Ch*<br/>
追加する文字

### <a name="remarks"></a>解説

指定した文字を既存`CSimpleStringT`のオブジェクトの末尾に追加します。

## <a name="csimplestringtcopychars"></a><a name="copychars"></a>CSimple文字列::コピーシャール

オブジェクトに文字をコピー`CSimpleStringT`します。

### <a name="syntax"></a>構文

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>パラメーター

*ペチデスト*<br/>
文字列へのポインター。

*pchSrc*<br/>
コピーする文字を含む文字列へのポインター。

*nChars*<br/>
コピーする*pchSrc*文字の数。

### <a name="remarks"></a>解説

このメソッドを呼び出して *、文字を pchSrc*から*pchDest*文字列にコピーします。

### <a name="example"></a>例

次の例は、`CSimpleStringT::CopyChars` の使い方を示しています。

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

## <a name="csimplestringtcopycharsoverlapped"></a><a name="copycharsoverlapped"></a>オーバーラップした文字のコピー

オブジェクトに文字をコピー`CSimpleStringT`します。

### <a name="syntax"></a>構文

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>パラメーター

*ペチデスト*<br/>
文字列へのポインター。

*pchSrc*<br/>
コピーする文字を含む文字列へのポインター。

*nChars*<br/>
コピーする*pchSrc*文字の数。

### <a name="remarks"></a>解説

このメソッドを呼び出して *、文字を pchSrc*から*pchDest*文字列にコピーします。 と`CopyChars`は`CopyCharsOverlapped`異なり、重複する可能性がある文字バッファーからコピーする安全な方法を提供します。

### <a name="example"></a>例

例については、次を参照してください[。:コピーシャール](#copychars)、または (atlsimpstr.h にある) の`CSimpleStringT::SetString`ソース コードを参照してください。

## <a name="csimplestringtcsimplestringt"></a><a name="ctor"></a>をクリックします。

`CSimpleStringT` オブジェクトを構築します。

### <a name="syntax"></a>構文

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>パラメーター

*ストルスク*<br/>
この`CSimpleStringT`オブジェクト`CSimpleStringT`にコピーされる既存のオブジェクト。

*pchSrc*<br/>
長さ*nLength*の文字の配列へのポインターが、null で終了しません。

*pszSrc*<br/>
この`CSimpleStringT`オブジェクトにコピーされる null で終わる文字列。

*nレングス*<br/>
の文字数`pch`。

*をクリックします。*<br/>
`CSimpleStringT`オブジェクトのメモリ マネージャーへのポインター。 のメモリ管理と`IAtlStringMgr`メモリ管理の`CSimpleStringT`詳細については、「[メモリ管理と CStringT](../memory-management-with-cstringt.md)」を参照してください。

### <a name="remarks"></a>解説

新しい `CSimpleStringT` オブジェクトを構築します。 コンストラクターは、入力データを新しく割り当てられた記憶域にコピーするため、メモリ例外が発生する可能性があります。

### <a name="example"></a>例

ATL **typedef**`CSimpleString`を使用`CSimpleStringT::CSimpleStringT`した使用方法を次の例に示します。 `CSimpleString`は、クラス テンプレートの一般的に使用`CSimpleStringT`される特殊化です。

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

## <a name="csimplestringtempty"></a><a name="empty"></a>をクリックします。

この`CSimpleStringT`オブジェクトを空の文字列にし、必要に応じてメモリを解放します。

### <a name="syntax"></a>構文

```
void Empty() throw();
```

### <a name="remarks"></a>解説

詳細については、「[文字列 : CString 例外クリーンアップ](../cstring-exception-cleanup.md)」を参照してください。

### <a name="example"></a>例

次の例は、`CSimpleStringT::Empty` の使い方を示しています。

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtfreeextra"></a><a name="freeextra"></a>Cシンプルストリング::フリーエクストラ

文字列によって以前に割り当てられた余分なメモリを解放しますが、不要です。

### <a name="syntax"></a>構文

```
void FreeExtra();
```

### <a name="remarks"></a>解説

これにより、文字列オブジェクトが消費するメモリオーバーヘッドが削減されます。 このメソッドは[、GetLength](#getlength)によって返される正確な長さにバッファーを再割り当てします。

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

## <a name="csimplestringtgetalloclength"></a><a name="getalloclength"></a>を取得します。

`CSimpleStringT`オブジェクトの割り当てられた長さを取得します。

### <a name="syntax"></a>構文

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトに割り当てられた文字数。

### <a name="remarks"></a>解説

この`CSimpleStringT`オブジェクトに割り当てられた文字数を調べます。 この関数を呼び出す例については[、FreeExtra](#freeextra)を参照してください。

## <a name="csimplestringtgetat"></a><a name="getat"></a>を取得します。

オブジェクトから 1`CSimpleStringT`文字を返します。

### <a name="syntax"></a>構文

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>パラメーター

*iChar*<br/>
`CSimpleStringT`オブジェクト内の文字の 0 から始まるインデックス。 *iChar*パラメータは、0 以上[、GetLength](#getlength)によって返される値より小さい値である必要があります。 それ以外`GetAt`の場合は、例外が生成されます。

### <a name="return-value"></a>戻り値

文字列`XCHAR`内の指定した位置にある文字を含む。

### <a name="remarks"></a>解説

*iChar*で指定された 1 文字を返します。 オーバーロードされた添字 (**[]**) 演算子は、`GetAt`の場合に便利なエイリアスです。 NULL 終端文字は、 を使用`GetAt`して例外を生成せずにアドレス指定できます。 ただし、この値は`GetLength`によってカウントされず、返される値は 0 です。

### <a name="example"></a>例

を使用`CSimpleStringT::GetAt`する方法を次の例に示します。

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

## <a name="csimplestringtgetbuffer"></a><a name="getbuffer"></a>を取得します。

オブジェクトの内部文字バッファーへのポインターを`CSimpleStringT`返します。

### <a name="syntax"></a>構文

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>パラメーター

*長さ*<br/>
文字バッファーが保持できる最小文字数。 この値には、NULL 終端文字用のスペースは含まれません。

*nMinBufferLength*が現在のバッファーの長さより大きい`GetBuffer`場合は、現在のバッファーを破棄し、要求されたサイズのバッファーに置き換え、オブジェクト参照カウントを 0 にリセットします。 このバッファに対して[LockBuffer](#lockbuffer)を以前に呼び出した場合、バッファ ロックは失われます。

### <a name="return-value"></a>戻り値

オブジェクト`PXSTR`の (null で終わる) 文字バッファーへのポインター。

### <a name="remarks"></a>解説

`CSimpleStringT`オブジェクトのバッファーの内容を返します。 返される`PXSTR`定数は定数ではないため、内容を`CSimpleStringT`直接変更できます。

返されるポインターを使用`GetBuffer`して文字列の内容を変更する場合は、他`CSimpleStringT`のメンバー メソッドを使用する前に[ReleaseBuffer](#releasebuffer)を呼び出す必要があります。

呼び出し`GetBuffer`後に返されるアドレスは、バッファ`ReleaseBuffer``CSimpleStringT`の再割り当て`CSimpleStringT`が発生する可能性があるため、呼び出し後に無効になる可能性があります。 の長さを変更しない場合、バッファーは再割り当てされません`CSimpleStringT`。

オブジェクトが破棄されると、バッファ メモリ`CSimpleStringT`は自動的に解放されます。

文字列の長さを自分で追跡する場合は、終端の null 文字を追加しないでください。 ただし、バッファーを`ReleaseBuffer`で解放する場合は、最後の文字列の長さを指定する必要があります。 終端の NULL 文字を追加する場合は、長さの -1 (既定値) を渡す必要があります。 `ReleaseBuffer`次に、バッファ長を決定します。

`GetBuffer`要求を満たすメモリが不足している場合、このメソッドは CMemoryException* をスローします。

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

## <a name="csimplestringtgetbuffersetlength"></a><a name="getbuffersetlength"></a>を返します。

オブジェクトの内部文字バッファーへのポインターを`CSimpleStringT`返し、必要に応じて*nLength*で指定した長さに正確に一致するように、その長さを切り捨てるか、長さを増やします。

### <a name="syntax"></a>構文

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>パラメーター

*nレングス*<br/>
文字バッファーの`CSimpleStringT`正確なサイズです。

### <a name="return-value"></a>戻り値

オブジェクト`PXSTR`の (null で終わる) 文字バッファーへのポインター。

### <a name="remarks"></a>解説

`CSimpleStringT`オブジェクトの内部バッファーの指定された長さを取得します。 返される`PXSTR`ポインタは**const**ではないため、内容を`CSimpleStringT`直接変更できます。

[GetBufferSetLength](#getbuffersetlength)によって返されるポインターを使用して文字列の内容を変更する`ReleaseBuffer`場合は、他`CsimpleStringT``CSimpleStringT`のメソッドを使用する前に内部の状態を更新する呼び出しします。

呼び出し`GetBufferSetLength`後に返されるアドレスは、バッファ`ReleaseBuffer``CSimpleStringT`の再割り当て`CSimpleStringT`が発生する可能性があるため、呼び出し後に無効になる可能性があります。 の長さを変更しない場合、バッファーは再割り当てされません`CSimpleStringT`。

オブジェクトが破棄されると、バッファ メモリ`CSimpleStringT`は自動的に解放されます。

文字列の長さを自分で追跡する場合は、終端の null 文字を追加しないでください。 を使用`ReleaseBuffer`してバッファーを解放する場合は、最後の文字列の長さを指定する必要があります。 `ReleaseBuffer`呼び出し時に終端の NULL 文字を追加する場合は、長さの -1 `ReleaseBuffer`(デフォルト`ReleaseBuffer`) を`strlen`渡し、バッファの長さを決定します。

参照カウントの詳細については、次の記事を参照してください。

- Windows SDK[での参照カウントを使用してオブジェクトの有効期間を管理](/windows/win32/com/managing-object-lifetimes-through-reference-counting)します。

- Windows SDK で[の参照カウントの実装](/windows/win32/com/implementing-reference-counting)。

- Windows SDK[で参照カウントを管理するための規則](/windows/win32/com/rules-for-managing-reference-counts)。

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

## <a name="csimplestringtgetlength"></a><a name="getlength"></a>を取得します。

オブジェクト内の文字数を`CSimpleStringT`返します。

### <a name="syntax"></a>構文

```
int GetLength() const throw();
```

### <a name="return-value"></a>戻り値

文字列内の文字数。

### <a name="remarks"></a>解説

オブジェクト内の文字数を返します。 カウントには、NULL 終端文字は含まれません。

マルチバイト文字セット (MBCS)`GetLength`の場合は、各 8 ビット文字をカウントします。つまり、1 つのマルチバイト文字のリードバイトとトレイルバイトは 2 バイトとしてカウントされます。 この関数を呼び出す例については[、FreeExtra](#freeextra)を参照してください。

## <a name="csimplestringtgetmanager"></a><a name="getmanager"></a>をクリックします。

オブジェクトのメモリ マネージャーを`CSimpleStringT`取得します。

### <a name="syntax"></a>構文

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>戻り値

`CSimpleStringT`オブジェクトのメモリ マネージャーへのポインター。

### <a name="remarks"></a>解説

`CSimpleStringT`オブジェクトによって使用されるメモリ マネージャーを取得します。 メモリ マネージャと文字列オブジェクトの詳細については、「[メモリ管理と CStringT](../memory-management-with-cstringt.md)」を参照してください。

## <a name="csimplestringtgetstring"></a><a name="getstring"></a>を取得します。

文字列を取得します。

### <a name="syntax"></a>構文

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>戻り値

NULL で終わる文字列へのポインター。

### <a name="remarks"></a>解説

`CSimpleStringT`オブジェクトに関連付けられている文字列を取得します。

> [!NOTE]
> 返された`PCXSTR`ポインターは**const**であり、内容の直接`CSimpleStringT`の変更はできません。

### <a name="example"></a>例

次の例は、`CSimpleStringT::GetString` の使い方を示しています。

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

## <a name="csimplestringtisempty"></a><a name="isempty"></a>をクリックします。

オブジェクトが`CSimpleStringT`空の条件を調べているのをテストします。

### <a name="syntax"></a>構文

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの長さが`CSimpleStringT`0 の場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトに空の文字列が含まれているかどうかを調べます。

### <a name="example"></a>例

次の例は、`CSimpleStringT::IsEmpty` の使い方を示しています。

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtlockbuffer"></a><a name="lockbuffer"></a>ロックバッファ

参照カウントを無効にし、バッファー内の文字列を保護します。

### <a name="syntax"></a>構文

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>戻り値

`CSimpleStringT`オブジェクトへのポインターまたは null で終わる文字列。

### <a name="remarks"></a>解説

`CSimpleStringT`オブジェクトのバッファーをロックします。 を呼`LockBuffer`び出すと、参照カウントに -1 を指定して文字列のコピーを作成します。 参照カウント値が -1 の場合、バッファー内の文字列は"ロック済み" 状態と見なされます。 ロック状態の間、文字列は次の 2 つの方法で保護されます。

- その文字列がロックされた文字列に割り当てられている場合でも、他の文字列はロックされた文字列内のデータへの参照を取得できません。

- ロックされた文字列は、他の文字列がロックされた文字列にコピーされても、別の文字列を参照することはありません。

文字列をバッファにロックすることで、文字列のバッファの排他的な保持がそのまま残ります。

`LockBuffer`を使用したら[、UnlockBuffer](#unlockbuffer)を呼び出して、参照カウントを 1 にリセットします。

> [!NOTE]
> ロックされたバッファーで[GetBuffer](#getbuffer)を呼び出し`GetBuffer`、`nMinBufferLength`パラメーターを現在のバッファーの長さよりも大きく設定すると、バッファー ロックが失われます。 現在のバッファーを`GetBuffer`破棄するこのような呼び出しは、要求されたサイズのバッファーに置き換え、参照カウントをゼロにリセットします。

参照カウントの詳細については、次の記事を参照してください。

- Windows SDK[での参照カウントによるオブジェクトの有効期間の管理](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

- Windows SDK での[参照カウントの実装](/windows/win32/com/implementing-reference-counting)

- Windows SDK[で参照カウントを管理するための規則](/windows/win32/com/rules-for-managing-reference-counts)

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

## <a name="csimplestringtoperator"></a><a name="operator_at"></a>を使用します。\[\]

文字配列の 1 文字にアクセスします。

### <a name="syntax"></a>構文

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>パラメーター

*iChar*<br/>
文字列内の文字の 0 から始まるインデックス。

### <a name="remarks"></a>解説

オーバーロードされた添字 **([])** 演算子は *、iChar*の 0 から始まるインデックスで指定された 1 文字を返します。 この演算子は[、GetAt](#getat)メンバー関数の代わりに便利です。

> [!NOTE]
> 添字 (**[])** 演算子を使用して`CSimpleStringT`、 の文字の値を取得することはできますが、 の文字の値を変更することはできません。 `CSimpleStringT`

### <a name="example"></a>例

次の例は、`CSimpleStringT::operator []` の使い方を示しています。

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="csimplestringtoperator-"></a><a name="operator_at"></a>を使用します。\[\]

文字配列の 1 文字にアクセスします。

### <a name="syntax"></a>構文

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>パラメーター

*iChar*<br/>
文字列内の文字の 0 から始まるインデックス。

### <a name="remarks"></a>解説

オーバーロードされた添字 **([])** 演算子は *、iChar*の 0 から始まるインデックスで指定された 1 文字を返します。 この演算子は[、GetAt](#getat)メンバー関数の代わりに便利です。

> [!NOTE]
> 添字 (**[])** 演算子を使用して`CSimpleStringT`、 の文字の値を取得することはできますが、 の文字の値を変更することはできません。 `CSimpleStringT`

## <a name="csimplestringtoperator-"></a><a name="operator_add_eq"></a>を指定します。

新しい文字列または文字列を既存の文字列の末尾に結合します。

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
null で終わる文字列へのポインター。

*ストルスク*<br/>
既存`CSimpleStringT`のオブジェクトへのポインター。

*Ch*<br/>
追加される文字。

### <a name="remarks"></a>解説

演算子は、別`CSimpleStringT`のオブジェクトまたは文字を受け入れます。 この`CSimpleStringT`連結演算子を使用すると、このオブジェクトに追加される文字に新しい記憶域が割り当てられる場合があるため、メモリ例外が発生する場合があります。

### <a name="example"></a>例

次の例は、`CSimpleStringT::operator +=` の使い方を示しています。

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

## <a name="csimplestringtoperator-"></a><a name="operator_eq"></a>を指定します。

オブジェクトに新しい値を`CSimpleStringT`割り当てます。

### <a name="syntax"></a>構文

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>パラメーター

*pszSrc*<br/>
null で終わる文字列へのポインター。

*ストルスク*<br/>
既存`CSimpleStringT`のオブジェクトへのポインター。

### <a name="remarks"></a>解説

変換先文字列 (左側) が新しいデータを格納するのに十分な大きさを既に持っている場合、新しいメモリ割り当ては実行されません。 割り当て演算子を使用すると、結果`CSimpleStringT`のオブジェクトを保持するために新しいストレージが割り当てられることが多いため、メモリ例外が発生する場合があります。

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

## <a name="csimplestringtoperator-pcxstr"></a><a name="operator_pcxstr"></a>を使用します。

オブジェクトに格納されている文字に`CSimpleStringT`C スタイルの文字列として直接アクセスします。

### <a name="syntax"></a>構文

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>戻り値

文字列のデータへの文字ポインター。

### <a name="remarks"></a>解説

文字はコピーされません。ポインターのみが返されます。 この演算子には注意してください。 文字ポインターを取得`CString`した後にオブジェクトを変更すると、ポインターを無効にするメモリの再割り当てが発生する可能性があります。

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

## <a name="csimplestringtpcxstr"></a><a name="pcxstr"></a>をクリックします :P。

定数文字列へのポインター。

### <a name="syntax"></a>構文

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

## <a name="csimplestringtpreallocate"></a><a name="preallocate"></a>割り当て:P

オブジェクトに特定のバイト数を`CSimpleStringT`割り当てます。

### <a name="syntax"></a>構文

```
void Preallocate( int nLength);
```

#### <a name="parameters"></a>パラメーター

*nレングス*<br/>
文字バッファーの`CSimpleStringT`正確なサイズです。

### <a name="remarks"></a>解説

`CSimpleStringT`オブジェクトに特定のバッファー サイズを割り当てます。

`CSimpleStringT`は、文字バッファーにスペースを割り当てることができない場合に、STATUS_NO_MEMORY例外を生成します。 既定では、メモリ割り当ては WIN32 `HeapAlloc` `HeapReAlloc`API 関数または .

### <a name="example"></a>例

次の例は、`CSimpleStringT::Preallocate` の使い方を示しています。

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

## <a name="csimplestringtpxstr"></a><a name="pxstr"></a>を:P

文字列へのポインター。

### <a name="syntax"></a>構文

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

## <a name="csimplestringtreleasebuffer"></a><a name="releasebuffer"></a>をクリックします。

[GetBuffer](#getbuffer)によって割り当てられたバッファーの制御を解放します。

### <a name="syntax"></a>構文

```
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>パラメーター

*n新しい長さ*<br/>
null 終端文字をカウントしない文字列の新しい長さ(文字数)。 文字列が null で終わる場合、-1 の既定値`CSimpleStringT`は、サイズを文字列の現在の長さに設定します。

### <a name="remarks"></a>解説

文字列オブジェクトのバッファーを再割り当てまたは解放します。 バッファー内の文字列が null で終了することがわかっている場合は *、nNewLength*引数を省略できます。 文字列が null で終わっていない場合は *、nNewLength を*使用して長さを指定します。 [GetBuffer](#getbuffer)によって返されるアドレスは、呼び出`ReleaseBuffer`しまたはその他`CSimpleStringT`の操作の後に無効です。

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

## <a name="csimplestringtreleasebuffersetlength"></a><a name="releasebuffersetlength"></a>を返します。

[GetBuffer](#getbuffer)によって割り当てられたバッファーの制御を解放します。

### <a name="syntax"></a>構文

```
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>パラメーター

*n新しい長さ*<br/>
解放される文字列の長さ

### <a name="remarks"></a>解説

この関数は、文字列オブジェクトに有効な長さを渡す必要があるという点を除いて[、機能上、ReleaseBuffer](#releasebuffer)に似ています。

## <a name="csimplestringtsetat"></a><a name="setat"></a>セットアット

オブジェクトから 1 文字`CSimpleStringT`を設定します。

### <a name="syntax"></a>構文

```
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>パラメーター

*iChar*<br/>
`CSimpleStringT`オブジェクト内の文字の 0 から始まるインデックス。 *iChar*パラメータは、0 以上[、GetLength](#getlength)によって返される値より小さい値である必要があります。

*Ch*<br/>
新しい文字。

### <a name="remarks"></a>解説

*iChar*にある文字を上書きします。 *iChar*が既存の文字列の範囲を超えた場合、このメソッドは文字列を拡大しません。

### <a name="example"></a>例

次の例は、`CSimpleStringT::SetAt` の使い方を示しています。

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

## <a name="csimplestringtsetmanager"></a><a name="setmanager"></a>をクリックします。

オブジェクトのメモリ マネージャを`CSimpleStringT`指定します。

### <a name="syntax"></a>構文

```
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
新しいメモリ マネージャーへのポインター。

### <a name="remarks"></a>解説

オブジェクトによって使用される新しいメモリ マネージャーを`CSimpleStringT`指定します。 メモリ マネージャと文字列オブジェクトの詳細については、「[メモリ管理と CStringT](../memory-management-with-cstringt.md)」を参照してください。

### <a name="example"></a>例

次の例は、`CSimpleStringT::SetManager` の使い方を示しています。

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

## <a name="csimplestringtsetstring"></a><a name="setstring"></a>を設定します。

オブジェクトの文字列を`CSimpleStringT`設定します。

### <a name="syntax"></a>構文

```
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>パラメーター

*pszSrc*<br/>
null で終わる文字列へのポインター。

*nレングス*<br/>
*pszSrc*内の文字数。

### <a name="remarks"></a>解説

オブジェクトに文字列を`CSimpleStringT`コピーします。 `SetString`は、バッファー内の古い文字列データを上書きします。

`SetString` *pszSrc*が null ポインタであるかどうかをチェックする両方のバージョンの場合は、E_INVALIDARGエラーをスローします。

1 つのパラメーターバージョンの`SetString` *pszSrc*は、null で終わる文字列を指します。

2 つのパラメーターバージョンの`SetString`場合も *、pszSrc*は null で終わる文字列であると想定しています。 最初に null 終端文字が検出されない限り *、nLength*を文字列の長さに使用します。

2 つのパラメーターバージョンの`SetString`は *、pszSrc*が の現在のバッファー内の`CSimpleStringT`位置を指しているかどうかをもチェックします。 この特殊なケースでは`SetString`、文字列データをバッファにコピーして戻すため、文字列データを上書きしないメモリコピー関数を使用します。

### <a name="example"></a>例

次の例は、`CSimpleStringT::SetString` の使い方を示しています。

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

## <a name="csimplestringtstringlength"></a><a name="stringlength"></a>文字列の長さ

指定した文字列の文字数を返します。

### <a name="syntax"></a>構文

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```

#### <a name="parameters"></a>パラメーター

*psz*<br/>
null で終わる文字列へのポインター。

### <a name="return-value"></a>戻り値

*psz*の文字数。NULL ターミネータをカウントしません。

### <a name="remarks"></a>解説

*psz*が指す文字列の文字数を取得します。

### <a name="example"></a>例

次の例は、`CSimpleStringT::StringLength` の使い方を示しています。

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

## <a name="csimplestringttruncate"></a><a name="truncate"></a>切り捨て

文字列を新しい長さに切り捨てます。

### <a name="syntax"></a>構文

```
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>パラメーター

*n新しい長さ*<br/>
文字列の新しい長さ。

### <a name="remarks"></a>解説

文字列の内容を新しい長さに切り捨てます。

> [!NOTE]
> これは、バッファーの割り当て長さに影響を与えません。 現在のバッファを増減するには[、FreeExtra](#freeextra)と[事前割り当てを](#preallocate)参照してください。

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

## <a name="csimplestringtunlockbuffer"></a><a name="unlockbuffer"></a>をクリックします。

オブジェクトのバッファーのロックを`CSimpleStringT`解除します。

### <a name="syntax"></a>構文

```
void UnlockBuffer() throw();
```

### <a name="remarks"></a>解説

文字列の参照カウントを 1 にリセットします。

デス`CSimpleStringT`トラクターは、デス`UnlockBuffer`トラクターが呼び出されたときにバッファーがロックされないように自動的に呼び出します。 このメソッドの例については、「 [LockBuffer](#lockbuffer)」を参照してください。

## <a name="csimplestringtcsimplestringt"></a><a name="dtor"></a>::~シンプルストリング

`CSimpleStringT` オブジェクトを破棄します。

### <a name="syntax"></a>構文

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>解説

`CSimpleStringT`オブジェクトを破棄します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
