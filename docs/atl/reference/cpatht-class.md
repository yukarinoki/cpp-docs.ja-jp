---
title: CPathT クラス
ms.date: 03/27/2019
f1_keywords:
- CPathT
- ATLPATH/ATL::CPathT
- ATLPATH/ATL::CPathT::PCXSTR
- ATLPATH/ATL::CPathT::PXSTR
- ATLPATH/ATL::CPathT::XCHAR
- ATLPATH/ATL::CPathT::CPathT
- ATLPATH/ATL::CPathT::AddBackslash
- ATLPATH/ATL::CPathT::AddExtension
- ATLPATH/ATL::CPathT::Append
- ATLPATH/ATL::CPathT::BuildRoot
- ATLPATH/ATL::CPathT::Canonicalize
- ATLPATH/ATL::CPathT::Combine
- ATLPATH/ATL::CPathT::CommonPrefix
- ATLPATH/ATL::CPathT::CompactPath
- ATLPATH/ATL::CPathT::CompactPathEx
- ATLPATH/ATL::CPathT::FileExists
- ATLPATH/ATL::CPathT::FindExtension
- ATLPATH/ATL::CPathT::FindFileName
- ATLPATH/ATL::CPathT::GetDriveNumber
- ATLPATH/ATL::CPathT::GetExtension
- ATLPATH/ATL::CPathT::IsDirectory
- ATLPATH/ATL::CPathT::IsFileSpec
- ATLPATH/ATL::CPathT::IsPrefix
- ATLPATH/ATL::CPathT::IsRelative
- ATLPATH/ATL::CPathT::IsRoot
- ATLPATH/ATL::CPathT::IsSameRoot
- ATLPATH/ATL::CPathT::IsUNC
- ATLPATH/ATL::CPathT::IsUNCServer
- ATLPATH/ATL::CPathT::IsUNCServerShare
- ATLPATH/ATL::CPathT::MakePretty
- ATLPATH/ATL::CPathT::MatchSpec
- ATLPATH/ATL::CPathT::QuoteSpaces
- ATLPATH/ATL::CPathT::RelativePathTo
- ATLPATH/ATL::CPathT::RemoveArgs
- ATLPATH/ATL::CPathT::RemoveBackslash
- ATLPATH/ATL::CPathT::RemoveBlanks
- ATLPATH/ATL::CPathT::RemoveExtension
- ATLPATH/ATL::CPathT::RemoveFileSpec
- ATLPATH/ATL::CPathT::RenameExtension
- ATLPATH/ATL::CPathT::SkipRoot
- ATLPATH/ATL::CPathT::StripPath
- ATLPATH/ATL::CPathT::StripToRoot
- ATLPATH/ATL::CPathT::UnquoteSpaces
- ATLPATH/ATL::CPathT::m_strPath
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
ms.openlocfilehash: 109f9baefd0e6775db05eeba8cb78542bf60a9ac
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565793"
---
# <a name="cpatht-class"></a>CPathT クラス

このクラスは、パスを表します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>パラメーター

*文字列型*<br/>
ATL と MFC の文字列クラスのパスを使用する (を参照してください[CStringT](../../atl-mfc-shared/reference/cstringt-class.md))。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CPathT::PCXSTR](#pcxstr)|文字列定数の型。|
|[CPathT::PXSTR](#pxstr)|文字列型です。|
|[CPathT::XCHAR](#xchar)|文字型。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CPathT::CPathT](#cpatht)|パスのコンス トラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPathT::AddBackslash](#addbackslash)|パスの正しい構文を作成する文字列の末尾に円記号を追加するには、このメソッドを呼び出します。|
|[CPathT::AddExtension](#addextension)|パスにファイル拡張子を追加するには、このメソッドを呼び出します。|
|[CPathT::Append](#append)|現在のパスに文字列を追加するには、このメソッドを呼び出します。|
|[CPathT::BuildRoot](#buildroot)|特定のドライブ番号からルート パスを作成するには、このメソッドを呼び出します。|
|[CPathT::Canonicalize](#canonicalize)|パスを正規の形式に変換するには、このメソッドを呼び出します。|
|[CPathT::Combine](#combine)|ディレクトリ名を表す文字列と、1 つのパスにファイルのパス名を表す文字列を連結するには、このメソッドを呼び出します。|
|[CPathT::CommonPrefix](#commonprefix)|指定されたパスが、現在のパスと共通プレフィックスを共有するかどうかを判断するには、このメソッドを呼び出します。|
|[CPathT::CompactPath](#compactpath)|パス コンポーネントを省略記号に置き換えることにより、指定したピクセル幅に収まるようにファイル パスを短くには、このメソッドを呼び出します。|
|[CPathT::CompactPathEx](#compactpathex)|パス コンポーネントを省略記号に置き換えることにより、指定した文字数に収まるようにファイル パスを短くには、このメソッドを呼び出します。|
|[CPathT::FileExists](#fileexists)|このパス名でファイルが存在するかどうかを確認するには、このメソッドを呼び出します。|
|[CPathT::FindExtension](#findextension)|パス内のファイル拡張子の位置を検索するには、このメソッドを呼び出します。|
|[CPathT::FindFileName](#findfilename)|パス内のファイル名の位置を検索するには、このメソッドを呼び出します。|
|[CPathT::GetDriveNumber](#getdrivenumber)|'A' から 'Z' の範囲内のドライブ文字のパスを検索し、対応するドライブの数を返すには、このメソッドを呼び出します。|
|[CPathT::GetExtension](#getextension)|パスからファイルの拡張子を取得するには、このメソッドを呼び出します。|
|[CPathT::IsDirectory](#isdirectory)|パスが有効なディレクトリであるかどうかを確認するには、このメソッドを呼び出します。|
|[CPathT::IsFileSpec](#isfilespec)|任意のパス区切り文字のパスを検索するには、このメソッドを呼び出す (たとえば、':' または '\\')。 パス区切り文字がない場合は、パスはファイルの仕様のパスと見なされます。|
|[CPathT::IsPrefix](#isprefix)|パスによって渡される型の有効なプレフィックスが含まれるかどうかを確認するには、このメソッドを呼び出す*pszPrefix*します。|
|[CPathT::IsRelative](#isrelative)|パスが相対かを判断するには、このメソッドを呼び出します。|
|[CPathT::IsRoot](#isroot)|パスがディレクトリのルートであるかを判断するには、このメソッドを呼び出します。|
|[CPathT::IsSameRoot](#issameroot)|別のパスが、共通のルート コンポーネントと現在のパスを持つかどうかを判断するには、このメソッドを呼び出します。|
|[CPathT::IsUNC](#isunc)|パスがサーバーの有効な UNC (汎用名前付け規則) パスであるかどうかを確認するには、このメソッドを呼び出すし、共有します。|
|[CPathT::IsUNCServer](#isuncserver)|パスがサーバーだけを表す有効な UNC (汎用名前付け規則) パスであるかどうかを確認するには、このメソッドを呼び出します。|
|[CPathT::IsUNCServerShare](#isuncservershare)|パスが有効な UNC (汎用名前付け規則) 共有パスであるかどうかを確認するには、このメソッドを呼び出す\\ \  *server*\ *共有*します。|
|[CPathT::MakePretty](#makepretty)|パスを一貫した外観のパスを指定する文字をすべて小文字に変換するには、このメソッドを呼び出します。|
|[CPathT::MatchSpec](#matchspec)|ワイルドカード一致の種類を含む文字列へのパスを検索するには、このメソッドを呼び出します。|
|[CPathT::QuoteSpaces](#quotespaces)|このメソッドでは、スペースが含まれている場合は、パスを引用符で囲みます。|
|[CPathT::RelativePathTo](#relativepathto)|1 つのファイルまたはフォルダーから別の相対パスを作成するには、このメソッドを呼び出します。|
|[CPathT::RemoveArgs](#removeargs)|パスからコマンドライン引数を削除するには、このメソッドを呼び出します。|
|[CPathT::RemoveBackslash](#removebackslash)|パスから、末尾に円記号を削除するには、このメソッドを呼び出します。|
|[CPathT::RemoveBlanks](#removeblanks)|パスからすべての先頭および末尾のスペースを削除するには、このメソッドを呼び出します。|
|[CPathT::RemoveExtension](#removeextension)|1 つを使用する必要がある場合は、パスからファイルの拡張子を削除するには、このメソッドを呼び出します。|
|[CPathT::RemoveFileSpec](#removefilespec)|それらがある場合は、パスからファイル名の末尾と円記号を削除するには、このメソッドを呼び出します。|
|[CPathT::RenameExtension](#renameextension)|このメソッドを呼び出して、新しい拡張機能で、パスにファイル名拡張子を置き換えます。 ファイル名に拡張機能が含まれていない場合、拡張機能は、文字列の末尾に添付されます。|
|[CPathT::SkipRoot](#skiproot)|ドライブ文字または UNC サーバー/共有のパス部分を無視して、パスを解析するには、このメソッドを呼び出します。|
|[CPathT::StripPath](#strippath)|完全修飾パスとファイル名のパス部分を削除するには、このメソッドを呼び出します。|
|[CPathT::StripToRoot](#striptoroot)|ただし、ルート情報、パスのすべての部分を削除するには、このメソッドを呼び出します。|
|[CPathT::UnquoteSpaces](#unquotespaces)|先頭とパスの末尾から引用符を削除するには、このメソッドを呼び出します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CPathT::operator const 文字列型 (& a)](#operator_const_stringtype_amp)|この演算子は、オブジェクトを文字列として扱うことができます。|
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|この演算子は、オブジェクトを文字列として扱うことができます。|
|[CPathT::operator 文字列型 (& a)](#operator_stringtype_amp)|この演算子は、オブジェクトを文字列として扱うことができます。|
|[CPathT::operator + =](#operator_add_eq)|この演算子は、パスに文字列を追加します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPathT::m_strPath](#m_strpath)|パス。|

## <a name="remarks"></a>Remarks

`CPath`、 `CPathA`、と`CPathW`のインスタンス化は`CPathT`次のように定義されています。

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlpath.h

##  <a name="addbackslash"></a>  CPathT::AddBackslash

パスの正しい構文を作成する文字列の末尾に円記号を追加するには、このメソッドを呼び出します。 パスは、末尾に円記号を既に持っている場合は、円記号は追加されません。

```
void AddBackslash();
```

### <a name="remarks"></a>Remarks

詳細については、[PathAddBackSlash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha)を参照してください。

##  <a name="addextension"></a>  CPathT::AddExtension

パスにファイル拡張子を追加するには、このメソッドを呼び出します。

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>パラメーター

*pszExtension*<br/>
追加するファイル拡張子。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona)を参照してください。

##  <a name="append"></a>  CPathT::Append

現在のパスに文字列を追加するには、このメソッドを呼び出します。

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>パラメーター

*pszMore*<br/>
追加する文字列。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda)を参照してください。

##  <a name="buildroot"></a>  CPathT::BuildRoot

特定のドライブ番号からルート パスを作成するには、このメソッドを呼び出します。

```
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>パラメーター

*ドライブ*<br/>
ドライブの数 (0 a: には、1 が b:、という具合)。

### <a name="remarks"></a>Remarks

詳細については、[PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota)を参照してください。

##  <a name="canonicalize"></a>  CPathT::Canonicalize

パスを正規の形式に変換するには、このメソッドを呼び出します。

```
void Canonicalize();
```

### <a name="remarks"></a>Remarks

詳細については、[PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea)を参照してください。

##  <a name="combine"></a>  CPathT::Combine

ディレクトリ名を表す文字列と、1 つのパスにファイルのパス名を表す文字列を連結するには、このメソッドを呼び出します。

```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>パラメーター

*pszDir*<br/>
ディレクトリのパス。

*pszFile*<br/>
ファイル パス。

### <a name="remarks"></a>Remarks

詳細については、[PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea)を参照してください。

##  <a name="commonprefix"></a>  CPathT::CommonPrefix

指定されたパスが、現在のパスと共通プレフィックスを共有するかどうかを判断するには、このメソッドを呼び出します。

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>パラメーター

*pszOther*<br/>
現在のものと比較するパス。

### <a name="return-value"></a>戻り値

一般的なプレフィックスを返します。

### <a name="remarks"></a>Remarks

プレフィックスでは、これらの型の 1 つです。"C:\\\\「,」.「,」..「,」..\\\\". 詳細については、[PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa)を参照してください。

##  <a name="compactpath"></a>  CPathT::CompactPath

パス コンポーネントを省略記号に置き換えることにより、指定したピクセル幅に収まるようにファイル パスを短くには、このメソッドを呼び出します。

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>パラメーター

*hDC*<br/>
フォント メトリックを使用するデバイス コンテキスト。

*nWidth*<br/>
幅 (ピクセル単位) に収まるように、文字列を強制されます。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha)を参照してください。

##  <a name="compactpathex"></a>  CPathT::CompactPathEx

パス コンポーネントを省略記号に置き換えることにより、指定した文字数に収まるようにファイル パスを短くには、このメソッドを呼び出します。

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>パラメーター

*nMaxChars*<br/>
終端の NULL 文字を含む、新しい文字列に含まれる文字の最大数。

*dwFlags*<br/>
予約済み。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa)を参照してください。

##  <a name="cpatht"></a>  CPathT::CPathT

コンストラクターです。

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>パラメーター

*pszPath*<br/>
パス文字列へのポインター。

*path*<br/>
パス文字列。

##  <a name="fileexists"></a>  CPathT::FileExists

このパス名でファイルが存在するかどうかを確認するには、このメソッドを呼び出します。

```
BOOL FileExists() const;
```

### <a name="return-value"></a>戻り値

かどうか、ファイルが存在するそれ以外の場合は TRUE を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa)を参照してください。

##  <a name="findextension"></a>  CPathT::FindExtension

パス内のファイル拡張子の位置を検索するには、このメソッドを呼び出します。

```
int FindExtension() const;
```

### <a name="return-value"></a>戻り値

位置を返します、"."前に、拡張機能。 拡張機能が見つからない場合は、-1 を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona)を参照してください。

##  <a name="findfilename"></a>  CPathT::FindFileName

パス内のファイル名の位置を検索するには、このメソッドを呼び出します。

```
int FindFileName() const;
```

### <a name="return-value"></a>戻り値

ファイル名の位置を返します。 ファイル名が見つからない場合は、-1 を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea)を参照してください。

##  <a name="getdrivenumber"></a>  CPathT::GetDriveNumber

'A' から 'Z' の範囲内のドライブ文字のパスを検索し、対応するドライブの数を返すには、このメソッドを呼び出します。

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>戻り値

ドライブ文字、または-1 がそれ以外の場合は、パスの場合に 0 ~ 25 (に対応する 'A' から 'Z') を整数としてドライブの数を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera)を参照してください。

##  <a name="getextension"></a>  CPathT::GetExtension

パスからファイルの拡張子を取得するには、このメソッドを呼び出します。

```
StringType GetExtension() const;
```

### <a name="return-value"></a>戻り値

ファイル拡張子を返します。

##  <a name="isdirectory"></a>  CPathT::IsDirectory

パスが有効なディレクトリであるかどうかを確認するには、このメソッドを呼び出します。

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>戻り値

パスがディレクトリの場合、FALSE それ以外の場合は、0 以外の値 (16) を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya)を参照してください。

##  <a name="isfilespec"></a>  CPathT::IsFileSpec

任意のパス区切り文字のパスを検索するには、このメソッドを呼び出す (たとえば、':' または '\\')。 パス区切り文字がない場合は、パスはファイルの仕様のパスと見なされます。

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>戻り値

パス内に、パス区切り文字がない場合は TRUE または FALSE の場合、パス区切り文字を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca)を参照してください。

##  <a name="isprefix"></a>  CPathT::IsPrefix

パスによって渡される型の有効なプレフィックスが含まれるかどうかを確認するには、このメソッドを呼び出す*pszPrefix*します。

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>パラメーター

*pszPrefix*<br/>
検索対象のプレフィックス。 プレフィックスでは、これらの型の 1 つです。"C:\\\\「,」.「,」..「,」..\\\\".

### <a name="return-value"></a>戻り値

パスが含まれる場合、プレフィックス、または FALSE それ以外の場合は、TRUE を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa)を参照してください。

##  <a name="isrelative"></a>  CPathT::IsRelative

パスが相対かを判断するには、このメソッドを呼び出します。

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>戻り値

絶対である場合、パスが相対パス、または FALSE の場合は TRUE を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea)を参照してください。

##  <a name="isroot"></a>  CPathT::IsRoot

パスがディレクトリのルートであるかを判断するには、このメソッドを呼び出します。

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>戻り値

パスはルート、または FALSE をそれ以外の場合がある場合は、TRUE を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota)を参照してください。

##  <a name="issameroot"></a>  CPathT::IsSameRoot

別のパスが、共通のルート コンポーネントと現在のパスを持つかどうかを判断するには、このメソッドを呼び出します。

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>パラメーター

*pszOther*<br/>
その他のパス。

### <a name="return-value"></a>戻り値

両方の文字列には、それ以外の場合するルート コンポーネントが同じ、または FALSE がある場合は TRUE を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota)を参照してください。

##  <a name="isunc"></a>  CPathT::IsUNC

パスがサーバーの有効な UNC (汎用名前付け規則) パスであるかどうかを確認するには、このメソッドを呼び出すし、共有します。

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>戻り値

パスは有効な UNC パスまたは FALSE をそれ以外の場合は TRUE を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca)を参照してください。

##  <a name="isuncserver"></a>  CPathT::IsUNCServer

パスがサーバーだけを表す有効な UNC (汎用名前付け規則) パスであるかどうかを確認するには、このメソッドを呼び出します。

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>戻り値

かどうか、文字列は有効なサーバーのみの UNC パス (共有を名前なし)、または FALSE それ以外の場合は TRUE を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera)を参照してください。

##  <a name="isuncservershare"></a>  CPathT::IsUNCServerShare

パスが有効な UNC (汎用名前付け規則) 共有パスであるかどうかを確認するには、このメソッドを呼び出す\\ \  *server*\ *共有*します。

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>戻り値

パスが、フォームの場合は TRUE を返します\\ \  *server*\ *共有*、FALSE またはそれ以外の場合。

### <a name="remarks"></a>Remarks

詳細については、[PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea)を参照してください。

##  <a name="m_strpath"></a>  CPathT::m_strPath

パス。

```
StringType m_strPath;
```

### <a name="remarks"></a>Remarks

`StringType` テンプレート パラメーターは、`CPathT`します。

##  <a name="makepretty"></a>  CPathT::MakePretty

パスを一貫した外観のパスを指定する文字をすべて小文字に変換するには、このメソッドを呼び出します。

```
BOOL MakePretty();
```

### <a name="return-value"></a>戻り値

それ以外の場合、パスが変換された場合は TRUE または FALSE を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya)を参照してください。

##  <a name="matchspec"></a>  CPathT::MatchSpec

ワイルドカード一致の種類を含む文字列へのパスを検索するには、このメソッドを呼び出します。

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>パラメーター

*pszSpec*<br/>
検索対象のファイルの種類に null で終わる文字列へのポインター。 たとえば、現在のパスにあるファイルは、DOC ファイル、かどうかをテストする*pszSpec*に設定する必要があります"* .doc"。

### <a name="return-value"></a>戻り値

それ以外の場合、文字列が一致する場合は TRUE または FALSE を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca)を参照してください。

##  <a name="operator_add_eq"></a>  CPathT::operator +=

この演算子は、パスに文字列を追加します。

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>パラメーター

*pszMore*<br/>
追加する文字列。

### <a name="return-value"></a>戻り値

更新されたパスを返します。

##  <a name="operator_const_stringtype_amp"></a>  CPathT::operator const 文字列型 &amp;

この演算子は、オブジェクトを文字列として扱うことができます。

```
operator const StringType&() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトによって管理されている現在のパスを表す文字列を返します。

##  <a name="operator_cpatht__pcxstr"></a>  CPathT::operator CPathT::PCXSTR

この演算子は、オブジェクトを文字列として扱うことができます。

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトによって管理されている現在のパスを表す文字列を返します。

##  <a name="operator_stringtype_amp"></a>  CPathT::operator 文字列型 &amp;

この演算子は、オブジェクトを文字列として扱うことができます。

```
operator StringType&() throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトによって管理されている現在のパスを表す文字列を返します。

##  <a name="pcxstr"></a>  CPathT::PCXSTR

文字列定数の型。

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>Remarks

`StringType` テンプレート パラメーターは、`CPathT`します。

##  <a name="pxstr"></a>  CPathT::PXSTR

文字列型です。

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>Remarks

`StringType` テンプレート パラメーターは、`CPathT`します。

##  <a name="quotespaces"></a>  CPathT::QuoteSpaces

このメソッドでは、スペースが含まれている場合は、パスを引用符で囲みます。

```
void QuoteSpaces();
```

### <a name="remarks"></a>Remarks

詳細については、[PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa)を参照してください。

##  <a name="relativepathto"></a>  CPathT::RelativePathTo

1 つのファイルまたはフォルダーから別の相対パスを作成するには、このメソッドを呼び出します。

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>パラメーター

*pszFrom*<br/>
相対パスの開始。

*dwAttrFrom*<br/>
ファイル属性の*pszFrom*します。 この値には、FILE_ATTRIBUTE_DIRECTORY が含まれている場合*pszFrom*がディレクトリであることが想定されます。 それ以外*pszFrom*ファイルであると見なされます。

*pszTo*<br/>
相対パスの終点。

*dwAttrTo*<br/>
ファイル属性の*pszTo*します。 この値には、FILE_ATTRIBUTE_DIRECTORY が含まれている場合*pszTo*がディレクトリであることが想定されます。 それ以外*pszTo*ファイルであると見なされます。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa)を参照してください。

##  <a name="removeargs"></a>  CPathT::RemoveArgs

パスからコマンドライン引数を削除するには、このメソッドを呼び出します。

```
void RemoveArgs();
```

### <a name="remarks"></a>Remarks

詳細については、[PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa)を参照してください。

##  <a name="removebackslash"></a>  CPathT::RemoveBackslash

パスから、末尾に円記号を削除するには、このメソッドを呼び出します。

```
void RemoveBackslash();
```

### <a name="remarks"></a>Remarks

詳細については、[PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha)を参照してください。

##  <a name="removeblanks"></a>  CPathT::RemoveBlanks

パスからすべての先頭および末尾のスペースを削除するには、このメソッドを呼び出します。

```
void RemoveBlanks();
```

### <a name="remarks"></a>Remarks

詳細については、[PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa)を参照してください。

##  <a name="removeextension"></a>  CPathT::RemoveExtension

1 つを使用する必要がある場合は、パスからファイルの拡張子を削除するには、このメソッドを呼び出します。

```
void RemoveExtension();
```

### <a name="remarks"></a>Remarks

詳細については、[PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona)を参照してください。

##  <a name="removefilespec"></a>  CPathT::RemoveFileSpec

それらがある場合は、パスからファイル名の末尾と円記号を削除するには、このメソッドを呼び出します。

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca)を参照してください。

##  <a name="renameextension"></a>  CPathT::RenameExtension

このメソッドを呼び出して、新しい拡張機能で、パスにファイル名拡張子を置き換えます。 ファイル名に拡張機能が含まれていない場合は、パスの末尾に、拡張機能に接続されています。

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>パラメーター

*pszExtension*<br/>
前に、新しいファイル名拡張子を"."の文字。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona)を参照してください。

##  <a name="skiproot"></a>  CPathT::SkipRoot

ドライブ文字または UNC (汎用名前付け規則) サーバー/共有のパス部分を無視して、パスを解析するには、このメソッドを呼び出します。

```
int SkipRoot() const;
```

### <a name="return-value"></a>戻り値

(ドライブ文字または UNC サーバー/共有) のルートの次のサブパスの開始位置を返します。

### <a name="remarks"></a>Remarks

詳細については、[PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota)を参照してください。

##  <a name="strippath"></a>  CPathT::StripPath

完全修飾パスとファイル名のパス部分を削除するには、このメソッドを呼び出します。

```
void StripPath();
```

### <a name="remarks"></a>Remarks

詳細については、[PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha)を参照してください。

##  <a name="striptoroot"></a>  CPathT::StripToRoot

ただし、ルート情報、パスのすべての部分を削除するには、このメソッドを呼び出します。

```
BOOL StripToRoot();
```

### <a name="return-value"></a>戻り値

有効なドライブ文字の場合は TRUE を返しますが見つかりましたパス、または FALSE それ以外の場合。

### <a name="remarks"></a>Remarks

詳細については、[PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota)を参照してください。

##  <a name="unquotespaces"></a>  CPathT::UnquoteSpaces

先頭とパスの末尾から引用符を削除するには、このメソッドを呼び出します。

```
void UnquoteSpaces();
```

### <a name="remarks"></a>Remarks

詳細については、[PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa)を参照してください。

##  <a name="xchar"></a>  CPathT::XCHAR

文字型。

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>Remarks

`StringType` テンプレート パラメーターは、`CPathT`します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)<br/>
[CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)
