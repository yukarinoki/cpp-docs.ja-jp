---
title: CSimpleStringT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7dc68cd1d91cb7b651dbeb68422f6a89fb9f2f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="csimplestringt-class"></a>CSimpleStringT クラス
このクラスを表します、`CSimpleStringT`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
template <typename BaseType>
class CSimpleStringT
```  
  
### <a name="parameters"></a>パラメーター  
 `BaseType`  
 String クラスの文字型。 次のいずれかの値を指定します。  
  
- `char` (ANSI 文字列を)。  
  
- `wchar_t` (の Unicode 文字列)。  
  
- **TCHAR** (用、ANSI と Unicode 文字の文字列)。  

## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleStringT::PCXSTR](#pcxstr)|定数文字列へのポインター。|  
|[CSimpleStringT::PXSTR](#pxstr)|文字列へのポインター。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleStringT::CSimpleStringT](#ctor)|構築`CSimpleStringT`さまざまな方法でオブジェクト。|  
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|デストラクターです。|  

  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleStringT::Append](#append)|追加、`CSimpleStringT`を既存のオブジェクト`CSimpleStringT`オブジェクト。|  
|[CSimpleStringT::AppendChar](#appendchar)|文字を追加すると、既存`CSimpleStringT`オブジェクト。|  
|[CSimpleStringT::CopyChars](#copychars)|別の文字列に文字または文字をコピーします。|  
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|重複するバッファーを別の文字列に文字または文字をコピーします。|  
|[CSimpleStringT::Empty](#empty)|長さ 0 の文字列を強制します。|  
|[CSimpleStringT::FreeExtra](#freeextra)|文字列オブジェクトに割り当てられているすべての余分なメモリを解放します。|  
|[CSimpleStringT::GetAllocLength](#getalloclength)|割り当て済みの長さを取得、`CSimpleStringT`オブジェクト。|  
|[CSimpleStringT::GetAt](#getat)|指定した位置にある文字を返します。|  
|[CSimpleStringT::GetBuffer](#getbuffer)|内の文字へのポインターを返します、`CSimpleStringT`です。|  
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|内の文字へのポインターを返します、 `CSimpleStringT`、指定された長さに切り詰めました。|  
|[CSimpleStringT::GetLength](#getlength)|内の文字の数を返します、`CSimpleStringT`オブジェクト。|  
|[CSimpleStringT::GetManager](#getmanager)|メモリ マネージャーの取得、`CSimpleStringT`オブジェクト。|  
|[CSimpleStringT::GetString](#getstring)|文字の文字列を取得します|  
|[CSimpleStringT::IsEmpty](#isempty)|テストするかどうか、`CSimpleStringT`オブジェクトに文字が含まれていません。|  
|[CSimpleStringT::LockBuffer](#lockbuffer)|参照カウントを無効にし、バッファー内の文字列を保護できます。|  
|[CSimpleStringT::Preallocate](#preallocate)|文字バッファーを特定の量のメモリを割り当てます。|  
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|によって返されるバッファーの制御を解放`GetBuffer`です。|  
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|によって返されるバッファーの制御を解放`GetBuffer`です。|  
|[CSimpleStringT::SetAt](#setat)|指定された位置に文字を設定します。|  
|[CSimpleStringT::SetManager](#setmanager)|メモリ マネージャーの設定、`CSimpleStringT`オブジェクト。|  
|[CSimpleStringT::SetString](#setstring)|文字列を設定、`CSimpleStringT`オブジェクト。|  
|[CSimpleStringT::StringLength](#stringlength)|指定された文字列の文字数を返します。|  
|[CSimpleStringT::Truncate](#truncate)|指定された長さに文字列を切り捨てます。|  
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|参照カウントを有効にし、バッファー内の文字列を解放します。|  

### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleStringT::operator PCXSTR](#operator_pcxstr)|格納された文字に直接アクセスする、`CSimpleStringT`オブジェクトを C スタイルの文字列として。|  
|[CSimpleStringT::operator\[\]](#operator_at)|指定した位置にある文字が返されますなどの演算子の代替`GetAt`です。|  
|[CSimpleStringT::operator + =](#operator_add_eq)|既存の文字列の末尾に新しい文字列を連結します。|  
|[CSimpleStringT::operator =](#operator_eq)|新しい値を割り当てます、`CSimpleStringT`オブジェクト。|  
  
### <a name="remarks"></a>コメント  
 `CSimpleStringT` Visual C でサポートされているさまざまな文字列クラスの基本クラスです。 基本的なバッファー操作、文字列オブジェクトのメモリ管理の最小限のサポートを提供します。 高度な文字列オブジェクトでは、次を参照してください。 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpstr.h  


## <a name="append"></a> CSimpleStringT::Append
追加、`CSimpleStringT`を既存のオブジェクト`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
void Append(const CSimpleStringT& strSrc); 
void Append(PCXSTR pszSrc, int nLength); 
void Append(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>パラメーター  
 `strSrc`  
 `CSimpleStringT`追加するオブジェクト。  
  
 `pszSrc`  
 追加する文字を含む文字列へのポインター。  
  
 `nLength`  
 追加する文字数。  
  
### <a name="remarks"></a>コメント  
 既存を追加するには、このメソッドを呼び出す`CSimpleStringT`を別のオブジェクト`CSimpleStringT`オブジェクト。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::Append` の使い方を示しています。  
  
```cpp  
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```
  
##  <a name="appendchar"></a> CSimpleStringT::AppendChar
文字を追加すると、既存`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
void AppendChar(XCHAR ch);
```  
#### <a name="parameters"></a>パラメーター  
 *ch*  
 追加する文字  
  
### <a name="remarks"></a>コメント  
 既存の末尾に指定した文字を追加するには、この関数を呼び出す`CSimpleStringT`オブジェクト。  
  
##  <a name="copychars"></a> CSimpleStringT::CopyChars  
 文字または文字のコピー、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
static void CopyChars(
  XCHAR* pchDest,
  const XCHAR* pchSrc, 
  int nChars) throw();
```  
#### <a name="parameters"></a>パラメーター  
 `pchDest`  
 文字の文字列へのポインター。  
  
 `pchSrc`  
 コピーする文字を含む文字列へのポインター。  
  
 `nChars`  
 数`pchSrc`コピーする文字。  
  
### <a name="remarks"></a>コメント  
 文字をコピーするには、このメソッドを呼び出す`pchSrc`を`pchDest`文字列。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::CopyChars` の使い方を示しています。  
  
```cpp  
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```
  
##  <a name="copycharsoverlapped"></a>  CSimpleStringT::CopyCharsOverlapped
文字または文字のコピー、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
static void CopyCharsOverlapped(
  XCHAR* pchDest,
  const XCHAR* pchSrc,
  int nChars) throw(); 
```  
#### <a name="parameters"></a>パラメーター  
 `pchDest`  
 文字の文字列へのポインター。  
  
 `pchSrc`  
 コピーする文字を含む文字列へのポインター。  
  
 `nChars`  
 数`pchSrc`コピーする文字。  
  
### <a name="remarks"></a>コメント  
 文字をコピーするには、このメソッドを呼び出す`pchSrc`を`pchDest`文字列。 異なり`CopyChars`、`CopyCharsOverlapped`オーバー ラップする可能性がありますの文字バッファーからコピーするための安全なメソッドを提供します。  
  
### <a name="example"></a>例  
 例を参照して[CSimpleStringT::CopyChars](#copychars)、またはソース コードを`CSimpleStringT::SetString`(atlsimpstr.h にあります)。  
  
##  <a name="ctor"></a>  CSimpleStringT::CSimpleStringT  
 `CSimpleStringT` オブジェクトを構築します。  
  
### <a name="syntax"></a>構文  
  
```  
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr); 
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr); 
CSimpleStringT(const CSimpleStringT& strSrc); 
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw(); 
```  
#### <a name="parameters"></a>パラメーター  
 `strSrc`  
 既存の`CSimpleStringT`オブジェクトにコピーされるこの`CSimpleStringT`オブジェクト。  
  
 `pchSrc`  
 長さの文字の配列へのポインター `nLength`、いない null で終了します。  
  
 `pszSrc`  
 これにコピーされる null で終わる文字列`CSimpleStringT`オブジェクト。  
  
 `nLength`  
 文字数のカウント`pch`です。  
  
 `pStringMgr`  
 メモリ マネージャーへのポインター、`CSimpleStringT`オブジェクト。 詳細については`IAtlStringMgr`およびメモリ管理を`CSimpleStringT`を参照してください[メモリ管理と CStringT](../memory-management-with-cstringt.md)です。  
  
### <a name="remarks"></a>コメント  
 新しい `CSimpleStringT` オブジェクトを構築します。 コンス トラクターは、新しい割り当てられている記憶域に入力データをコピーするために、メモリ不足例外があります。  
  
### <a name="example"></a>例  
 次の例で使用する`CSimpleStringT::CSimpleStringT`ATL を使用して、 `typedef` `CSimpleString`です。 `CSimpleString` 一般的に使用される特殊クラス テンプレートの`CSimpleStringT`します。  
  
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

  
##  <a name="empty"></a>  CSimpleStringT::Empty
これにより、`CSimpleStringT`オブジェクトの空の文字列と、必要に応じてメモリを解放します。  
  
### <a name="syntax"></a>構文  
  
```  
void Empty() throw();  
```  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[文字列: CString の例外の後処理](../cstring-exception-cleanup.md)です。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::Empty` の使い方を示しています。  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());  
```  
  
##  <a name="freeextra"></a>  CSimpleStringT::FreeExtra
文字列が割り当てられていたが、不要になったすべての余分なメモリを解放します。  
  
### <a name="syntax"></a>構文  
  
```  
void FreeExtra(); 
```  
### <a name="remarks"></a>コメント  
 文字列オブジェクトによって消費されるメモリのオーバーヘッドが減ります。 メソッドによって返される正確な長さにバッファーを再割り当て[GetLength](#getlength)です。  
  
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
  
### <a name="remarks"></a>コメント  
 この例からの出力は次のとおりです。  
  
 `Alloc length is 1031, String length is 1024`  
  
 `Alloc length is 1031, String length is 15`  
  
 `Alloc length is 15, String length is 15`  
  
##  <a name="getalloclength"></a>  CSimpleStringT::GetAllocLength  
割り当て済みの長さを取得、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
int GetAllocLength() const throw();  
```  
### <a name="return-value"></a>戻り値  
 このオブジェクトに割り当てられた文字の数。  
  
### <a name="remarks"></a>コメント  
 これに割り当てられた文字の数を決定するには、このメソッドを呼び出す`CSimpleStringT`オブジェクト。 参照してください[FreeExtra](#freeextra)この関数の呼び出しの例についてはします。  
  
##  <a name="getat"></a>  CSimpleStringT::GetAt  
1 つの文字を返します、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
XCHAR GetAt(int iChar) const;
```  
#### <a name="parameters"></a>パラメーター  
 `iChar`  
 内の文字の 0 から始まるインデックス、`CSimpleStringT`オブジェクト。 `iChar`より大きいまたは 0 に等しいとによって返される値よりも小さいかをパラメーターとして使用することがあります[GetLength](#getlength)です。 それ以外の場合、`GetAt`例外が生成されます。  
  
### <a name="return-value"></a>戻り値  
 `XCHAR`文字列で指定した位置にある文字を格納しています。  
  
### <a name="remarks"></a>コメント  
 指定された 1 つの文字を返すには、このメソッドを呼び出す`iChar`です。 オーバー ロードされた、添字 (`[]`) 演算子はの便利なエイリアス`GetAt`です。 使用して例外を生成せず、null 終端文字がアドレス指定可能な`GetAt`します。 ただし、これはカウントされない`GetLength`、返される値は 0 です。  
  
### <a name="example"></a>例  
 次の例を使用する方法を示します`CSimpleStringT::GetAt`です。  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```
  
##  <a name="getbuffer"></a>  CSimpleStringT::GetBuffer  
内部文字バッファーへのポインターを返します、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
PXSTR GetBuffer(int nMinBufferLength); 
PXSTR GetBuffer();
```  
#### <a name="parameters"></a>パラメーター  
 `nMinBufferLength`  
 文字バッファーに保持できる文字の最小数。 この値では、null 終端文字のスペースは含まれません。  
  
 場合`nMinBufferLength`が現在のバッファーの長さよりも大きい`GetBuffer`現在のバッファーを破棄し、要求されたサイズのバッファーに置き換えられ、オブジェクトの参照カウントを 0 にリセットします。 以前を呼び出した場合[LockBuffer](#lockbuffer)このバッファーでバッファーのロックが失われました。  
  
### <a name="return-value"></a>戻り値  
 `PXSTR`オブジェクトの (null で終わる) 文字バッファーへのポインター。  
  
### <a name="remarks"></a>コメント  
 バッファーの内容を返すには、このメソッドを呼び出す、`CSimpleStringT`オブジェクト。 返された`PXSTR`定数ではありませんし、したがっての直接的な変更では、`CSimpleStringT`内容。  
  
 によって返されたポインターを使用する場合`GetBuffer`文字列の内容を変更するを呼び出す必要があります[ReleaseBuffer](#releasebuffer)以外を使用する前に`CSimpleStringT`メンバー メソッド。  
  
 によって返されるアドレス`GetBuffer`が無効である呼び出しの後に`ReleaseBuffer`ため追加`CSimpleStringT`操作が発生することができます、`CSimpleStringT`を再割り当てするバッファー。 長さを変更しない場合、バッファーが再割り当てできません、`CSimpleStringT`です。  
  
 バッファーのメモリが自動的に解放されるときに、`CSimpleStringT`オブジェクトが破棄されます。  
  
 場合の追跡は文字列の長さ自分で、終端の null 文字を付けないでください。 含むバッファーを解放するときに、最終的な文字列の長さを指定する必要がありますただし、`ReleaseBuffer`です。 終端の null 文字を追加する場合は、長さの場合は-1 (既定値) を渡す必要があります。 `ReleaseBuffer` バッファーの長さを決定します。  
  
 対応する十分なメモリがある場合、`GetBuffer`要求と、このメソッドはスロー CMemoryException * です。  
  
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
  
##  <a name="getbuffersetlength"></a>  CSimpleStringT::GetBufferSetLength  
内部文字バッファーへのポインターを返します、`CSimpleStringT`オブジェクト、切り捨てまたはで指定された長さと正確に一致する必要がある場合は、その長さを拡大して`nLength`です。  
  
### <a name="syntax"></a>構文  
  
```  
PXSTR GetBufferSetLength(int nLength);
```  
#### <a name="parameters"></a>パラメーター  
 `nLength`  
 正確なサイズ、`CSimpleStringT`文字内で文字バッファー。  
  
### <a name="return-value"></a>戻り値  
 A`PXSTR`オブジェクトの (null で終わる) 文字バッファーへのポインター。  
  
### <a name="remarks"></a>コメント  
 内部バッファーの指定された長さを取得するには、このメソッドを呼び出して、`CSimpleStringT`オブジェクト。 返された`PXSTR`ポインターがない`const`できるので、直接変更`CSimpleStringT`内容。  
  
 によって返されたポインターを使用する場合[GetBufferSetLength](#getbuffersetlength)文字列の内容を変更するには、呼び出す`ReleaseBuffer`の内部状態を更新する`CsimpleStringT`以外を使用する前に`CSimpleStringT`メソッドです。  
  
 によって返されるアドレス`GetBufferSetLength`が無効である呼び出しの後に`ReleaseBuffer`ため追加`CSimpleStringT`操作が発生することができます、`CSimpleStringT`を再割り当てするバッファー。 長さを変更しない場合は、バッファーを再割り当てされません、`CSimpleStringT`です。  
  
 バッファーのメモリが自動的に解放されるときに、`CSimpleStringT`オブジェクトが破棄されます。  
  
 追跡は文字列の長さ自分で場合、は、終端の null 文字をいない追加しません。 使用して、バッファーを解放する場合は、最終的な文字列の長さを指定する必要があります`ReleaseBuffer`です。 呼び出すとき、終端の null 文字を追加するかどうかは`ReleaseBuffer`に長さの場合 (既定)、-1 を渡します`ReleaseBuffer`、および`ReleaseBuffer`を実行、`strlen`でその長さを決定するバッファーでします。  
  
 参照カウントの詳細については、次の記事を参照してください。  
  
- [参照カウントをオブジェクトの有効期間を管理する](http://msdn.microsoft.com/library/windows/desktop/ms687260)Windows SDK にします。 
  
- [参照カウントを実装する](http://msdn.microsoft.com/library/windows/desktop/ms693431)Windows SDK にします。
  
- [参照カウントを管理するためのルール](http://msdn.microsoft.com/library/windows/desktop/ms692481)Windows SDK にします。  
  
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
  
##  <a name="getlength"></a>  CSimpleStringT::GetLength  
内の文字の数を返します、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
int GetLength() const throw();  
```  
### <a name="return-value"></a>戻り値  
 文字列の文字の数。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出してオブジェクト内の文字数を返します。 カウントには、null 終端文字は含まれません。  
  
 マルチバイト文字セット (MBCS) の`GetLength`カウントが 1 つのマルチバイト文字内の各 8 ビット文字です。 つまり、、潜在顧客と後続バイトが 2 バイトとしてカウントされます。 参照してください[FreeExtra](#freeextra)この関数の呼び出しの例についてはします。  
  
##  <a name="getmanager"></a>  CSimpleStringT::GetManager  
メモリ マネージャーの取得、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
IAtlStringMgr* GetManager() const throw();  
```  
### <a name="return-value"></a>戻り値  
 メモリ マネージャーへのポインター、`CSimpleStringT`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 マネージャーによって使用されるメモリを取得するには、このメソッドを呼び出して、`CSimpleStringT`オブジェクト。 メモリ マネージャーと文字列オブジェクトの詳細については、次を参照してください。[メモリ管理と CStringT](../memory-management-with-cstringt.md)です。  
  
##  <a name="getstring"></a>  CSimpleStringT::GetString
文字の文字列を取得します。  
  
### <a name="syntax"></a>構文  
  
```  
PCXSTR GetString() const throw();
```  
### <a name="return-value"></a>戻り値  
 Null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 関連付けられている文字の文字列を取得するには、このメソッドを呼び出して、`CSimpleStringT`オブジェクト。  
  
> [!NOTE]
>  返された`PCXSTR`ポインターが`const`との直接的な変更を許可しない`CSimpleStringT`内容。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::GetString` の使い方を示しています。  
  
```cpp  
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```
  
##  <a name="isempty"></a>  CSimpleStringT::IsEmpty  
テスト、`CSimpleStringT`空の状態のオブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
bool IsEmpty() const throw();  
```  
### <a name="return-value"></a>戻り値  
 返します**true**場合、`CSimpleStringT`オブジェクトには長さが 0 以外の場合**false**です。  
  
### <a name="remarks"></a>コメント  
 オブジェクトに、空の文字列が含まれているかどうかは、このメソッドを呼び出します。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::IsEmpty` の使い方を示しています。  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```
  
##  <a name="lockbuffer"></a>  CSimpleStringT::LockBuffer  
参照カウントを無効にし、バッファー内の文字列を保護できます。  
  
### <a name="syntax"></a>構文  
  
```  
PXSTR LockBuffer();
```  
### <a name="return-value"></a>戻り値  
 ポインター、`CSimpleStringT`オブジェクトまたは null で終わる文字列。  
  
### <a name="remarks"></a>コメント  
 バッファーをロックするには、このメソッドを呼び出して、`CSimpleStringT`オブジェクト。 呼び出して`LockBuffer`、参照カウントの場合は-1 で、文字列のコピーを作成します。 参照カウント値が-1 の場合は、バッファー内の文字列が「ロック」の状態であると見なされます。 ロックの状態のときに、文字列が 2 つの方法で保護します。  
  
-   その他の文字列を取得できませんデータへの参照をロックされた文字列の場合でも、ロックされた文字列に割り当てられている文字列。  
  
-   ロックされた文字列にその他の文字列をコピーする場合でも、ロックされた文字列は別の文字列参照はありません。  
  
 バッファーに文字列をロックすることにより、文字列のバッファーで排他的に保持はそのまま残ることを確認します。  
  
 完了したら後`LockBuffer`、呼び出す[として](#unlockbuffer)参照カウントを 1 にリセットします。  
  
> [!NOTE]
>  呼び出す場合[GetBuffer](#getbuffer)ロックされているバッファーに設定、`GetBuffer`パラメーター`nMinBufferLength`から現在のバッファーの長さより大きいバッファーのロックは失われます。 このような呼び出しを`GetBuffer`現在のバッファーを破棄し、要求されたサイズのバッファーに置き換えられ、参照カウントを 0 にリセットします。  
  
 参照カウントの詳細については、次の記事を参照してください。  
  
- [参照カウントをオブジェクトの有効期間を管理する](http://msdn.microsoft.com/library/windows/desktop/ms687260)Windows SDK の  
  
- [参照カウントを実装する](http://msdn.microsoft.com/library/windows/desktop/ms693431)Windows SDK の  
  
- [参照カウントを管理するためのルール](http://msdn.microsoft.com/library/windows/desktop/ms692481)Windows SDK の  
  
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
  
##  <a name="operator_at"></a>  CSimpleStringT::operator\[\]  
文字配列の 1 つの文字にアクセスするには、この関数を呼び出します。  
  
### <a name="syntax"></a>構文  
  
```  
XCHAR operator[](int iChar) const;
```  
#### <a name="parameters"></a>パラメーター  
 `iChar`  
 文字列内の文字の 0 から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 オーバー ロードされた、添字 (`[]`) 演算子内の 0 から始まるインデックスによって指定された 1 つの文字を返します`iChar`です。 この演算子は便利な代替には、 [GetAt](#getat)メンバー関数。  
  
> [!NOTE]
>  下付き文字を使用することができます (`[]`) 内の文字の値を取得する演算子を`CSimpleStringT`、内の文字の値を変更するのには使用できませんが、`CSimpleStringT`です。  
  
### <a name="example"></a>例  
 次の例で使用する**CSimpleStringT::operator:operator[]** です。  
  
```cpp  
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```
  
## <a name="operator_at"></a>  CSimpleStringT::operator \[\]
文字配列の 1 つの文字にアクセスするには、この関数を呼び出します。  
  
### <a name="syntax"></a>構文  
  
```   
XCHAR operator[](int iChar) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `iChar`  
 文字列内の文字の 0 から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 オーバー ロードされた、添字 (`[]`) 演算子内の 0 から始まるインデックスによって指定された 1 つの文字を返します`iChar`です。 この演算子は便利な代替には、 [GetAt](#getat)メンバー関数。  
  
> [!NOTE]
>  下付き文字を使用することができます (`[]`) 内の文字の値を取得する演算子を`CSimpleStringT`、内の文字の値を変更するのには使用できませんが、`CSimpleStringT`です。  
  
  
##  <a name="operator_add_eq"></a>  CSimpleStringT::operator + =  
既存の文字列の末尾に新しい文字列または文字を結合します。  
  
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
 `pszSrc`  
 Null で終わる文字列へのポインター。  
  
 `strSrc`  
 既存へのポインター`CSimpleStringT`オブジェクト。  
  
 *ch*  
 追加される文字。  
  
### <a name="remarks"></a>コメント  
 この演算子は別`CSimpleStringT`オブジェクトまたは文字。 メモリ不足にこの追加の文字を新しい記憶域が割り当てられるために、連結演算子を使用するたびに、例外が発生する可能性があります`CSimpleStringT`オブジェクト。  
  
### <a name="example"></a>例  
 次の例で使用する**CSimpleStringT::operator + =** です。  
  
```cpp  
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```
  
##  <a name="operator_eq"></a>  CSimpleStringT::operator =  
新しい値を割り当てます、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
CSimpleStringT& operator =(PCXSTR pszSrc); 
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```  
#### <a name="parameters"></a>パラメーター  
 `pszSrc`  
 Null で終わる文字列へのポインター。  
  
 `strSrc`  
 既存へのポインター`CSimpleStringT`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 コピー先の文字列 (左側) は、新しいデータを格納するのに十分な大きさでは既に、新しいメモリ割り当ては実行されません。 メモリ不足、代入演算子を使用すると、新しい記憶域は多くの場合、その結果を保持するために割り当てられているために、例外が発生する可能性があります`CSimpleStringT`オブジェクト。  
  
### <a name="example"></a>例  
 次の例で使用する**CSimpleStringT::operator =** です。  
  
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
  
##  <a name="operator_pcxstr"></a>  CSimpleStringT::operator PCXSTR  

 格納された文字に直接アクセスする、`CSimpleStringT`オブジェクトを C スタイルの文字列として。  
  
### <a name="syntax"></a>構文  
  
```  
operator PCXSTR() const throw();
```  
### <a name="return-value"></a>戻り値  
 文字列のデータを指すポインターです。  
  
### <a name="remarks"></a>コメント  
 文字はコピーされません。ポインターのみが返されます。 この演算子を使ってように注意します。 変更した場合、`CString`オブジェクトした文字ポインターを取得した後、ポインターを無効にするメモリの再割り当てが発生する可能性があります。  
  
### <a name="example"></a>例  
 次の例で使用する**CSimpleStringT::operator PCXSTR**です。  
  
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
  
##  <a name="pcxstr"></a>  CSimpleStringT::PCXSTR
定数文字列へのポインター。  
  
### <a name="syntax"></a>構文  
  
```  
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;    
```  
##  <a name="preallocate"></a>  CSimpleStringT::Preallocate  
特定の容量 (バイト) の割り当て、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
void Preallocate( int nLength);
```  
#### <a name="parameters"></a>パラメーター  
 `nLength`  
 正確なサイズ、`CSimpleStringT`文字内で文字バッファー。  
  
### <a name="remarks"></a>コメント  
 特定のバッファー サイズを割り当てることは、このメソッドを呼び出して、`CSimpleStringT`オブジェクト。  
  
 `CSimpleStringT` 生成、`STATUS_NO_MEMORY`文字バッファーに領域を割り当てることがない場合は例外です。 既定では、メモリの割り当ては WIN32 API 関数により実行`HeapAlloc`または`HeapReAlloc`です。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::Preallocate` の使い方を示しています。  
  
```cpp  
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```
  
##  <a name="pxstr"></a>  CSimpleStringT::PXSTR  
文字列へのポインター。  
  
### <a name="syntax"></a>構文  
  
```  
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;  
```  
##  <a name="releasebuffer"></a>  CSimpleStringT::ReleaseBuffer  
によって割り当てられるバッファーの制御を解放[GetBuffer](#getbuffer)です。  
  
### <a name="syntax"></a>構文  
  
```  
void ReleaseBuffer(int nNewLength = -1);
```  
#### <a name="parameters"></a>パラメーター  
 `nNewLength`  
 Null 終端文字をカウントせず、文字の文字列の新しい長さ。 -1 の既定値が設定された文字列が null の場合は終了、`CSimpleStringT`サイズ文字列の現在の長さにします。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して再割り当てまたは文字列オブジェクトのバッファーを解放します。 バッファー内の文字列は null で終了、省略することがわかっている場合、`nNewLength`引数。 場合は、文字列が null でない終了を使用して`nNewLength`その長さを指定します。 によって返されるアドレス[GetBuffer](#getbuffer)への呼び出し後は無効`ReleaseBuffer`または他の`CSimpleStringT`操作します。  
  
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
  
##  <a name="releasebuffersetlength"></a>  CSimpleStringT::ReleaseBufferSetLength

によって割り当てられるバッファーの制御を解放[GetBuffer](#getbuffer)です。  
  
### <a name="syntax"></a>構文  
  
```  
void ReleaseBufferSetLength(int nNewLength);
```  
#### <a name="parameters"></a>パラメーター  
 `nNewLength`  
 解放されている文字列の長さ  
  
### <a name="remarks"></a>コメント  
 この関数に機能的によく似た[ReleaseBuffer](#releasebuffer)が、有効な長さの文字列オブジェクトを渡す必要があります。  
  
##  <a name="setat"></a>  CSimpleStringT::SetAt  
1 つの文字を設定、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
void SetAt(int iChar, XCHAR ch);
```  
#### <a name="parameters"></a>パラメーター  
 `iChar`  
 内の文字の 0 から始まるインデックス、`CSimpleStringT`オブジェクト。 `iChar`より大きいまたは 0 に等しいとによって返される値よりも小さいかをパラメーターとして使用することがあります[GetLength](#getlength)です。  
  
 *ch*  
 新しい文字です。  
  
### <a name="remarks"></a>コメント  
 ある文字を上書きするには、このメソッドを呼び出す`iChar`です。 場合は、このメソッドに、文字列は拡大されません`iChar`が既存の文字列の範囲を超えています。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::SetAt` の使い方を示しています。  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
``` 
  
##  <a name="setmanager"></a>  CSimpleStringT::SetManager  
メモリ マネージャーを指定します、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
void SetManager(IAtlStringMgr* pStringMgr);
```  
#### <a name="parameters"></a>パラメーター  
 `pStringMgr`  
 新しいメモリ マネージャーへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して新しいメモリを指定で使用されるマネージャー、`CSimpleStringT`オブジェクト。 メモリ マネージャーと文字列オブジェクトの詳細については、次を参照してください。[メモリ管理と CStringT](../memory-management-with-cstringt.md)です。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::SetManager` の使い方を示しています。  
  
```cpp  
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```
  
##  <a name="setstring"></a>  CSimpleStringT::SetString  
文字列を設定、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
void SetString(PCXSTR pszSrc, int nLength); 
void SetString(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>パラメーター  
 `pszSrc`  
 Null で終わる文字列へのポインター。  
  
 `nLength`  
 文字数のカウント`pszSrc`です。  
  
### <a name="remarks"></a>コメント  
 文字列をコピー、`CSimpleStringT`オブジェクト。 `SetString` バッファー内の古い文字列データを上書きします。  
  
 両方のバージョンの`SetString`を確認するかどうか`pszSrc`null ポインターでは、スローする場合は、 **E_INVALIDARG**エラーです。  
  
 パラメーターを 1 つのバージョンの`SetString`が必要ですが`pszSrc`に null で終わる文字列をポイントします。  
  
 2 つのパラメーターのバージョンの`SetString`も期待しています`pszSrc`null で終わる文字列を指定します。 使用して`nLength`文字列の長さとして null 終端文字を最初に検出した場合を除き、します。  
  
 2 つのパラメーターのバージョンの`SetString`も確認するかどうか`pszSrc`で現在のバッファー内の場所を指す`CSimpleStringT`です。 この特殊なケースで`SetString`際に、文字列データをバッファーに文字列データは上書きされませんメモリ コピー関数を使用します。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::SetString` の使い方を示しています。  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```
  
##  <a name="stringlength"></a>  CSimpleStringT::StringLength  
指定された文字列の文字数を返します。  
  
### <a name="syntax"></a>構文  
  
```  
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```  
#### <a name="parameters"></a>パラメーター  
 `psz`  
 Null で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 文字数`psz`; null 終端文字を含みません。  
  
### <a name="remarks"></a>コメント  
 指す文字列の文字数を取得するには、このメソッドを呼び出す`psz`です。  
  
### <a name="example"></a>例  
 次の例は、`CSimpleStringT::StringLength` の使い方を示しています。  
  
```cpp  
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
``` 
  
##  <a name="truncate"></a>  CSimpleStringT::Truncate
文字列を新しい長さに切り捨てます。  
  
### <a name="syntax"></a>構文  
  
```  
void Truncate(int nNewLength);
```  
#### <a name="parameters"></a>パラメーター  
 `nNewLength`  
 文字列の新しい長さ。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して、新しい長さに文字列の内容を切り捨てます。  
  
> [!NOTE]
>  これは、割り当てられたバッファーの長さには影響ありません。 現在のバッファーを増減するには、次を参照してください。 [FreeExtra](#freeextra)と[Preallocate](#preallocate)です。  
  
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
  
##  <a name="unlockbuffer"></a>  CSimpleStringT::UnlockBuffer
 バッファーのロックを解除、`CSimpleStringT`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```  
void UnlockBuffer() throw();
```  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して、文字列の参照カウントは 1 にリセットします。  
  
 `CSimpleStringT`デストラクターを自動的に呼び出します`UnlockBuffer`をデストラクターが呼び出されたときに、バッファーはロックされないことを確認します。 このメソッドの例は、次を参照してください。 [LockBuffer](#lockbuffer)です。  
  
##  <a name="dtor"></a>  CSimpleStringT:: ~ CSimpleStringT
`CSimpleStringT` オブジェクトを破棄します。  
  
### <a name="syntax"></a>構文  
  
```  
~CSimpleStringT() throw();
```  
### <a name="remarks"></a>コメント  
 破棄するには、このメソッドを呼び出して、`CSimpleStringT`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)