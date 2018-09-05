---
title: CStringT クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATLSTR/ATL::CStringT
- ATLSTR/ATL::CStringT::CStringT
- ATLSTR/ATL::CStringT::AllocSysString
- ATLSTR/ATL::CStringT::AnsiToOem
- ATLSTR/ATL::CStringT::AppendFormat
- ATLSTR/ATL::CStringT::Collate
- ATLSTR/ATL::CStringT::CollateNoCase
- ATLSTR/ATL::CStringT::Compare
- ATLSTR/ATL::CStringT::CompareNoCase
- ATLSTR/ATL::CStringT::Delete
- ATLSTR/ATL::CStringT::Find
- ATLSTR/ATL::CStringT::FindOneOf
- ATLSTR/ATL::CStringT::Format
- ATLSTR/ATL::CStringT::FormatMessage
- ATLSTR/ATL::CStringT::FormatMessageV
- ATLSTR/ATL::CStringT::FormatV
- ATLSTR/ATL::CStringT::GetEnvironmentVariable
- ATLSTR/ATL::CStringT::Insert
- ATLSTR/ATL::CStringT::Left
- ATLSTR/ATL::CStringT::LoadString
- ATLSTR/ATL::CStringT::MakeLower
- ATLSTR/ATL::CStringT::MakeReverse
- ATLSTR/ATL::CStringT::MakeUpper
- ATLSTR/ATL::CStringT::Mid
- ATLSTR/ATL::CStringT::OemToAnsi
- ATLSTR/ATL::CStringT::Remove
- ATLSTR/ATL::CStringT::Replace
- ATLSTR/ATL::CStringT::ReverseFind
- ATLSTR/ATL::CStringT::Right
- ATLSTR/ATL::CStringT::SetSysString
- ATLSTR/ATL::CStringT::SpanExcluding
- ATLSTR/ATL::CStringT::SpanIncluding
- ATLSTR/ATL::CStringT::Tokenize
- ATLSTR/ATL::CStringT::Trim
- ATLSTR/ATL::CStringT::TrimLeft
- ATLSTR/ATL::CStringT::TrimRight
- CSTRINGT/CStringT
- CSTRINGT/CStringT::CStringT
- CSTRINGT/CStringT::AllocSysString
- CSTRINGT/CStringT::AnsiToOem
- CSTRINGT/CStringT::AppendFormat
- CSTRINGT/CStringT::Collate
- CSTRINGT/CStringT::CollateNoCase
- CSTRINGT/CStringT::Compare
- CSTRINGT/CStringT::CompareNoCase
- CSTRINGT/CStringT::Delete
- CSTRINGT/CStringT::Find
- CSTRINGT/CStringT::FindOneOf
- CSTRINGT/CStringT::Format
- CSTRINGT/CStringT::FormatMessage
- CSTRINGT/CStringT::FormatMessageV
- CSTRINGT/CStringT::FormatV
- CSTRINGT/CStringT::GetEnvironmentVariable
- CSTRINGT/CStringT::Insert
- CSTRINGT/CStringT::Left
- CSTRINGT/CStringT::LoadString
- CSTRINGT/CStringT::MakeLower
- CSTRINGT/CStringT::MakeReverse
- CSTRINGT/CStringT::MakeUpper
- CSTRINGT/CStringT::Mid
- CSTRINGT/CStringT::OemToAnsi
- CSTRINGT/CStringT::Remove
- CSTRINGT/CStringT::Replace
- CSTRINGT/CStringT::ReverseFind
- CSTRINGT/CStringT::Right
- CSTRINGT/CStringT::SetSysString
- CSTRINGT/CStringT::SpanExcluding
- CSTRINGT/CStringT::SpanIncluding
- CSTRINGT/CStringT::Tokenize
- CSTRINGT/CStringT::Trim
- CSTRINGT/CStringT::TrimLeft
- CSTRINGT/CStringT::TrimRight
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77f86356dada81afb64f0c0efa8f5f5154caa8e4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766062"
---
# <a name="cstringt-class"></a>CStringT クラス

このクラスを表す、`CStringT`オブジェクト。

## <a name="syntax"></a>構文

```

template<typename BaseType, class StringTraits>  
class CStringT :   
public CSimpleStringT<BaseType,
                      _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                      ::c_bIsMFCDLLTraits>

```

#### <a name="parameters"></a>パラメーター

*BaseType*  
String クラスの文字型。 次のいずれかの値を指定します。

- **char** (の ANSI 文字列)。

- **wchar_t** (の Unicode 文字の文字列)。

- TCHAR (の ANSI および Unicode 文字列)。

*StringTraits*  
文字列クラスには、C ランタイム (CRT) ライブラリのサポートと文字列リソースが配置される必要があるかどうかを決定します。 次のいずれかの値を指定します。

- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR、ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**

   クラスは、CRT サポートおよびリソース文字列によって指定されたモジュールでの検索が必要です。 `m_hInstResource` (アプリケーションのモジュールのクラスのメンバー)。

- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR、ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**

   クラスに、CRT サポートおよびリソース文字列によって指定されたモジュールでの検索は必要ありません`m_hInstResource`(アプリケーションのモジュールのクラスのメンバー)。

- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR、ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**

   クラスには、CRT のサポートと MFC の標準の検索アルゴリズムを使用して、リソース文字列を検索が必要です。

- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR、ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**

   クラスは、CRT のサポートと MFC の標準の検索アルゴリズムを使用して、リソース文字列を検索には必要ありません。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CStringT::CStringT](#cstringt)|構築、`CStringT`さまざまな方法でオブジェクト。|
|[CStringT:: ~ CStringT](#_dtorcstringt)|`CStringT` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStringT::AllocSysString](#allocsysstring)|BSTR を割り当てます`CStringT`データ。|
|[CStringT::AnsiToOem](#ansitooem)|ANSI 文字を OEM 文字セットをセットからのインプレース変換を使用します。|
|[CStringT::AppendFormat](#appendformat)|書式付きデータを追加すると、既存`CStringT`オブジェクト。|
|[CStringT::Collate](#collate)|2 つの文字列 (大文字と小文字が、使用してロケール固有の情報) を比較します。|
|[CStringT::CollateNoCase](#collatenocase)|2 つの文字列 (大文字小文字を区別、使用してロケール固有の情報) を比較します。|
|[CStringT::Compare](#compare)|2 つの文字列 (大文字と小文字) を比較します。|
|[CStringT::CompareNoCase](#comparenocase)|2 つの文字列 (大文字と小文字を区別しない) を比較します。|
|[CStringT::Delete](#delete)|文字列から文字を削除します。|
|[CStringT::Find](#find)|文字または文字列内の部分文字列を検索します。|
|[CStringT::FindOneOf](#findoneof)|セットから最初の一致する文字を検索します。|
|[CStringT::Format](#format)|として文字列を書式設定`sprintf`は。|
|[CStringT::FormatMessage](#formatmessage)|メッセージ文字列の書式を設定します。|
|[CStringT::FormatMessageV](#formatmessagev)|可変個引数リストを使用してメッセージ文字列の書式を設定します。|
|[CStringT::FormatV](#formatv)|可変個引数リストを使用して、文字列の書式を設定します。|
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|文字列を指定した環境変数の値に設定します。|
|[CStringT::Insert](#insert)|文字列内の指定したインデックス位置にある 1 つの文字または部分文字列を挿入します。|
|[CStringT::Left](#left)|文字列の左側部分を抽出します。|
|[CStringT::LoadString](#loadstring)|既存のロード`CStringT`Windows リソースからのオブジェクト。|
|[CStringT::MakeLower](#makelower)|この文字列を小文字のすべての文字に変換します。|
|[CStringT::MakeReverse](#makereverse)|文字列を反転させます。|
|[CStringT::MakeUpper](#makeupper)|すべての文字がこの文字列を大文字に変換します。|
|[CStringT::Mid](#mid)|文字列の中央部を抽出します。|
|[CStringT::OemToAnsi](#oemtoansi)|OEM 文字を ANSI 文字セットをセットからのインプレース変換を使用します。|
|[CStringT::Remove](#remove)|削除には、文字列から文字が示されます。|
|[CStringT::Replace](#replace)|置換には、他の文字と文字が示されます。|
|[CStringT::ReverseFind](#reversefind)|文字列内の文字を検索します。末尾から開始します。|
|[CStringT::Right](#right)|文字列の右側の部分を抽出します。|
|[名称](#setsysstring)|既存の BSTR オブジェクトからデータを設定、`CStringT`オブジェクト。|
|[CStringT::SpanExcluding](#spanexcluding)|識別される文字のセットに含まれていない最初の文字で始まる、文字列から文字を抽出`pszCharSet`します。|
|[CStringT::SpanIncluding](#spanincluding)|セット内の文字のみを含む部分文字列を抽出します。|
|[CStringT::Tokenize](#tokenize)|抽出は、対象の文字列でトークンを指定します。|
|[CStringT::Trim](#trim)|文字列から先頭および末尾の空白文字がすべてをトリムします。|
|[CStringT::TrimLeft](#trimleft)|文字列から先頭の空白文字のトリム。|
|[CStringT::TrimRight](#trimright)|末尾の空白文字、文字列から削除します。|

### <a name="operators"></a>演算子

|||
|-|-|
|[演算子 =](#operator_eq)|新しい値を割り当てます、`CStringT`オブジェクト。|
|[CStringT::operator +](#operator_add)|2 つの文字列または文字と文字列を連結します。|
|[CStringT::operator + =](#operator_add_eq)|既存の文字列の末尾に新しい文字列を連結します。|
|[CStringT::operator = =](#operator_eq_eq)|2 つの文字列が論理的に等しいかどうかを決定します。|
|[CStringT::operator! =](#operator_neq)|2 つの文字列が論理的に等しいかどうかを決定します。|
|[CStringT::operator &lt;](#operator_lt)|演算子の左側にある文字列がより小さいかどうかを判断右側にある文字列。|
|[CStringT::operator &gt;](#operator_gt)|演算子の左側にある文字列が右側にある文字列より大きいかどうかを決定します。|
|[CStringT::operator &lt;=](#operator_lt_eq)|演算子の左側にある文字列が右側にある文字列に等しいまたはそれよりも少ないかどうかを判断します。|
|[CStringT::operator &gt;=](#operator_gt_eq)|演算子の左側にある文字列が右側にある文字列以上のかどうかを決定します。|

## <a name="remarks"></a>Remarks

`CStringT` 継承[CSimpleStringT クラス](../../atl-mfc-shared/reference/csimplestringt-class.md)します。 文字の操作、並べ替え、および検索などの高度な機能は、によって実装される`CStringT`します。

> [!NOTE]
> `CStringT` オブジェクトは例外をスローできます。 これが発生したときに、`CStringT`オブジェクトが何らかの理由がメモリ不足。

A`CStringT`オブジェクトは、文字の可変長シーケンスで構成されています。 `CStringT` 関数と演算子の Basic に似た構文を使用して提供します。 連結および簡略化されたメモリの管理との比較演算子、`CStringT`オブジェクトの通常の文字配列より簡単に使用します。

> [!NOTE]
>  作成することはできますが`CStringT`に対して推奨が含まれているインスタンスには、null 文字が埋め込まれている。 メソッドと演算子を呼び出すことで`CStringT`埋め込まれた null 文字が含まれているオブジェクトは、意図しない結果を生成できます。

さまざまな組み合わせを使用して、`BaseType`と`StringTraits`パラメーター、`CStringT`できますでは、次の種類があらかじめ定義された ATL ライブラリによってオブジェクトします。

ATL アプリケーションの使用: 場合

`CString`、 `CStringA`、および`CStringW`(MFC90 MFC DLL からエクスポートされました。DLL)、ユーザーの Dll からことはありません。 防ぐためにこれは、`CStringT`複数回定義されているからです。

> [!NOTE]
>  コードに記載されているリンカー エラーの回避策が含まれるかどうか[Linking Errors When You Import CString-Derived クラス"(Q309801)](https://support.microsoft.com/help/309801/you-may-receive-an-lnk2019-error-message-when-you-build-a-visual-c-200)、そのコードを削除する必要があります。 これが不要になった。

MFC ベースのアプリケーション内で、次の文字列型があります。

|CStringT 型|宣言|
|-------------------|-----------------|
|`CStringA`|ANSI 文字では、CRT のサポートを含む文字列を入力します。|
|`CStringW`|Unicode 文字では、CRT のサポートを含む文字列を入力します。|
|`CString`|CRT のサポートと ANSI と Unicode 文字型。|

次の文字列型は ATL_CSTRING_NO_CRT が定義されているプロジェクトで使用できます。

|CStringT 型|宣言|
|-------------------|-----------------|
|`CAtlStringA`|ANSI 文字では、CRT サポートなしの文字列を入力します。|
|`CAtlStringW`|Unicode 文字では、CRT サポートなしの文字列を入力します。|
|`CAtlString`|CRT をサポートしていない ANSI と Unicode 文字型。|

次の文字列型は、ATL_CSTRING_NO_CRT が定義されていないプロジェクトで使用可能です。

|CStringT 型|宣言|
|-------------------|-----------------|
|`CAtlStringA`|ANSI 文字では、CRT のサポートを含む文字列を入力します。|
|`CAtlStringW`|Unicode 文字では、CRT のサポートを含む文字列を入力します。|
|`CAtlString`|CRT のサポートと ANSI と Unicode 文字型。|

`CString` オブジェクトは、次の特徴もあります。

- `CStringT` 連結演算の結果としてオブジェクトを拡張できます。

- `CStringT` オブジェクトは、「セマンティクス値です」に従う 考える、`CStringT`文字列へのポインターとしてではなく、実際の文字列としてのオブジェクト。

- 代わりに使用することが自由に`CStringT`オブジェクトに対する`PCXSTR`関数の引数。

- カスタムのメモリ管理の文字列バッファー。 詳細については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。

## <a name="cstringt-predefined-types"></a>CStringT 組み込み型

`CStringT`テンプレート引数を使用して文字型の定義 (か[wchar_t](../../c-runtime-library/standard-types.md)または[char](../../c-runtime-library/standard-types.md)) サポートされている場合、メソッド パラメーターの型は複雑になる時点。 定義済みの型の一連の定義および全体で使用されるこの問題を簡素化する、`CStringT`クラス。 次の表では、さまざまな種類を示します。

|名前|説明|
|----------|-----------------|
|`XCHAR`|1 つの文字 (か**wchar_t**または**char**) と同じ文字型を持つ、`CStringT`オブジェクト。|
|`YCHAR`|1 つの文字 (か**wchar_t**または**char**) と反対の文字型を持つ、`CStringT`オブジェクト。|
|`PXSTR`|文字の文字列へのポインター (か**wchar_t**または**char**) と同じ文字型を持つ、`CStringT`オブジェクト。|
|`PYSTR`|文字の文字列へのポインター (か**wchar_t**または**char**) と反対の文字型を持つ、`CStringT`オブジェクト。|
|`PCXSTR`|ポインターを**const**文字の文字列 (どちらか**wchar_t**または**char**) と同じ文字型を持つ、`CStringT`オブジェクト。|
|`PCYSTR`|ポインターを**const**文字の文字列 (どちらか**wchar_t**または**char**) と反対の文字型を持つ、`CStringT`オブジェクト。|

> [!NOTE]
>  コードのドキュメントに未記載のメソッドを使用していた`CString`(など`AssignCopy`) の文書化されている次のメソッドを使用するコードに置き換える必要がある`CStringT`(など`GetBuffer`または`ReleaseBuffer`)。 これらのメソッドから継承されます`CSimpleStringT`します。

## <a name="inheritance-hierarchy"></a>継承階層

[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>要件

|Header|を使用します。|
|------------|-------------|
|cstringt.h|MFC 専用の文字列オブジェクト|
|atlstr.h|非 MFC 文字列オブジェクト|

##  <a name="allocsysstring"></a>  CStringT::AllocSysString

BSTR 型の Automation と互換性のある文字列が割り当てられの内容をコピー、`CStringT`終端の null 文字を含む、オブジェクト。

```
BSTR AllocSysString() const;  
```

### <a name="return-value"></a>戻り値

新しく割り当てられた文字列。

### <a name="remarks"></a>Remarks

MFC プログラムで、 [CMemoryException クラス](../../mfc/reference/cmemoryexception-class.md)が不十分なメモリが存在する場合にスローされます。 ATL のプログラムで、 [CAtlException](../../atl/reference/catlexception-class.md)がスローされます。 この関数は通常、Automation で文字列を返すに使用します。

一般的には、この文字列は、COM 関数に渡される場合は、[in] としてパラメーターで文字列を解放する呼び出し元が必要です。 これを使用して行うことができます[SysFreeString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)」の説明に従って、Windows SDK。 詳細については、次を参照してください。[割り当てと BSTR のメモリの解放](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)します。

Windows での OLE 割り当て関数の詳細については、次を参照してください。 [SysAllocString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysallocstring) Windows SDK に含まれています。  


### <a name="example"></a>例

次の例は、`CStringT::AllocSysString` の使い方を示しています。

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

##  <a name="ansitooem"></a>  CStringT::AnsiToOem

これですべての文字に変換します`CStringT`ANSI 文字を OEM 文字セットをセットからのオブジェクト。

```
void AnsiToOem();
```

### <a name="remarks"></a>Remarks

関数は、_UNICODE が定義されている場合は、ご利用いただけません。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

##  <a name="appendformat"></a>  CStringT::AppendFormat

書式付きデータを追加すると、既存`CStringT`オブジェクト。

```
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>パラメーター

*pszFormat*  
コントロールの書式設定文字列。

*nFormatID*  
コントロールの書式設定文字列を含む文字列リソースの識別子です。

*argument*  
省略可能な引数。

### <a name="remarks"></a>Remarks

この関数は、書式設定し、一連の文字と値を追加します、`CStringT`します。 各オプションの引数 (ある場合) が変換されに対応する書式指定に応じて追加*pszFormat*またはで識別される文字列リソースから*nFormatID*します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

##  <a name="collate"></a>  CStringT::Collate

汎用テキスト関数を使用して 2 つの文字列を比較します`_tcscoll`します。

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>パラメーター

*2 つ*  
その他の文字列の比較に使用します。

### <a name="return-value"></a>戻り値

0 の文字列が同一の場合、< 0 の場合は、この`CStringT`オブジェクトより小さい*した*、または > 0 の場合は、この`CStringT`オブジェクトがより大きい*した*します。

### <a name="remarks"></a>Remarks

汎用テキスト関数`_tcscoll`TCHAR で定義されています。H は、いずれかにマップ`strcoll`、 `wcscoll`、または`_mbscoll`コンパイル時に定義されている文字セットによって異なります。 現在使用中で、各関数はコード ページに従って文字列の大文字小文字の比較を実行します。 詳細については、次を参照してください。 [strcoll、wcscoll、_mbscoll、_strcoll_l、_wcscoll_l、_mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)します。

##  <a name="collatenocase"></a>  CStringT::CollateNoCase

汎用テキスト関数を使用して 2 つの文字列を比較します`_tcscoll`します。

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>パラメーター

*2 つ*  
その他の文字列の比較に使用します。

### <a name="return-value"></a>戻り値

0 の文字列がある場合と同じです (無視する場合) は、< 0 の場合は、この`CStringT`オブジェクトより小さい*した*(大文字)、または > 0 の場合は、この`CStringT`オブジェクトがより大きい*した*(大文字)。

### <a name="remarks"></a>Remarks

汎用テキスト関数`_tcscoll`TCHAR で定義されています。H は、いずれかにマップ`stricoll`、 `wcsicoll`、または`_mbsicoll`コンパイル時に定義されている文字セットによって異なります。 各関数は、現在使用されているコード ページに従って、文字列の大文字と小文字を実行します。 詳細については、次を参照してください。 [strcoll、wcscoll、_mbscoll、_strcoll_l、_wcscoll_l、_mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

##  <a name="compare"></a>  CStringT::Compare

2 つの文字列 (大文字と小文字) を比較します。

```
int Compare(PCXSTR psz) const; 
```

### <a name="parameters"></a>パラメーター

*2 つ*  
その他の文字列の比較に使用します。

### <a name="return-value"></a>戻り値

0 の文字列が同一の場合、< 0 の場合は、この`CStringT`オブジェクトより小さい*した*、または > 0 の場合は、この`CStringT`オブジェクトがより大きい*した*します。

### <a name="remarks"></a>Remarks

汎用テキスト関数`_tcscmp`TCHAR で定義されています。H は、いずれかにマップ`strcmp`、 `wcscmp`、または`_mbscmp`コンパイル時に定義されている文字セットによって異なります。 各関数は、文字列の大文字小文字の比較を実行し、ロケールの影響を受けません。 詳細については、次を参照してください。 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)します。

文字列に埋め込み null 値が含まれている場合の比較のために、文字列と見なされます最初の埋め込まれた null 文字で切り捨てられます。

### <a name="example"></a>例

次の例は、`CStringT::Compare` の使い方を示しています。

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

##  <a name="comparenocase"></a>  CStringT::CompareNoCase

2 つの文字列 (大文字と小文字を区別しない) を比較します。

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>パラメーター

*2 つ*  
その他の文字列の比較に使用します。

### <a name="return-value"></a>戻り値

文字列が一致している場合は 0 (大文字)、< 0 の場合は、この`CStringT`オブジェクトより小さい*した*(大文字)、または > 0 の場合は、この`CStringT`オブジェクトがより大きい*した*(大文字)。

### <a name="remarks"></a>Remarks

汎用テキスト関数`_tcsicmp`TCHAR で定義されています。H は、いずれかにマップ`_stricmp`、`_wcsicmp`または`_mbsicmp`コンパイル時に定義されている文字セットによって異なります。 各関数は、大文字と小文字の文字列を実行します。 比較は、ロケールがない LC_COLLATE LC_CTYPE 縦横に依存します。 詳細については、次を参照してください。 [_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

##  <a name="cstringt"></a>  CStringT::CStringT

`CStringT` オブジェクトを構築します。

```
CStringT() throw() :   
    CThisSimpleString(StringTraits::GetDefaultManager());

explicit CStringT(IAtlStringMgr* pStringMgr) throw() :   
    CThisSimpleString( pStringMgr); 

CStringT(const VARIANT& varSrc);

CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);

CStringT(const CStringT& strSrc) :   
    CThisSimpleString( strSrc);

operator CSimpleStringT<
                    BaseType, 
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()

template <bool bMFCDLL>  
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :   
    CThisSimpleString( strSrc);

template <class SystemString>  
CStringT(SystemString^ pString) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);

CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength) :   
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());

CStringT(const YCHAR* pch, int nLength) :   
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :   
    CThisSimpleString( pch, nLength, pStringMgr);

CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
```

### <a name="parameters"></a>パラメーター

*pch*  
長さの文字の配列へのポインター*されて*null で終了していません。

*されて*  
文字数のカウント*pch*します。

*ch*  
1 文字です。

*pszSrc*  
これにコピーされる null で終わる文字列`CStringT`オブジェクト。

*pStringMgr*  
メモリ マネージャーへのポインター、`CStringT`オブジェクト。 詳細については`IAtlStringMgr`のメモリ管理と`CStringT`を参照してください[CStringT によるメモリ管理](../../atl-mfc-shared/memory-management-with-cstringt.md)します。

*strSrc*  
既存の`CStringT`オブジェクトにコピーされるこの`CStringT`オブジェクト。 詳細については`CThisString`と`CThisSimpleString`、「解説」を参照してください。

*varSrc*  
これにコピーされるバリアント オブジェクト`CStringT`オブジェクト。

*BaseType*  
String クラスの文字型。 次のいずれかの値を指定します。

**char** (の ANSI 文字列)。

**wchar_t** (の Unicode 文字の文字列)。

TCHAR (の ANSI および Unicode 文字列)。

*bMFCDLL*  
プロジェクトが MFC DLL (TRUE) であるかどうかどうかを指定するブール値 (FALSE)。

*[Systemstring]*  
必要があります`System::String`、し、プロジェクトは/clr でコンパイルする必要があります。

*pString*  
ハンドルを`CStringT`オブジェクト。

### <a name="remarks"></a>Remarks

コンス トラクターは、入力データを新しい割り当て済み記憶域にコピー、ため、注意する必要がメモリ不足例外が発生する可能性があります。 変換関数として機能するようにこれらのコンス トラクターのいくつかに注意してください。 これにより、たとえば、LPTSTR に置き換えてください場所、`CStringT`オブジェクトが必要です。

- `CStringT`( `LPCSTR` `lpsz` ): Unicode を構築します`CStringT`ANSI 文字列から。 このコンス トラクターは次の例で示すように文字列リソースの読み込みに使用することもできます。

- `CStringT(` `LPCWSTR` `lpsz` ): 作成、 `CStringT` Unicode 文字列。

- `CStringT`( `const unsigned char*` `psz` ): 作成することができます、`CStringT`へのポインターから**unsigned char**します。

> [!NOTE]
>  ANSI および Unicode 文字列の間で文字列の暗黙的な変換をオフに _CSTRING_DISABLE_NARROW_WIDE_CONVERSION マクロを定義します。 マクロは、変換をサポートするコンス トラクターをコンパイルから除外します。

なお、 *strSrc*パラメーターには、いずれかを指定できます、`CStringT`または`CThisSimpleString`オブジェクト。 `CStringT`、その既定のインスタンス化のいずれかを使用して、(`CString`、 `CStringA`、または`CStringW`) は`CThisSimpleString`を使用して、**この**ポインター。 `CThisSimpleString` インスタンスが宣言されて、 [CSimpleStringT クラス](../../atl-mfc-shared/reference/csimplestringt-class.md)より小さい組み込み機能を備えた小さい文字列クラスは、`CStringT`クラス。

オーバー ロード演算子`CSimpleStringT<>&()`を構築、`CStringT`オブジェクトから、`CSimpleStringT`宣言します。

> [!NOTE]
>  作成することはできますが`CStringT`に対して推奨が含まれているインスタンスには、null 文字が埋め込まれている。 メソッドと演算子を呼び出すことで`CStringT`埋め込まれた null 文字が含まれているオブジェクトは、意図しない結果を生成できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

##  <a name="_dtorcstringt"></a>  CStringT:: ~ CStringT

`CStringT` オブジェクトを破棄します。

```
~CStringT() throw();
```

### <a name="remarks"></a>Remarks

`CStringT` オブジェクトを破棄します。

##  <a name="delete"></a>  CStringT::Delete

指定したインデックス位置にある文字で始まる文字列から文字を削除します。

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>パラメーター

*iIndex*  
最初の文字の 0 から始まるインデックス、`CStringT`オブジェクトを削除します。

*nCount*  
削除する文字数。

### <a name="return-value"></a>戻り値

変更後の文字列の長さ。

### <a name="remarks"></a>Remarks

場合*nCount*が長く、文字列、文字列の残りの部分は削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output  
Before: Soccer is best,
    but hockey is quicker!  
After: Soccer best,
    but hockey is quicker!  
```

##  <a name="find"></a>  CStringT::Find

文字または部分文字列の最初の一致には、この文字列を検索します。

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>パラメーター

*pszSub*  
検索する部分文字列。

*iStart*  
使用すると、検索を開始する文字列または最初から開始するには 0 で文字のインデックス。

*ch*  
単一の文字を検索します。

### <a name="return-value"></a>戻り値

この最初の文字の 0 から始まるインデックス`CStringT`要求された部分文字列または文字に一致するオブジェクト。 部分文字列または文字が見つからない場合は-1。

### <a name="remarks"></a>Remarks

両方の 1 つの文字を受け入れるように、関数がオーバー ロード (実行時の関数に似ています`strchr`) と文字列 (のような`strstr`)。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

##  <a name="findoneof"></a>  CStringT::FindOneOf

この文字列に含まれている任意の文字に一致する最初の文字を検索*pszCharSet*します。

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>パラメーター

*pszCharSet*  
一致する文字を含む文字列。

### <a name="return-value"></a>戻り値

この文字列になっている最初の文字の 0 から始まるインデックス*pszCharSet*; 一致が存在しない場合は-1。

### <a name="remarks"></a>Remarks

内の文字のいずれかの最初に見つかった*pszCharSet*します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

##  <a name="format"></a>  CStringT::Format

書式付きデータを書き込みます、 `CStringT` 、同じ方法[sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) C スタイル文字配列にデータを書式設定します。

```
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>パラメーター

*nFormatID*  
コントロールの書式設定文字列を含む文字列リソースの識別子です。

*pszFormat*  
コントロールの書式設定文字列。

*argument*  
省略可能な引数。

### <a name="remarks"></a>Remarks

この関数は、書式化して、一連の文字と値を格納、`CStringT`します。 各オプションの引数 (ある場合) は変換されに対応する書式指定に応じて*pszFormat*またはで識別される文字列リソースから*nFormatID*します。

文字列オブジェクト自体がパラメーターとして提供されている場合、呼び出しは失敗`Format`します。 たとえば、次のコードは、予期しない結果になります。

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

詳細については、「[書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」をご覧ください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

##  <a name="formatmessage"></a>  CStringT::FormatMessage

メッセージ文字列の書式を設定します。

```
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>パラメーター

*nFormatID*  
書式設定されていないメッセージのテキストを含む文字列リソースの識別子です。

*pszFormat*  
コントロールの書式設定文字列を指します。 挿入のためにスキャンされ、それに応じて書式設定されます。 書式指定文字列は実行時の関数に似ています*printf*-パラメーターが任意の順序で挿入できることを除いて、書式指定文字列をスタイル設定します。

*argument*  
省略可能な引数。

### <a name="remarks"></a>Remarks

関数では、入力としてメッセージの定義が必要です。 メッセージ定義によって決定される*pszFormat*またはで識別される文字列リソースから*nFormatID*します。 関数は、書式設定されたメッセージ テキストをコピー、`CStringT`オブジェクト、埋め込まれたいずれかの処理が要求されている場合、シーケンスを挿入します。

> [!NOTE]
> `FormatMessage` 新しく書式設定された文字列のシステム メモリの割り当てを試行します。 この試行が失敗すると、自動的にメモリ不足例外がスローされます。

各挿入は対応するパラメーター次が必要、 *pszFormat*または*nFormatID*パラメーター。 メッセージのテキスト内でいくつかのエスケープ シーケンスが動的にメッセージの書式設定のサポートされています。 詳細については、Windows を参照してください。 [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) Windows SDK 内の関数。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

##  <a name="formatmessagev"></a>  CStringT::FormatMessageV

可変個引数リストを使用してメッセージ文字列の書式を設定します。

```
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>パラメーター

*pszFormat*  
コントロールの書式設定文字列を指します。 挿入のためにスキャンされ、それに応じて書式設定されます。 書式指定文字列は実行時の関数に似ています`printf`-パラメーターが任意の順序で挿入できることを除いて、書式指定文字列をスタイル設定します。

*pArgList*  
引数のリストへのポインター。

### <a name="remarks"></a>Remarks

関数に必要な入力としてのメッセージ定義によって決まります*pszFormat*します。 関数は、書式設定されたメッセージ テキストとへの引数の変数の一覧をコピー、`CStringT`オブジェクト、埋め込まれたいずれかの処理が要求されている場合、シーケンスを挿入します。

> [!NOTE]
> `FormatMessageV` 呼び出し[CStringT::FormatMessage](#formatmessage)、新しく書式設定された文字列のシステム メモリの割り当てしようと試みます。 この試行が失敗すると、自動的にメモリ不足例外がスローされます。

詳細については、Windows を参照してください。 [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) Windows SDK 内の関数。

##  <a name="formatv"></a>  CStringT::FormatV

可変個引数リストを使用してメッセージ文字列の書式を設定します。

```
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>パラメーター

*pszFormat*  
コントロールの書式設定文字列を指します。 挿入のためにスキャンされ、それに応じて書式設定されます。 書式指定文字列は実行時の関数に似ています`printf`-パラメーターが任意の順序で挿入できることを除いて、書式指定文字列をスタイル設定します。

*引数*  
引数のリストへのポインター。

### <a name="remarks"></a>Remarks

書式設定された文字列と引数の変数の一覧を書き込みます、 `CStringT` 、同じ文字列方法`vsprintf_s`C スタイル文字配列にデータを書式設定します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

##  <a name="getenvironmentvariable"></a>  CStringT::GetEnvironmentVariable

文字列を指定した環境変数の値に設定します。

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>パラメーター

*pszVar*  
環境変数を指定する null で終わる文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

呼び出し元プロセスの環境ブロックから、指定された変数の値を取得します。 値は、文字の null で終わる文字列の形式では。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

##  <a name="insert"></a>  CStringT::Insert

文字列内の指定したインデックス位置にある 1 つの文字または部分文字列を挿入します。

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>パラメーター

*iIndex*  
その前に、挿入が行われます文字のインデックス。

*2 つ*  
挿入する部分文字列へのポインター。

*ch*  
挿入する文字。

### <a name="return-value"></a>戻り値

変更後の文字列の長さ。

### <a name="remarks"></a>Remarks

*IIndex*パラメーターは文字または部分文字列を確保するために移動する最初の文字を識別します。 場合*nIndex* 0 の場合は、全体の文字列の前に、挿入が発生します。 場合*nIndex*が、関数、文字列の長さが存在する文字列を連結し、いずれかによって、新しいマテリアルが提供されるよりも大きい*ch*または*した*します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

##  <a name="left"></a>  CStringT::Left

抽出範囲の左端から*nCount*これから文字`CStringT`オブジェクトし、抽出された部分文字列のコピーを返します。

```
CStringT Left(int nCount) const; 
```

### <a name="parameters"></a>パラメーター

*nCount*  
この `CStringT` オブジェクトから抽出する文字数。

### <a name="return-value"></a>戻り値

指定の文字範囲のコピーを含む `CStringT` オブジェクト。 返された `CStringT` オブジェクトは空の場合があります。

### <a name="remarks"></a>Remarks

場合*nCount*文字列の長さを超えていますし、文字列全体が抽出されます。 `Left` は、Basic `Left` 関数に類似します。

マルチ バイト文字セット (MBCS) *nCount*各 8 ビット シーケンスを文字として処理できるように*nCount* 2 で乗算されたマルチバイト文字の数を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

##  <a name="loadstring"></a>  CStringT::LoadString

識別される、Windows の文字列リソースを読み取る*nID*を既存`CStringT`オブジェクト。

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>パラメーター

*hInstance*  
モジュールのインスタンスへのハンドル。

*nID*  
Windows の文字列リソース id。

*wLanguageID*  
文字列リソースの言語です。

### <a name="return-value"></a>戻り値

リソースの読み込みが成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

文字列リソースを読み込みます (*nID*)、指定したモジュールから (*hInstance*)、指定した言語を使用して (*wLanguage*)。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

##  <a name="makelower"></a>  CStringT::MakeLower

変換、`CStringT`オブジェクトを小文字の文字列。

```
CStringT& MakeLower();
```

### <a name="return-value"></a>戻り値

結果として得られる小文字の文字列。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

##  <a name="makereverse"></a>  CStringT::MakeReverse

内の文字の順序を反転、`CStringT`オブジェクト。

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>戻り値

結果には、文字列が取り消されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

##  <a name="makeupper"></a>  CStringT::MakeUpper

変換、`CStringT`に大文字の文字列オブジェクト。

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>戻り値

結果として得られる大文字の文字列。

### <a name="remarks"></a>Remarks

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

##  <a name="mid"></a>  CStringT::Mid

長さの部分文字列を抽出します*nCount*これから文字`CStringT`オブジェクト、開始位置から*iFirst* (0 から始まる)。

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const; 
```

### <a name="parameters"></a>パラメーター

*iFirst*  
この最初の文字の 0 から始まるインデックス`CStringT`で抽出された部分文字列に含まれるオブジェクト。

*nCount*  
この `CStringT` オブジェクトから抽出する文字数。 このパラメーターが指定されていない場合は、文字列の残りの部分を抽出します。

### <a name="return-value"></a>戻り値

指定の文字範囲のコピーを含む `CStringT` オブジェクト。 なお、返された`CStringT`オブジェクトを空にすることがあります。

### <a name="remarks"></a>Remarks

関数は、抽出された部分文字列のコピーを返します。 `Mid` ですが、基本的な Mid 関数に似ています (Basic でのインデックスでは、1 から始まる) です。

マルチバイト文字セット (MBCS) *nCount*各 8 ビット文字; これは、潜在顧客バイトと後続バイト マルチバイト文字が 2 つの文字としてカウントされるいずれかを参照します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

##  <a name="oemtoansi"></a>  CStringT::OemToAnsi

これですべての文字に変換します`CStringT`オブジェクトから OEM 文字を ANSI 文字セットに設定します。

```
void OemToAnsi();
```

### <a name="remarks"></a>Remarks

この関数は、_UNICODE が定義されている場合は、ご利用いただけません。

### <a name="example"></a>例

例をご覧ください[CStringT::AnsiToOem](#ansitooem)します。

##  <a name="operator_add"></a>  CStringT::operator +

2 つの文字列または文字と文字列を連結します。

```
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```

### <a name="parameters"></a>パラメーター

*ch1*  
文字列に連結する ANSI または Unicode 文字。

*ch2*  
文字列に連結する ANSI または Unicode 文字。

*str1*  
A`CStringT`文字列または文字で連結します。

*str2*  
A`CStringT`文字列または文字で連結します。

*psz1*  
文字列または文字で連結する null で終わる文字列へのポインター。

*psz2*  
文字列または文字で連結する文字列へのポインター。

### <a name="remarks"></a>Remarks

7 つのオーバー ロード形式としては、`CStringT::operator+`関数。 最初のバージョンでは、既存の 2 つを連結`CStringT`オブジェクト。 次の 2 つ連結、`CStringT`オブジェクトと、null で終わる文字列。 次の 2 つ連結、`CStringT`オブジェクトおよび ANSI 文字。 最後の 2 つ連結、`CStringT`オブジェクトと Unicode 文字。

> [!NOTE]
>  作成することはできますが`CStringT`に対して推奨が含まれているインスタンスには、null 文字が埋め込まれている。 メソッドと演算子を呼び出すことで`CStringT`埋め込まれた null 文字が含まれているオブジェクトは、意図しない結果を生成できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

##  <a name="operator_add_eq"></a>  CStringT::operator + =

文字列の末尾に文字を連結します。

```
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>  
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>  
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```

### <a name="parameters"></a>パラメーター

str  
`CThisSimpleString` オブジェクトへの参照。

*bMFCDLL*  
プロジェクトが MFC DLL であるかどうかどうか指定するブール値。

*BaseType*  
文字列の基本型。

*var*  
この文字列に連結するバリアント オブジェクト。

*ch*  
文字列に連結する ANSI または Unicode 文字。

*pszSrc*  
連結された場合、元の文字列へのポインター。

*strSrc*  
A`CStringT`をこの文字列に連結します。

### <a name="remarks"></a>Remarks

この演算子は別`CStringT`オブジェクト、文字のポインター、または 1 つの文字。 注意すべき例外が発生するは、この文字の新しい記憶域を割り当てることがあるために、この連結演算子を使用するたびにそのメモリ`CStringT`オブジェクト。

について`CThisSimpleString`の「解説」を参照してください。 [CStringT::CStringT](#cstringt)します。

> [!NOTE]
>  作成することはできますが`CStringT`に対して推奨が含まれているインスタンスには、null 文字が埋め込まれている。 メソッドと演算子を呼び出すことで`CStringT`埋め込まれた null 文字が含まれているオブジェクトは、意図しない結果を生成できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

##  <a name="operator_eq_eq"></a>  CStringT::operator = =

2 つの文字列が論理的に等しいかどうかを判断します。

```
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>パラメーター

*ch1*  
比較のための ANSI または Unicode 文字。

*ch2*  
比較のための ANSI または Unicode 文字。

*str1*  
A`CStringT`比較します。

*str2*  
A`CStringT`比較します。

*psz1*  
比較対象の null で終わる文字列へのポインター。

*psz2*  
比較対象の null で終わる文字列へのポインター。

### <a name="remarks"></a>Remarks

文字列または右側にある、文字と、それに応じて TRUE または FALSE を返します、文字列または文字の左側にあるかどうかをテストします。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

##  <a name="operator_neq"></a>  CStringT::operator! =

2 つの文字列が等しく論理的にないかどうかを判断します。

```
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>パラメーター

*ch1*  
文字列に連結する ANSI または Unicode 文字。

*ch2*  
文字列に連結する ANSI または Unicode 文字。

*str1*  
A`CStringT`比較します。

*str2*  
A`CStringT`比較します。

*psz1*  
比較対象の null で終わる文字列へのポインター。

*psz2*  
比較対象の null で終わる文字列へのポインター。

### <a name="remarks"></a>Remarks

文字列または左側にある文字が文字列または右側にある文字と等しくないかどうかをテストします。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

##  <a name="operator_lt"></a>  CStringT::operator &lt;

演算子の左側にある文字列が右側にある文字列より小さいかどうかを判断します。

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*  
A`CStringT`比較します。

*str2*  
A`CStringT`比較します。

*psz1*  
比較対象の null で終わる文字列へのポインター。

*psz2*  
比較対象の null で終わる文字列へのポインター。

### <a name="remarks"></a>Remarks

文字列、文字までの間の辞書式比較:

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

##  <a name="operator_gt"></a>  CStringT::operator &gt;

演算子の左側にある文字列が右側にある文字列より大きいかどうかを判断します。

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*  
A`CStringT`比較します。

*str2*  
A`CStringT`比較します。

*psz1*  
比較対象の null で終わる文字列へのポインター。

*psz2*  
比較対象の null で終わる文字列へのポインター。

### <a name="remarks"></a>Remarks

文字列、文字までの間の辞書式比較:

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

##  <a name="operator_lt_eq"></a>  CStringT::operator &lt;=

演算子の左側にある文字列が右側にある文字列に等しいまたはそれよりも小さいかどうかを判断します。

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*  
A`CStringT`比較します。

*str2*  
A`CStringT`比較します。

*psz1*  
比較対象の null で終わる文字列へのポインター。

*psz2*  
比較対象の null で終わる文字列へのポインター。

### <a name="remarks"></a>Remarks

文字列、文字までの間の辞書式比較:

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

##  <a name="operator_gt_eq"></a>  CStringT::operator &gt;=

演算子の左側にある文字列が右側にある文字列値以上かどうかを判断します。

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*  
A`CStringT`比較します。

*str2*  
A`CStringT`比較します。

*psz1*  
比較対象の文字列へのポインター。

*psz2*  
比較対象の文字列へのポインター。

### <a name="remarks"></a>Remarks

文字列、文字までの間の辞書式比較:

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

##  <a name="remove"></a>  CStringT::Remove

文字列から指定した文字のすべてのインスタンスを削除します。

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>パラメーター

*chRemove*  
文字列から削除する文字。

### <a name="return-value"></a>戻り値

文字数は、文字列から削除します。 文字列が変更されていない場合は 0 を返します。

### <a name="remarks"></a>Remarks

文字の比較は、大文字小文字が区別されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

##  <a name="replace"></a>  CStringT::Replace

2 つのバージョンがある`Replace`します。最初のバージョンでは、別の部分文字列を使用して部分文字列の 1 つまたは複数のコピーが置き換えられます。 両方の部分文字列は、null で終わるです。 2 番目のバージョンでは、別の文字を使用して文字の 1 つまたは複数のコピーが置き換えられます。 両方のバージョンに格納されている文字データを操作`CStringT`します。

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>パラメーター

*pszold と*  
によって置き換えられる null で終わる文字列へのポインター *pszNew*します。

*pszNew*  
置換する null で終わる文字列へのポインター *pszold と*します。

*chOld*  
置換する文字*chNew*します。

*chNew*  
文字置換*chOld*します。

### <a name="return-value"></a>戻り値

文字列が変更されていない場合は、置き換えられた文字または部分文字列、または 0 の数を返します。

### <a name="remarks"></a>Remarks

`Replace` 文字列の長さを変更できる*pszNew*と*pszold と*、同じ長さである必要はありませんし、古いの部分文字列の複数のコピーを新しいものに変更できます。 関数は、大文字と小文字を実行します。

例の`CStringT`インスタンスが`CString`、 `CStringA`、および`CStringW`します。

`CStringA`、 `Replace` ANSI またはマルチバイト (MBCS) 文字と組み合わせて動作します。 `CStringW`、`Replace`ワイド文字と連携します。

`CString`、文字データ型は次の表に、定数が定義されているかどうかに基づいて、コンパイル時に選択します。

|定義された定数|文字データ型|
|----------------------|-------------------------|
|_UNICODE|ワイド文字|
|_MBCS|マルチ バイト文字|
|どちらも|1 バイト文字|
|両方|未定義|

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

##  <a name="reversefind"></a>  CStringT::ReverseFind

この検索`CStringT`文字の最後の一致のオブジェクト。

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>パラメーター

*ch*  
検索する文字。

### <a name="return-value"></a>戻り値

この最後の文字の 0 から始まるインデックス`CStringT`文字が見つからない場合は、指定した文字または-1 と一致するオブジェクト。

### <a name="remarks"></a>Remarks

関数は、実行時刻の関数に似ています`strrchr`します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

##  <a name="right"></a>  CStringT::Right

最後に抽出します (つまり、右端) *nCount*これから文字`CStringT`オブジェクトし、抽出された部分文字列のコピーを返します。

```
CStringT Right(int nCount) const; 
```

### <a name="parameters"></a>パラメーター

*nCount*  
この `CStringT` オブジェクトから抽出する文字数。

### <a name="return-value"></a>戻り値

指定の文字範囲のコピーを含む `CStringT` オブジェクト。 なお、返された`CStringT`オブジェクトを空にすることができます。

### <a name="remarks"></a>Remarks

場合*nCount*文字列の長さを超えていますし、文字列全体が抽出されます。 `Right` Basic に似た`Right`機能 (点が異なりますが、Basic でのインデックスは 0 から始まる)。

マルチバイト文字セット (MBCS) *nCount*各 8 ビット文字; これは、潜在顧客バイトと後続バイト マルチバイト文字が 2 つの文字としてカウントされるいずれかを参照します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

##  <a name="setsysstring"></a>  名称

指す BSTR を再割り当て*pbstr*の内容をコピー、 `CStringT` NULL 文字を含む、オブジェクト。

```
BSTR SetSysString(BSTR* pbstr) const; 
```

### <a name="parameters"></a>パラメーター

*pbstr*  
文字の文字列へのポインター。

### <a name="return-value"></a>戻り値

新しい文字列。

### <a name="remarks"></a>Remarks

内容に応じて、`CStringT`オブジェクト、値によって参照される BSTR の*pbstr*を変更することができます。 関数のスロー、`CMemoryException`十分なメモリが存在する場合。

この関数は通常、自動化のために参照によって渡された文字列の値を変更する使用します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

##  <a name="spanexcluding"></a>  CStringT::SpanExcluding

識別される文字のセットに含まれていない最初の文字で始まる、文字列から文字を抽出*pszCharSet*します。

```
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```

### <a name="parameters"></a>パラメーター

*pszCharSet*  
文字列は、一連の文字として解釈されます。

### <a name="return-value"></a>戻り値

部分文字列でない文字列に文字を含む*pszCharSet*、文字列の最初の文字で始まるでも文字列内にある最初の文字で終わる*pszCharSet*(つまり、文字列とバックアップには、最初の文字が見つかった文字列内の最初の文字で始まる*pszCharSet*)。 内の文字に文字列全体を返します*pszCharSet*文字列内にあります。

### <a name="remarks"></a>Remarks

`SpanExcluding` 抽出し、最初に見つかった位置の文字の前のすべての文字を返します*pszCharSet* (つまりの文字から*pszCharSet*おり、すべての文字が文字列で、次のことがないです。返されます)。 文字*pszCharSet*が文字列にし、見つかった`SpanExcluding`文字列全体を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

##  <a name="spanincluding"></a>  CStringT::SpanIncluding

識別される文字のセットに含まれる最初の文字で始まる、文字列から文字を抽出*pszCharSet*します。

```
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```

### <a name="parameters"></a>パラメーター

*pszCharSet*  
文字列は、一連の文字として解釈されます。

### <a name="return-value"></a>戻り値

部分文字列に含まれる文字列内の文字を含む*pszCharSet*、文字列の最初の文字で始まるおよびではない文字列に文字が見つかったときに終わる*pszCharSet*します。 `SpanIncluding` 指定されたセット内の文字列の最初の文字がない場合は、空の部分文字列を返します。

### <a name="remarks"></a>Remarks

文字列の最初の文字がない場合、文字セット、`SpanIncluding`空の文字列を返します。 それ以外の場合、セットに含まれる連続する文字のシーケンスを返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

##  <a name="tokenize"></a>  CStringT::Tokenize

ターゲット文字列の次のトークンを検索します。

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const; 
```

### <a name="parameters"></a>パラメーター

*pszTokens*  
トークン区切り記号を含む文字列。 これらの区切り記号の順序は重要ではありません。

*iStart*  
検索の開始位置の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

A`CStringT`オブジェクトの現在のトークンの値を格納します。

### <a name="remarks"></a>Remarks

`Tokenize`関数は、ターゲット文字列の次のトークンを検索します。 内の文字セット*pszTokens*検索されたトークンの区切り文字を指定します。 呼び出すたびに`Tokenize`関数から始まり*iStart*、先頭の区切り文字をスキップしを返します、`CStringT`次の区切り記号文字までの文字の文字列であり、現在のトークンを含むオブジェクト。 値*iStart*文字列の末尾に達した場合は、終了区切り文字、または-1、次の位置に更新されます。 以上のトークンは、一連の呼び出しの対象の文字列の残りの部分から分けることができます`Tokenize`を使用して、 *iStart*の次のトークンが読み込まれる文字列の位置を追跡します。 関数は空の文字列を返します以上トークンがある場合と*iStart*は-1 に設定されます。

CRT とは異なりなどの関数をトークン化[strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)、`Tokenize`ターゲット文字列は変更しません。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>Remarks

この例の出力は次のとおりです。

`Resulting Token: First`

`Resulting Token: Second`

`Resulting Token: Third`

##  <a name="trim"></a>  CStringT::Trim

先頭および末尾、文字列から文字をトリミングします。

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>パラメーター

*chTarget*  
トリムされる文字。

*pszTargets*  
トリムされる文字を含む文字列へのポインター。 すべての先頭と末尾の文字の出現*pszTarget*から除去されることは、`CStringT`オブジェクト。

### <a name="return-value"></a>戻り値

トリミングされた文字列を返します。

### <a name="remarks"></a>Remarks

次のいずれかの先頭および末尾の出現をすべて削除します。

- 指定された文字*chTarget*します。

- すべての文字で指定された文字列内にある*pszTargets*します。

- 空白文字。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>Remarks

この例の出力は次のとおりです。

`Before: "******Soccer is best, but liquor is quicker!!!!!"`

`After : "Soccer is best, but liquor is quicker"`

##  <a name="trimleft"></a>  CStringT::TrimLeft

文字列の先頭から文字をトリミングします。

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>パラメーター

*chTarget*  
トリムされる文字。

*pszTargets*  
トリムされる文字を含む文字列へのポインター。 内の文字の先頭をすべて*pszTarget*から除去されることは、`CStringT`オブジェクト。

### <a name="return-value"></a>戻り値

結果のトリミングされた文字列。

### <a name="remarks"></a>Remarks

次のいずれかの先頭および末尾の出現をすべて削除します。

- 指定された文字*chTarget*します。

- すべての文字で指定された文字列内にある*pszTargets*します。

- 空白文字。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

##  <a name="trimright"></a>  CStringT::TrimRight

末尾、文字列から文字をトリミングします。

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>パラメーター

*chTarget*  
トリムされる文字。

*pszTargets*  
トリムされる文字を含む文字列へのポインター。 末尾の文字のすべて*pszTarget*から除去されることは、`CStringT`オブジェクト。

### <a name="return-value"></a>戻り値

返します、`CStringT`トリミングされた文字列を格納しているオブジェクト。

### <a name="remarks"></a>Remarks

末尾に、次のいずれかの出現を削除します。

- 指定された文字*chTarget*します。

- すべての文字で指定された文字列内にある*pszTargets*します。

- 空白文字。

`CStringT& TrimRight(XCHAR chTarget)`バージョンは、文字の 1 つのパラメーターを受け入れるしの末尾から、その文字のすべてのコピーを削除します`CStringT`文字列データ。 文字列の末尾から開始し、前面いきます。 別の文字を見つけた場合、または停止する`CSTringT`文字データが不足します。

`CStringT& TrimRight(PCXSTR pszTargets)`バージョンを検索するさまざまなすべての文字を含む null で終わる文字列を使用できます。 これらの文字のすべてのコピーを削除しますが、`CStringT`オブジェクト。 文字列の末尾から開始し、前部に動作します。 対象の文字列に含まれていない文字が見つかったとき、または停止する`CStringT`文字データが不足します。 最後の部分文字列全体のターゲットの文字列と一致しません`CStringT`します。

`CStringT& TrimRight()`バージョン パラメーターは必要ありません。 末尾から末尾の空白文字をトリム、`CStringT`文字列。 改行文字、スペース、またはタブ空白文字ができます。

-

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)   
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
[CSimpleStringT クラス](../../atl-mfc-shared/reference/csimplestringt-class.md)

