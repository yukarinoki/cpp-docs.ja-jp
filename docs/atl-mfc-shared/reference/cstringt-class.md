---
title: CStringT クラス
ms.date: 03/27/2019
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
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
ms.openlocfilehash: 90f63b474f509b4d1a15ad6fe11bda61c343f483
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317598"
---
# <a name="cstringt-class"></a>CStringT クラス

このクラスはオブジェクト`CStringT`を表します。

## <a name="syntax"></a>構文

```
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>パラメーター

*BaseType*<br/>
文字列クラスの文字型。 以下のいずれかを指定できます。

- **char** (ANSI 文字列の場合)。

- **wchar_t** (Unicode 文字列の場合)

- TCHAR (ANSI および Unicode 文字列の両方の場合)。

*ストリングストレイト*<br/>
文字列クラスに C ランタイム (CRT) ライブラリのサポートが必要かどうか、および文字列リソースが配置されている場所を決定します。 以下のいずれかを指定できます。

- **ストレイト wchar_tレイト**<<、wchar_tの **&#124;のチャー** &#124;TCHAR > >&#124;wchar_tの **&#124;の文字****&#124;TCHAR、ChTraitsCRT<** **TCHAR > >**

   このクラスでは、CRT サポートが必要で、(アプリケーションのモジュール`m_hInstResource`クラスのメンバー) で指定されたモジュール内のリソース文字列を検索します。

- **StrTraitATL wchar_t<&#124;****のチャー** **&#124;TCHAR、ChTraitsOS<wchar_t&#124;****のチャー** **&#124;TCHAR > >**

   クラスは CRT サポートを必要とせず、(アプリケーションのモジュール クラス`m_hInstResource`のメンバー) で指定されたモジュール内のリソース文字列を検索します。

- **wchar_t TCHAR** &#124;&#124;**チャー** &#124;&#124;< **wchar_t<、TCHAR** > >**TCHAR > >** **&#124;&#124;&#124;文字**

   このクラスでは、標準の MFC 検索アルゴリズムを使用して、CRT サポートとリソース文字列の検索が必要です。

- < **TCHAR > >** **TCHAR、ChTrait &#124; wchar_t<sos** &#124;&#124;&#124;**の文字**&#124;tchar > >&#124;wchar_twchar_twchar_t **StrTraitMFC< wchar_t** **char**

   このクラスでは、標準の MFC 検索アルゴリズムを使用してリソース文字列を検索する CRT を必要としません。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cストリング::Cストリング](#cstringt)|さまざまな方法で`CStringT`オブジェクトを構築します。|
|[::~CStringT](#_dtorcstringt)|`CStringT` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を返します。](#allocsysstring)|データから`CStringT`BSTR を割り当てます。|
|[Cストリングト::アンシトオーム](#ansitooem)|ANSI 文字セットから OEM 文字セットへのインプレース変換を行います。|
|[を指定します。](#appendformat)|既存`CStringT`のオブジェクトに書式付きデータを追加します。|
|[コレート](#collate)|2 つの文字列を比較します (大文字と小文字を区別し、ロケール固有の情報を使用します)。|
|[コレットノケース](#collatenocase)|2 つの文字列を比較します (大文字と小文字は区別されず、ロケール固有の情報を使用します)。|
|[比較](#compare)|2 つの文字列を比較します (大文字と小文字を区別します)。|
|[クストレット::比較なし大文字と小文字](#comparenocase)|2 つの文字列を比較します (大文字と小文字は区別されません)。|
|[CStringT::Dエレテ](#delete)|文字列から 1 文字または 1 文字を削除します。|
|[検索](#find)|大きい文字列の中の文字または部分文字列を検索します。|
|[クストレット::検索ワンOf](#findoneof)|セットから最初に一致する文字を検索します。|
|[フォーマット](#format)|文字列を書式として`sprintf`設定します。|
|[をクリックします。](#formatmessage)|メッセージ文字列をフォーマットします。|
|[をクリックします。](#formatmessagev)|可変引数リストを使用してメッセージ文字列をフォーマットします。|
|[Cストリング::フォーマットV](#formatv)|引数の変数リストを使用して文字列を書式設定します。|
|[変数を取得します。](#getenvironmentvariable)|指定した環境変数の値に文字列を設定します。|
|[挿入](#insert)|文字列内の指定されたインデックスに、1 つの文字または部分文字列を挿入します。|
|[CStringT::左](#left)|文字列の左部分を抽出します。|
|[を文字列として使用します。](#loadstring)|Windows リソース`CStringT`から既存のオブジェクトを読み込みます。|
|[Cストリング::メイクローワー](#makelower)|この文字列のすべての文字を小文字に変換します。|
|[Cストリング::メイクリバース](#makereverse)|文字列を反転します。|
|[CStringT::メイクアッパー](#makeupper)|この文字列のすべての文字を大文字に変換します。|
|[CStringT::ミッド](#mid)|文字列の中央部分を抽出します。|
|[CStringT::OemToAnsi](#oemtoansi)|OEM 文字セットから ANSI 文字セットへのインプレース変換を行います。|
|[をクリックします。](#remove)|文字列から指定された文字を削除します。|
|[置き換え](#replace)|指定された文字を他の文字に置き換えます。|
|[を見つける](#reversefind)|大きな文字列の中の文字を検索します。は終わりから始まります。|
|[CStringT::右](#right)|文字列の右の部分を抽出します。|
|[を文字列として使用します。](#setsysstring)|既存の BSTR オブジェクトを、オブジェクト`CStringT`のデータと共に設定します。|
|[を除外します。](#spanexcluding)|で`pszCharSet`識別される文字のセットにない最初の文字から始まる文字列から文字を抽出します。|
|[を含む](#spanincluding)|セット内の文字のみを含む部分文字列を抽出します。|
|[トークン化](#tokenize)|ターゲット文字列内の指定されたトークンを抽出します。|
|[CStringT::トリム](#trim)|文字列の先頭と末尾の空白文字をすべて切り取ります。|
|[CStringT::トリムレフト](#trimleft)|文字列の先頭の空白文字を切り取ります。|
|[CStringT::トリムライト](#trimright)|文字列の末尾の空白文字を切り取ります。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 =](#operator_eq)|オブジェクトに新しい値を`CStringT`割り当てます。|
|[CStringT::演算子 +](#operator_add)|2 つの文字列または文字列と文字列を連結します。|
|[CStringT::演算子 +=](#operator_add_eq)|新しい文字列を既存の文字列の末尾に連結します。|
|[==](#operator_eq_eq)|2 つの文字列が論理的に等しいかどうかを判断します。|
|[演算子を使用します。](#operator_neq)|2 つの文字列が論理的に等しくないかどうかを判断します。|
|[演算子&lt;](#operator_lt)|演算子の左側の文字列が右側の文字列より小さいかどうかを判断します。|
|[演算子&gt;](#operator_gt)|演算子の左側の文字列が右側の文字列より大きいかどうかを判断します。|
|[演算子&lt;=](#operator_lt_eq)|演算子の左側の文字列が右側の文字列以下かどうかを判断します。|
|[演算子&gt;=](#operator_gt_eq)|演算子の左側の文字列が右側の文字列以上かどうかを判断します。|

## <a name="remarks"></a>解説

`CStringT`クラスから継承[します](../../atl-mfc-shared/reference/csimplestringt-class.md)。 文字操作、順序付け、検索などの高度な機能は、 によって`CStringT`実装されます。

> [!NOTE]
> `CStringT`オブジェクトは例外をスローできます。 これは、何らかの理由`CStringT`でオブジェクトがメモリ不足になったときに発生します。

オブジェクト`CStringT`は、可変長の文字シーケンスで構成されます。 `CStringT`は、基本と同様の構文を使用して関数と演算子を提供します。 連結演算子と比較演算子は、単純化されたメモリ管理と共に、`CStringT`通常の文字配列よりもオブジェクトを使いやすくします。

> [!NOTE]
> null 文字が埋め`CStringT`込まれたインスタンスを作成することは可能ですが、この文字に対しては推奨します。 null 文字が埋`CStringT`め込まれたオブジェクトに対してメソッドと演算子を呼び出すと、意図しない結果が生じる可能性があります。

パラメーター`BaseType`と`StringTraits`パラメーターの異なる組み合`CStringT`わせを使用すると、オブジェクトは ATL ライブラリによって事前定義された次の型で使用できます。

ATL アプリケーションで使用する場合:

`CString`、、`CStringA`および`CStringW`MFC DLL (MFC90) からエクスポートされます。DLL) は、ユーザー DLL からは決してありません。 これは、乗算が定義`CStringT`されるのを防ぐために行われます。

> [!NOTE]
> コードに[CStringT を使用した文字列クラスのエクスポート](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md)で説明されているリンカー エラーの回避策が含まれている場合は、そのコードを削除する必要があります。 これは不要になりました。

MFC ベースのアプリケーションでは、次の文字列型を使用できます。

|タイプ|宣言|
|-------------------|-----------------|
|`CStringA`|CRT をサポートする ANSI 文字型の文字列。|
|`CStringW`|CRT をサポートする Unicode 文字型の文字列。|
|`CString`|CRT をサポートする ANSI 文字型と Unicode 文字型の両方。|

ATL_CSTRING_NO_CRTが定義されているプロジェクトでは、次の文字列型を使用できます。

|タイプ|宣言|
|-------------------|-----------------|
|`CAtlStringA`|CRT をサポートしない ANSI 文字型の文字列。|
|`CAtlStringW`|CRT をサポートしない Unicode 文字型文字列。|
|`CAtlString`|CRT をサポートしない ANSI 文字型と Unicode 文字型の両方。|

ATL_CSTRING_NO_CRTが定義されていないプロジェクトでは、次の文字列型を使用できます。

|タイプ|宣言|
|-------------------|-----------------|
|`CAtlStringA`|CRT をサポートする ANSI 文字型の文字列。|
|`CAtlStringW`|CRT をサポートする Unicode 文字型の文字列。|
|`CAtlString`|CRT をサポートする ANSI 文字型と Unicode 文字型の両方。|

`CString`オブジェクトには、次の特性もあります。

- `CStringT`連結操作の結果としてオブジェクトが拡大する可能性があります。

- `CStringT`オブジェクトは"値のセマンティクス" に従います。 オブジェクトは`CStringT`、文字列へのポインタではなく、実際の文字列と考えてください。

- 関数の引数の`CStringT`代わりに`PCXSTR`オブジェクトを自由に使用できます。

- 文字列バッファーのカスタム メモリ管理。 詳細については、「[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="cstringt-predefined-types"></a>CStringT 定義済み型

テンプレート`CStringT`引数を使用して、サポートされる文字タイプ[(wchar_t](../../c-runtime-library/standard-types.md)または[char)](../../c-runtime-library/standard-types.md)を定義するため、メソッドのパラメーター型は複雑になることがあります。 この問題を簡単にするために、定義済みの型のセットが定義され、クラス全体`CStringT`で使用されます。 次の表に、さまざまな種類を示します。

|名前|説明|
|----------|-----------------|
|`XCHAR`|`CStringT`オブジェクトと同じ文字型を持つ単一の文字 **(wchar_t**または**char)。**|
|`YCHAR`|`CStringT`オブジェクトに反対の文字型を持つ単一の文字 **(wchar_t**または**char)。**|
|`PXSTR`|オブジェクトと同じ文字型の文字列 **(wchar_t**または**char)** へのポインター。 `CStringT`|
|`PYSTR`|オブジェクトに反対の文字型を持つ文字列 **(wchar_t**または char) へのポインター。 **char** `CStringT`|
|`PCXSTR`|オブジェクトと同じ文字型を持つ**const**文字列 **(wchar_t**または**char)** へのポインター。 `CStringT`|
|`PCYSTR`|オブジェクトに対する文字型を持つ**const**文字列 **(wchar_t**または**char)** へのポインター。 `CStringT`|

> [!NOTE]
> ドキュメント化されていないメソッド`CString`( など`AssignCopy`) を使用していたコードは、 または`CStringT``GetBuffer``ReleaseBuffer`など、 の次のドキュメント化されたメソッドを使用するコードに置き換える必要があります。 これらのメソッドは`CSimpleStringT`から継承されます。

## <a name="inheritance-hierarchy"></a>継承階層

[をクリックします。](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>必要条件

|ヘッダー|用途|
|------------|-------------|
|文字列.h|MFC のみの文字列オブジェクト|
|atlstr.h|非 MFC 文字列オブジェクト|

## <a name="cstringtallocsysstring"></a><a name="allocsysstring"></a>を返します。

タイプ BSTR のオートメーション互換文字列を割り当て、オブジェクトの内容`CStringT`(終端の null 文字を含む) をその型にコピーします。

```
BSTR AllocSysString() const;
```

### <a name="return-value"></a>戻り値

新しく割り当てられた文字列。

### <a name="remarks"></a>解説

MFC プログラムでは、メモリが不足している場合は[CMemoryException クラス](../../mfc/reference/cmemoryexception-class.md)がスローされます。 ATL プログラムでは[、CAtlException](../../atl/reference/catlexception-class.md)がスローされます。 この関数は、通常、オートメーションの文字列を返すために使用されます。

通常、この文字列が [in] パラメータとして COM 関数に渡される場合、呼び出し元は文字列を解放する必要があります。 これは、Windows SDK で説明されているように[、SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)を使用して行うことができます。 詳細については、「 [BSTR のメモリの割り当てと解放](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)」を参照してください。

Windows の OLE 割り当て関数の詳細については、Windows SDK の[「SysAllocString」](/windows/win32/api/oleauto/nf-oleauto-sysallocstring)を参照してください。

### <a name="example"></a>例

次の例は、`CStringT::AllocSysString` の使い方を示しています。

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

## <a name="cstringtansitooem"></a><a name="ansitooem"></a>Cストリングト::アンシトオーム

この`CStringT`オブジェクトのすべての文字を、ANSI 文字セットから OEM 文字セットに変換します。

```
void AnsiToOem();
```

### <a name="remarks"></a>解説

_UNICODEが定義されている場合、この関数は使用できません。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

## <a name="cstringtappendformat"></a><a name="appendformat"></a>を指定します。

既存`CStringT`のオブジェクトに書式付きデータを追加します。

```
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>パラメーター

*フォーマット*<br/>
書式制御文字列。

*データを持つ*<br/>
書式制御文字列を含む文字列リソース識別子。

*引数*<br/>
省略可能な引数。

### <a name="remarks"></a>解説

この関数は、一連の文字と値をフォーマットして追加`CStringT`します。 オプションの各引数 (存在する場合) は *、pszFormat*の対応するフォーマット指定に従って、または*nFormatID*で識別される文字列リソースに従って変換され、追加されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

## <a name="cstringtcollate"></a><a name="collate"></a>コレート

汎用テキスト関数`_tcscoll`を使用して 2 つの文字列を比較します。

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
比較に使用するもう 1 つの文字列。

### <a name="return-value"></a>戻り値

文字列が同じ場合は 0 を<、この`CStringT`オブジェクトが psz より小さい場合は 0 を、この`CStringT`オブジェクトが*psz*より大きい場合は 0 を>。 *psz*

### <a name="remarks"></a>解説

TCHAR で定義`_tcscoll`されている汎用テキスト関数。H は、コンパイル`strcoll`時`wcscoll`に定義`_mbscoll`された文字セットに応じて、 、 、 、 、 のいずれかにマップされます。 各関数は、現在使用されているコード ページに従って、大文字と小文字を区別して文字列を比較します。 詳細については、 [strcoll、 wcscoll、 _mbscoll、 _strcoll_l、 _wcscoll_l、 _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)を参照してください。

## <a name="cstringtcollatenocase"></a><a name="collatenocase"></a>コレットノケース

汎用テキスト関数`_tcscoll`を使用して 2 つの文字列を比較します。

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
比較に使用するもう 1 つの文字列。

### <a name="return-value"></a>戻り値

文字列が同一の場合は 0 (大文字小文字を無視`CStringT`)、このオブジェクトが psz より小さい場合は 0 `CStringT` (大文字小文字を無視)、このオブジェクトが*psz*より大きい場合は 0 を> (大文字小文字は無視します) を<します。 *psz*

### <a name="remarks"></a>解説

TCHAR で定義`_tcscoll`されている汎用テキスト関数。H は、コンパイル`stricoll`時`wcsicoll`に定義`_mbsicoll`された文字セットに応じて、 、 、 、 、 のいずれかにマップされます。 各関数は、現在使用されているコード ページに従って、文字列の大文字と小文字を区別しない比較を実行します。 詳細については、 [strcoll、 wcscoll、 _mbscoll、 _strcoll_l、 _wcscoll_l、 _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

## <a name="cstringtcompare"></a><a name="compare"></a>比較

2 つの文字列を比較します (大文字と小文字を区別します)。

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
比較に使用するもう 1 つの文字列。

### <a name="return-value"></a>戻り値

文字列が同じ場合は 0 を<、この`CStringT`オブジェクトが psz より小さい場合は 0 を、この`CStringT`オブジェクトが*psz*より大きい場合は 0 を>。 *psz*

### <a name="remarks"></a>解説

TCHAR で定義`_tcscmp`されている汎用テキスト関数。H は、コンパイル`strcmp`時`wcscmp`に定義`_mbscmp`された文字セットに応じて、 、 、 、 、 のいずれかにマップされます。 各関数は、大文字と小文字を区別して文字列を比較し、ロケールの影響を受けません。 詳細については、 [strcmp、 wcscmp、 _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)を参照してください。

文字列に埋め込み null が含まれている場合、比較のために文字列は最初の埋め込み null 文字で切り捨てられると見なされます。

### <a name="example"></a>例

次の例は、`CStringT::Compare` の使い方を示しています。

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

## <a name="cstringtcomparenocase"></a><a name="comparenocase"></a>クストレット::比較なし大文字と小文字

2 つの文字列を比較します (大文字と小文字は区別されません)。

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>パラメーター

*psz*<br/>
比較に使用するもう 1 つの文字列。

### <a name="return-value"></a>戻り値

文字列が同一 (大文字小文字は無視) の場合は`CStringT`0 を<し、このオブジェクトが*psz*より小`CStringT`さい場合は 0 を<(大文字小文字は無視)、このオブジェクトが*psz*より大きい場合は 0 を>(大文字小文字は無視)。

### <a name="remarks"></a>解説

TCHAR で定義`_tcsicmp`されている汎用テキスト関数。H は、コンパイル`_stricmp`時`_wcsicmp`に`_mbsicmp`定義された文字セットに応じて、 または のいずれかにマップされます。 各関数は、大文字と小文字を区別しない文字列の比較を実行します。 比較はロケールのLC_CTYPEの側面によって異なりますが、LC_COLLATEではありません。 詳細については、「 [_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l」](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

## <a name="cstringtcstringt"></a><a name="cstringt"></a>Cストリング::Cストリング

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

*Pch*<br/>
長さ*nLength*の文字の配列へのポインター。

*nレングス*<br/>
*pch*内の文字数。

*Ch*<br/>
1 文字。

*pszSrc*<br/>
この`CStringT`オブジェクトにコピーされる null で終わる文字列。

*をクリックします。*<br/>
`CStringT`オブジェクトのメモリ マネージャーへのポインター。 のメモリ管理と`IAtlStringMgr`メモリ管理の詳細`CStringT`については、「 [CStringT を使用したメモリ管理](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

*ストルスク*<br/>
この`CStringT`オブジェクト`CStringT`にコピーされる既存のオブジェクト。 および`CThisString``CThisSimpleString`の詳細については、「 」を参照してください。

*varSrc*<br/>
この`CStringT`オブジェクトにコピーされるバリアントオブジェクト。

*BaseType*<br/>
文字列クラスの文字型。 以下のいずれかを指定できます。

**char** (ANSI 文字列の場合)。

**wchar_t** (Unicode 文字列の場合)

TCHAR (ANSI および Unicode 文字列の両方の場合)。

*をクリックします。*<br/>
プロジェクトが MFC DLL (TRUE) かどうかを指定するブール値 (FALSE)。

*システム文字列*<br/>
で、`System::String`プロジェクトは /clr でコンパイルする必要があります。

*をクリックします。*<br/>
`CStringT`オブジェクトのハンドル。

### <a name="remarks"></a>解説

コンストラクターは、入力データを新しく割り当てられた記憶域にコピーするため、メモリ例外が発生する可能性があることに注意してください。 これらのコンストラクタの一部は変換関数として機能します。 これにより、`CStringT`たとえば、オブジェクトが予期される LPTSTR に置き換えることができます。

- `CStringT`( `LPCSTR` `lpsz` ): ANSI`CStringT`文字列からユニコードを構築します。 このコンストラクターを使用して、次の例に示すように文字列リソースを読み込むこともできます。

- `CStringT(`): Unicode`CStringT`文字列からを構築します。 `LPCWSTR` `lpsz`

- `CStringT`( `const unsigned char*` `psz` ):**符号なし** `CStringT` char へのポインタから を構築できます。

> [!NOTE]
> anSI 文字列と Unicode 文字列の間の暗黙的な文字列変換を無効にする_CSTRING_DISABLE_NARROW_WIDE_CONVERSION マクロを定義します。 マクロは、変換をサポートするコンパイル コンストラクターから除外されます。

*strSrc*パラメーターは、a または`CStringT``CThisSimpleString`オブジェクトのいずれかであることに注意してください。 の`CStringT`場合は、デフォルトのインスタンスの 1 つ`CString` `CStringA`( `CStringW`、 、または ) を使用します。に`CThisSimpleString`対しては **、this**ポインターを使用します。 `CThisSimpleString`は、クラスよりも組み込み機能が少ない小さい文字列クラスである[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)クラスのインスタンス`CStringT`を宣言します。

オーバーロード演算子`CSimpleStringT<>&()`は、宣言から`CStringT`オブジェクトを構築`CSimpleStringT`します。

> [!NOTE]
> null 文字が埋め`CStringT`込まれたインスタンスを作成することは可能ですが、この文字に対しては推奨します。 null 文字が埋`CStringT`め込まれたオブジェクトに対してメソッドと演算子を呼び出すと、意図しない結果が生じる可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

## <a name="cstringtcstringt"></a><a name="_dtorcstringt"></a>::~CStringT

`CStringT` オブジェクトを破棄します。

```
~CStringT() throw();
```

### <a name="remarks"></a>解説

`CStringT` オブジェクトを破棄します。

## <a name="cstringtdelete"></a><a name="delete"></a>CStringT::Dエレテ

指定したインデックス位置にある文字で始まる文字列から 1 つまたは 1 つの文字を削除します。

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
削除するオブジェクトの最初の文字の`CStringT`0 から始まるインデックス。

*nカウント*<br/>
削除する文字数。

### <a name="return-value"></a>戻り値

変更された文字列の長さ。

### <a name="remarks"></a>解説

*nCount*が文字列より長い場合、文字列の残りの部分は削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

## <a name="cstringtfind"></a><a name="find"></a>検索

この文字列を検索して、文字または部分文字列の最初の一致を検索します。

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
検索する部分文字列。

*Istart*<br/>
検索を開始する文字列内の文字のインデックス。または先頭から開始する場合は 0。

*Ch*<br/>
検索する 1 文字。

### <a name="return-value"></a>戻り値

要求されたサブストリングまたは文字に一致する、`CStringT`このオブジェクトの最初の文字の 0 から始まるインデックス。サブストリングまたは文字が見つからない場合は -1。

### <a name="remarks"></a>解説

この関数は、単一の文字 ( ランタイム関数`strchr`に似ています ) と文字列 (`strstr`に似ています ) の両方を受け入れるようにオーバーロードされます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

## <a name="cstringtfindoneof"></a><a name="findoneof"></a>クストレット::検索ワンOf

この文字列を検索して *、pszCharSet*に含まれる任意の文字と一致する最初の文字を検索します。

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>パラメーター

*を設定します。*<br/>
一致する文字を含む文字列。

### <a name="return-value"></a>戻り値

この文字列の最初の文字の 0 から始まるインデックスで *、pszCharSet*内のインデックスは 0 です。一致するものがない場合は -1。

### <a name="remarks"></a>解説

*pszCharSet*で最初に出現する文字を検索します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

## <a name="cstringtformat"></a><a name="format"></a>フォーマット

書式付きデータを`CStringT`[、sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)が C スタイルの文字配列にデータを書式設定するのと同じ方法で、書式指定されたデータを書き込みます。

```
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>パラメーター

*データを持つ*<br/>
書式制御文字列を含む文字列リソース識別子。

*フォーマット*<br/>
書式制御文字列。

*引数*<br/>
省略可能な引数。

### <a name="remarks"></a>解説

この関数は、一連の文字と値をフォーマットして`CStringT`格納します。 オプションの各引数 (存在する場合) は *、pszFormat*の対応するフォーマット指定に従って、または*nFormatID*で識別される文字列リソースに従って変換され、出力されます。

文字列オブジェクト自体が パラメータとして提供されている場合、呼び出し`Format`は失敗します。 たとえば、次のコードは予測できない結果を引き起こします。

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

詳細については、「[書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」をご覧ください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

## <a name="cstringtformatmessage"></a><a name="formatmessage"></a>をクリックします。

メッセージ文字列をフォーマットします。

```
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>パラメーター

*データを持つ*<br/>
書式設定されていないメッセージ テキストを含む文字列リソース識別子。

*フォーマット*<br/>
書式制御文字列へのポイント。 挿入用にスキャンされ、それに応じてフォーマットされます。 書式指定文字列は、実行時関数*printf*-style 書式指定文字列に似ていますが、パラメーターを任意の順序で挿入できる点が異なります。

*引数*<br/>
省略可能な引数。

### <a name="remarks"></a>解説

この関数は、入力としてメッセージ定義を必要とします。 メッセージ定義は *、pszFormat*によって、または*nFormatID*で識別される文字列リソースから決定されます。 この関数は、フォーマットされたメッセージ・テキストを`CStringT`オブジェクトにコピーし、要求された場合は埋め込み挿入シーケンスを処理します。

> [!NOTE]
> `FormatMessage`新しくフォーマットされた文字列にシステム メモリを割り当てようとします。 この試行が失敗すると、メモリ例外が自動的にスローされます。

各挿入には *、pszFormat*または*nFormatID*パラメーターの後に対応するパラメーターが必要です。 メッセージ テキスト内では、メッセージを動的にフォーマットするためにいくつかのエスケープ シーケンスがサポートされています。 詳細については、Windows SDK の Windows[形式のメッセージ](/windows/win32/api/winbase/nf-winbase-formatmessage)関数を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

## <a name="cstringtformatmessagev"></a><a name="formatmessagev"></a>をクリックします。

可変引数リストを使用してメッセージ文字列をフォーマットします。

```
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>パラメーター

*フォーマット*<br/>
書式制御文字列へのポイント。 挿入用にスキャンされ、それに応じてフォーマットされます。 書式指定文字列は、実行時関数`printf`-style 書式指定文字列に似ていますが、パラメーターを任意の順序で挿入できる点が異なります。

*一覧*<br/>
引数のリストへのポインター。

### <a name="remarks"></a>解説

この関数は *、pszFormat*によって決定される入力としてメッセージ定義を必要とします。 この関数は、書式設定されたメッセージ・テキストと可変引数リストを`CStringT`オブジェクトにコピーし、要求された場合は埋め込み挿入シーケンスを処理します。

> [!NOTE]
> `FormatMessageV`呼び出し[CStringT::FormatMessage](#formatmessage)は、新しく書式設定された文字列のシステム メモリを割り当てようとします。 この試行が失敗すると、メモリ例外が自動的にスローされます。

詳細については、Windows SDK の Windows[形式のメッセージ](/windows/win32/api/winbase/nf-winbase-formatmessage)関数を参照してください。

## <a name="cstringtformatv"></a><a name="formatv"></a>Cストリング::フォーマットV

可変引数リストを使用してメッセージ文字列をフォーマットします。

```
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>パラメーター

*フォーマット*<br/>
書式制御文字列へのポイント。 挿入用にスキャンされ、それに応じてフォーマットされます。 書式指定文字列は、実行時関数`printf`-style 書式指定文字列に似ていますが、パラメーターを任意の順序で挿入できる点が異なります。

*Args*<br/>
引数のリストへのポインター。

### <a name="remarks"></a>解説

書式付き文字列と引数の変数リストを、データを`CStringT`C 形式の文字`vsprintf_s`配列に書式設定するのと同じ方法で文字列に書き込みます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

## <a name="cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a>変数を取得します。

指定した環境変数の値に文字列を設定します。

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>パラメーター

*pszVar*<br/>
環境変数を指定する NULL で終わる文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

呼び出し元プロセスの環境ブロックから、指定した変数の値を取得します。 値は、NULL で終わる文字ストリングの形式です。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

## <a name="cstringtinsert"></a><a name="insert"></a>挿入

文字列内の指定されたインデックスに、1 つの文字または部分文字列を挿入します。

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
挿入が行われる前の文字のインデックス。

*psz*<br/>
挿入する部分文字列へのポインター。

*Ch*<br/>
挿入する文字。

### <a name="return-value"></a>戻り値

変更された文字列の長さ。

### <a name="remarks"></a>解説

*iIndex*パラメーターは、文字または部分文字列用の領域を作成するために移動される最初の文字を識別します。 *nIndex が*0 の場合、挿入は文字列全体の前に行われます。 *nIndex*が文字列の長さより大きい場合、関数は現在の文字列と*ch*または*psz*で提供される新しいマテリアルを連結します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

## <a name="cstringtleft"></a><a name="left"></a>CStringT::左

この`CStringT`オブジェクトから左端の*nCount*文字を抽出し、抽出された部分文字列のコピーを返します。

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>パラメーター

*nカウント*<br/>
この `CStringT` オブジェクトから抽出する文字数。

### <a name="return-value"></a>戻り値

指定の文字範囲のコピーを含む `CStringT` オブジェクト。 返された `CStringT` オブジェクトは空の場合があります。

### <a name="remarks"></a>解説

*nCount*が文字列の長さを超える場合は、文字列全体が抽出されます。 `Left` は、Basic `Left` 関数に類似します。

マルチバイト文字セット (MBCS) の場合 *、nCount*は 8 ビットの各シーケンスを文字として扱うので *、nCount*はマルチバイト文字の数に 2 を掛けた数を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

## <a name="cstringtloadstring"></a><a name="loadstring"></a>を文字列として使用します。

*nID*で識別される Windows 文字列リソースを既存`CStringT`のオブジェクトに読み込みます。

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>パラメーター

*hInstance*<br/>
モジュールのインスタンスへのハンドル。

*nID*<br/>
Windows 文字列リソース ID。

*言語 ID*<br/>
文字列リソースの言語。

### <a name="return-value"></a>戻り値

リソースの読み込みが成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

指定された言語 (*wLanguage*) を使用して、指定されたモジュール (*hInstance*) から文字列リソース (*nID*) を読み込みます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

## <a name="cstringtmakelower"></a><a name="makelower"></a>Cストリング::メイクローワー

オブジェクトを`CStringT`小文字の文字列に変換します。

```
CStringT& MakeLower();
```

### <a name="return-value"></a>戻り値

結果の小文字の文字列。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

## <a name="cstringtmakereverse"></a><a name="makereverse"></a>Cストリング::メイクリバース

オブジェクト内の文字の順序を`CStringT`反転します。

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>戻り値

結果として得られる反転した文字列。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

## <a name="cstringtmakeupper"></a><a name="makeupper"></a>CStringT::メイクアッパー

オブジェクトを`CStringT`大文字の文字列に変換します。

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>戻り値

結果の大文字の文字列。

### <a name="remarks"></a>解説

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

## <a name="cstringtmid"></a><a name="mid"></a>CStringT::ミッド

この`CStringT`オブジェクトから、*位置 iFirst* (0 から始まる) から長さ*nCount*文字の部分文字列を抽出します。

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>パラメーター

*iファーストファースト*<br/>
抽出された部分文字列に含まれる、この`CStringT`オブジェクトの最初の文字の 0 から始まるインデックス。

*nカウント*<br/>
この `CStringT` オブジェクトから抽出する文字数。 このパラメーターが指定されていない場合は、文字列の残りの部分が抽出されます。

### <a name="return-value"></a>戻り値

指定の文字範囲のコピーを含む `CStringT` オブジェクト。 返される`CStringT`オブジェクトは空である可能性があります。

### <a name="remarks"></a>解説

この関数は、抽出された部分文字列のコピーを返します。 `Mid`は基本の Mid 関数と似ています (Basic のインデックスは 1 からベースです)。

マルチバイト文字セット (MBCS) の場合 *、nCount*は 8 ビット文字をそれぞれ参照します。つまり、1 つのマルチバイト文字のリードバイトとトレイルバイトは 2 文字としてカウントされます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

## <a name="cstringtoemtoansi"></a><a name="oemtoansi"></a>CStringT::OemToAnsi

この`CStringT`オブジェクトのすべての文字を OEM 文字セットから ANSI 文字セットに変換します。

```
void OemToAnsi();
```

### <a name="remarks"></a>解説

この関数は、_UNICODEが定義されている場合は使用できません。

### <a name="example"></a>例

[の](#ansitooem)例を参照してください。

## <a name="cstringtoperator-"></a><a name="operator_eq"></a>演算子 =

文字列に新しい値を割り当てます。

```
CStringT& operator=(const CStringT& strSrc);

template<bool bMFCDLL>
CStringT& operator=(const CSimpleStringT<BaseType, bMFCDLL>& str);

CStringT& operator=(PCXSTR pszSrc);
CStringT& operator=(PCYSTR pszSrc);
CStringT& operator=(const unsigned char* pszSrc);
CStringT& operator=(XCHAR ch);
CStringT& operator=(YCHAR ch);
CStringT& operator=(const VARIANT& var);
```

### <a name="parameters"></a>パラメーター

*ストルスク*<br/>
この`CStringT`文字列に代入する。

*Str*<br/>
`CThisSimpleString` オブジェクトへの参照です。

*をクリックします。*<br/>
プロジェクトが MFC DLL であるかどうかを指定するブール値。

*BaseType*<br/>
文字列の基本型。

*Var*<br/>
この文字列に割り当てるバリアントオブジェクト。

*Ch*<br/>
文字列に割り当てる ANSI 文字または Unicode 文字。

*pszSrc*<br/>
割り当てられる元の文字列へのポインター。

### <a name="remarks"></a>解説

代入演算子は、別`CStringT`のオブジェクト、文字ポインター、または 1 文字を受け入れます。 この演算子を使用すると、新しい記憶域を割り当てることができるため、メモリ例外が発生する可能性があることに注意してください。

`CThisSimpleString`の詳細については[、CStringT::CStringT](#cstringt)の解説セクションを参照してください。

> [!NOTE]
> null 文字が埋め`CStringT`込まれたインスタンスを作成することは可能ですが、この文字に対しては推奨します。 null 文字が埋`CStringT`め込まれたオブジェクトに対してメソッドと演算子を呼び出すと、意図しない結果が生じる可能性があります。

## <a name="cstringtoperator-"></a><a name="operator_add"></a>CStringT::演算子 +

2 つの文字列または文字列と文字列を連結します。

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

*ch1*<br/>
文字列と連結する ANSI 文字または Unicode 文字。

*ch2*<br/>
文字列と連結する ANSI 文字または Unicode 文字。

*str1*<br/>
文字列`CStringT`または文字と連結する。

*str2*<br/>
文字列`CStringT`または文字と連結する。

*psz1*<br/>
文字列または文字と連結する null で終わる文字列へのポインター。

*psz2*<br/>
文字列または文字と連結する文字列へのポインター。

### <a name="remarks"></a>解説

関数には 7 つのオーバーロード`CStringT::operator+`形式があります。 最初のバージョンは、2 つの既存`CStringT`のオブジェクトを連結します。 次の 2 つは`CStringT`、オブジェクトと null で終わる文字列を連結します。 次の 2 つは`CStringT`、オブジェクトと ANSI 文字を連結します。 最後の 2 つは`CStringT`、オブジェクトと Unicode 文字を連結します。

> [!NOTE]
> null 文字が埋め`CStringT`込まれたインスタンスを作成することは可能ですが、この文字に対しては推奨します。 null 文字が埋`CStringT`め込まれたオブジェクトに対してメソッドと演算子を呼び出すと、意図しない結果が生じる可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_add_eq"></a>CStringT::演算子 +=

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

*Str*<br/>
`CThisSimpleString` オブジェクトへの参照です。

*をクリックします。*<br/>
プロジェクトが MFC DLL であるかどうかを指定するブール値。

*BaseType*<br/>
文字列の基本型。

*Var*<br/>
この文字列に連結するバリアント オブジェクト。

*Ch*<br/>
文字列と連結する ANSI 文字または Unicode 文字。

*pszSrc*<br/>
連結される元の文字列へのポインター。

*ストルスク*<br/>
この`CStringT`文字列に連結する A。

### <a name="remarks"></a>解説

この演算子は、別`CStringT`のオブジェクト、文字ポインター、または 1 文字を受け取ります。 この連結演算子を使用すると、この`CStringT`オブジェクトに追加される文字に新しい記憶域を割り当てることができるため、メモリ例外が発生する可能性があることに注意してください。

`CThisSimpleString`の詳細については[、CStringT::CStringT](#cstringt)の解説セクションを参照してください。

> [!NOTE]
> null 文字が埋め`CStringT`込まれたインスタンスを作成することは可能ですが、この文字に対しては推奨します。 null 文字が埋`CStringT`め込まれたオブジェクトに対してメソッドと演算子を呼び出すと、意図しない結果が生じる可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_eq_eq"></a>==

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

*ch1*<br/>
比較用の ANSI 文字またはユニコード文字。

*ch2*<br/>
比較用の ANSI 文字またはユニコード文字。

*str1*<br/>
比較`CStringT`用の A。

*str2*<br/>
比較`CStringT`用の A。

*psz1*<br/>
比較用の null で終わる文字列へのポインター。

*psz2*<br/>
比較用の null で終わる文字列へのポインター。

### <a name="remarks"></a>解説

左側の文字列または文字が右側の文字列または文字と等しいかどうかをテストし、それに応じて TRUE または FALSE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_neq"></a>演算子を使用します。

2 つの文字列が論理的に等しくないかどうかを判断します。

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

*ch1*<br/>
文字列と連結する ANSI 文字または Unicode 文字。

*ch2*<br/>
文字列と連結する ANSI 文字または Unicode 文字。

*str1*<br/>
比較`CStringT`用の A。

*str2*<br/>
比較`CStringT`用の A。

*psz1*<br/>
比較用の null で終わる文字列へのポインター。

*psz2*<br/>
比較用の null で終わる文字列へのポインター。

### <a name="remarks"></a>解説

左側の文字列または文字が右側の文字列または文字と等しくないかどうかをテストします。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt"></a>演算子&lt;

演算子の左側の文字列が右側の文字列より小さいかどうかを判断します。

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
比較`CStringT`用の A。

*str2*<br/>
比較`CStringT`用の A。

*psz1*<br/>
比較用の null で終わる文字列へのポインター。

*psz2*<br/>
比較用の null で終わる文字列へのポインター。

### <a name="remarks"></a>解説

文字列間の辞書的な比較、文字ごとの次の場合:

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt"></a>演算子&gt;

演算子の左側の文字列が右側の文字列より大きいかどうかを判断します。

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
比較`CStringT`用の A。

*str2*<br/>
比較`CStringT`用の A。

*psz1*<br/>
比較用の null で終わる文字列へのポインター。

*psz2*<br/>
比較用の null で終わる文字列へのポインター。

### <a name="remarks"></a>解説

文字列間の辞書的な比較、文字ごとの次の場合:

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt_eq"></a>演算子&lt;=

演算子の左側の文字列が右側の文字列以下かどうかを判断します。

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
比較`CStringT`用の A。

*str2*<br/>
比較`CStringT`用の A。

*psz1*<br/>
比較用の null で終わる文字列へのポインター。

*psz2*<br/>
比較用の null で終わる文字列へのポインター。

### <a name="remarks"></a>解説

文字列間の辞書的な比較、文字ごとの次の場合:

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt_eq"></a>演算子&gt;=

演算子の左側の文字列が右側の文字列以上かどうかを判断します。

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
比較`CStringT`用の A。

*str2*<br/>
比較`CStringT`用の A。

*psz1*<br/>
比較対象の文字列へのポインター。

*psz2*<br/>
比較対象の文字列へのポインター。

### <a name="remarks"></a>解説

文字列間の辞書的な比較、文字ごとの次の場合:

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

## <a name="cstringtremove"></a><a name="remove"></a>をクリックします。

指定した文字のすべてのインスタンスを文字列から削除します。

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>パラメーター

*ch削除*<br/>
文字列から削除する文字。

### <a name="return-value"></a>戻り値

文字列から削除された文字数。 文字列が変更されない場合は 0。

### <a name="remarks"></a>解説

文字の比較では、大文字と小文字が区別されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

## <a name="cstringtreplace"></a><a name="replace"></a>置き換え

には 2 つの`Replace`バージョンがあります。最初のバージョンでは、別の部分文字列を使用して、部分文字列の 1 つ以上のコピーを置き換えます。 両方の部分文字列は null で終わる。 2 番目のバージョンでは、1 つ以上の文字のコピーが別の文字を使用して置き換えられます。 どちらのバージョンも、 に格納されている文字`CStringT`データに対して動作します。

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>パラメーター

*プシュオールド*<br/>
*pszNew*に置き換えられる null で終わる文字列へのポインター。

*psz新しい*<br/>
*pszOld*を置き換える null で終わる文字列へのポインター。

*チョルド*<br/>
*chNew*に置き換えられる文字。

*chNew*<br/>
*chOld*を置き換える文字。

### <a name="return-value"></a>戻り値

文字列が変更されていない場合は、置換された文字列の数を返します。

### <a name="remarks"></a>解説

`Replace`*pszNew*と*pszOld*は同じ長さである必要はないため、文字列の長さを変更できます。 この関数は、大文字と小文字を区別して一致します。

インスタンスの`CStringT`例としては`CString`、 `CStringA`、`CStringW`および があります。

の`CStringA`場合`Replace`は、ANSI またはマルチバイト (MBCS) 文字で動作します。 の`CStringW`場合`Replace`は、ワイド文字で動作します。

の`CString`場合、次の表の定数が定義されているかどうかに基づいて、文字データ型がコンパイル時に選択されます。

|定義済み定数|文字データ型|
|----------------------|-------------------------|
|_UNICODE|ワイド文字|
|_MBCS|マルチバイト文字|
|[Neither]|1 バイト文字|
|両方|未定義。|

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

## <a name="cstringtreversefind"></a><a name="reversefind"></a>を見つける

この`CStringT`オブジェクトを検索して、文字の最後の一致を検索します。

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>パラメーター

*Ch*<br/>
検索する文字。

### <a name="return-value"></a>戻り値

要求された文字と一致するこの`CStringT`オブジェクトの最後の文字の 0 から始まるインデックス。

### <a name="remarks"></a>解説

この関数は、ランタイム関数`strrchr`に似ています。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

## <a name="cstringtright"></a><a name="right"></a>CStringT::右

この`CStringT`オブジェクトから最後の (右端) *nCount*文字を抽出し、抽出された部分文字列のコピーを返します。

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>パラメーター

*nカウント*<br/>
この `CStringT` オブジェクトから抽出する文字数。

### <a name="return-value"></a>戻り値

指定の文字範囲のコピーを含む `CStringT` オブジェクト。 返される`CStringT`オブジェクトは空にすることができます。

### <a name="remarks"></a>解説

*nCount*が文字列の長さを超える場合は、文字列全体が抽出されます。 `Right`は Basic`Right`関数と似ています (Basic のインデックスは 0 から始まるという点を除く)。

マルチバイト文字セット (MBCS) の場合 *、nCount*は 8 ビット文字をそれぞれ参照します。つまり、1 つのマルチバイト文字のリードバイトとトレイルバイトは 2 文字としてカウントされます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

## <a name="cstringtsetsysstring"></a><a name="setsysstring"></a>を文字列として使用します。

*pbstr*が指す BSTR を再割り当てし`CStringT`、NULL 文字を含むオブジェクトの内容をコピーします。

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>パラメーター

*pbstr*<br/>
文字列へのポインター。

### <a name="return-value"></a>戻り値

新しい文字列。

### <a name="remarks"></a>解説

`CStringT`オブジェクトの内容に応じて *、pbstr*によって参照される BSTR の値が変更される場合があります。 この関数は、メモリ`CMemoryException`が不足している場合に a をスローします。

この関数は通常、オートメーションの参照によって渡される文字列の値を変更するために使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

## <a name="cstringtspanexcluding"></a><a name="spanexcluding"></a>を除外します。

*pszCharSet*で識別される文字のセットにない最初の文字から始まる文字列から文字を抽出します。

```
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>パラメーター

*を設定します。*<br/>
文字のセットとして解釈される文字列。

### <a name="return-value"></a>戻り値

*文字列*内に含まれていない文字列の中で、文字列の先頭文字から始まり *、pszCharSet*にある文字列の最初の文字で終わる部分文字列です (つまり、文字列の最初の文字から始まり *、pszCharSet*が見つかった文字列の最初の文字を除きます)。 *pszCharSet*内の文字が文字列内に見つからない場合は、文字列全体を返します。

### <a name="remarks"></a>解説

`SpanExcluding`*pszCharSet*から最初に出現した文字の前にあるすべての文字を抽出して返します (つまり *、pszCharSet*の文字と、文字列内のその文字の後に続くすべての文字は返されません)。 *pszCharSet*の文字が文字列に見つからない場合は、`SpanExcluding`文字列全体を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

## <a name="cstringtspanincluding"></a><a name="spanincluding"></a>を含む

最初の文字から始まる文字列から *、pszCharSet*で識別される文字のセットにある文字を抽出します。

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>パラメーター

*を設定します。*<br/>
文字のセットとして解釈される文字列。

### <a name="return-value"></a>戻り値

文字列内の文字列内の文字を含む部分文字列で、文字列の最初の文字から始まり *、pszCharSet*に含まれていない文字列に文字が見つかると終わる部分文字列。 *pszCharSet* `SpanIncluding`文字列の最初の文字が指定されたセットにない場合は、空の部分文字列を返します。

### <a name="remarks"></a>解説

文字列の最初の文字が文字セットにない場合`SpanIncluding`は、空の文字列を返します。 それ以外の場合は、セット内の連続する文字のシーケンスを返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

## <a name="cstringttokenize"></a><a name="tokenize"></a>トークン化

ターゲット文字列内の次のトークンを検索します。

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>パラメーター

*トークン*<br/>
トークン区切り記号を含む文字列。 これらの区切り文字の順序は重要ではありません。

*Istart*<br/>
検索を開始する 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

現在`CStringT`のトークン値を含むオブジェクト。

### <a name="remarks"></a>解説

この`Tokenize`関数は、ターゲット文字列内の次のトークンを検索します。 *pszTokens*の文字セットは、見つかるトークンの可能な区切り文字を指定します。 関数の`Tokenize`呼び出しのたびに*iStart*から開始し、先頭の区切り`CStringT`文字をスキップし、現在のトークンを含むオブジェクトを返します。 *iStart*の値は、終了区切り文字の後の位置に更新され、ストリングの終わりに達した場合は -1 になります。 iStart を使用して、次のトークンが読み取られる文字列の場所を`Tokenize`追跡するために*iStart*、ターゲット文字列の残りの部分からさらにトークンを分割できます。 トークンがなくなった場合、関数は空の文字列を返し *、iStart*は -1 に設定されます。

CRT トークン化関数とは異なり[、strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)などの`Tokenize`関数は、ターゲット文字列を変更しません。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>解説

この例の出力は次のとおりです。

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

## <a name="cstringttrim"></a><a name="trim"></a>CStringT::トリム

文字列の先頭文字と末尾文字をトリムします。

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>パラメーター

*chターゲット*<br/>
トリミングするターゲット文字。

*pszターゲット*<br/>
トリミングする対象の文字を含む文字列へのポインター。 *pszTarget*内の文字の先頭と末尾のすべての出現は`CStringT`、オブジェクトからトリムされます。

### <a name="return-value"></a>戻り値

トリミングされた文字列を返します。

### <a name="remarks"></a>解説

次のいずれかの先頭と末尾の出現をすべて削除します。

- *chTarget*で指定された文字。

- *pszTargets*で指定された文字列内のすべての文字が見つかりました。

- 空白。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>解説

この例の出力は次のとおりです。

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

## <a name="cstringttrimleft"></a><a name="trimleft"></a>CStringT::トリムレフト

文字列の先頭文字をトリムします。

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>パラメーター

*chターゲット*<br/>
トリミングするターゲット文字。

*pszターゲット*<br/>
トリミングする対象の文字を含む文字列へのポインター。 *pszTarget*の先頭文字はすべて`CStringT`オブジェクトからトリムされます。

### <a name="return-value"></a>戻り値

結果として得られるトリミングされた文字列。

### <a name="remarks"></a>解説

次のいずれかの先頭と末尾の出現をすべて削除します。

- *chTarget*で指定された文字。

- *pszTargets*で指定された文字列内のすべての文字が見つかりました。

- 空白。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

## <a name="cstringttrimright"></a><a name="trimright"></a>CStringT::トリムライト

文字列の末尾の文字をトリムします。

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>パラメーター

*chターゲット*<br/>
トリミングするターゲット文字。

*pszターゲット*<br/>
トリミングする対象の文字を含む文字列へのポインター。 *pszTarget*内の文字の末尾に出現するすべての文字は、`CStringT`オブジェクトからトリムされます。

### <a name="return-value"></a>戻り値

トリミングされた`CStringT`文字列を含むオブジェクトを返します。

### <a name="remarks"></a>解説

次のいずれかの末尾の出現を削除します。

- *chTarget*で指定された文字。

- *pszTargets*で指定された文字列内のすべての文字が見つかりました。

- 空白。

バージョン`CStringT& TrimRight(XCHAR chTarget)`は、1 文字のパラメーターを受け取り、文字列データの末尾から`CStringT`その文字のすべてのコピーを削除します。 文字列の末尾から始まり、前面に向かって動作します。 別の文字が見つかったり、文字データ`CSTringT`が不足したりすると、このコードは停止します。

バージョン`CStringT& TrimRight(PCXSTR pszTargets)`は、検索対象のすべての異なる文字を含む null で終わる文字列を受け入れます。 オブジェクト内のこれらの文字のすべてのコピーを`CStringT`削除します。 文字列の末尾から始まり、前面に向かって動作します。 ターゲット文字列にない文字を見つけたり、文字データが不足したりすると`CStringT`、このコードは停止します。 ターゲット文字列全体を`CStringT`の末尾の部分文字列に一致させようとはしません。

バージョン`CStringT& TrimRight()`にはパラメータは必要ありません。 文字列の末尾から末尾の空白文字を切り取ります`CStringT`。 空白文字は、改行、スペース、タブです。

-

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[CSimpleStringT クラス](../../atl-mfc-shared/reference/csimplestringt-class.md)
