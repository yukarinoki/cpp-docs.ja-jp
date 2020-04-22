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
ms.openlocfilehash: c10b854ae5c2d7167a067675b1391be24b6a8122
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746588"
---
# <a name="cpatht-class"></a>CPathT クラス

このクラスはパスを表します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <typename StringType>
class CPathT
```

#### <a name="parameters"></a>パラメーター

*StringType*<br/>
パスに使用する ATL/MFC 文字列クラス[(CStringT](../../atl-mfc-shared/reference/cstringt-class.md)を参照)。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[次のサービスを:P](#pcxstr)|定数文字列型。|
|[:PXSTR](#pxstr)|文字列型。|
|[CPathT::XCHAR](#xchar)|文字型。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cパス::Cパスト](#cpatht)|パスのコンストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPathT::バックスラッシュの追加](#addbackslash)|文字列の末尾に円記号を追加して、パスの正しい構文を作成します。|
|[CPathT::拡張機能の追加](#addextension)|パスにファイル拡張子を追加します。|
|[CPathT::追加](#append)|現在のパスに文字列を追加します。|
|[CPathT::ビルドルート](#buildroot)|指定したドライブ番号からルート パスを作成します。|
|[CPathT::正規化](#canonicalize)|パスを正規形式に変換します。|
|[CPathT::コンバイン](#combine)|ディレクトリ名を表す文字列と、ファイル パス名を表す文字列を 1 つのパスに連結します。|
|[CPathT::コモンプレフィックス](#commonprefix)|指定したパスが現在のパスと共通のプレフィックスを共有しているかどうかを調べます。|
|[Cパス::コンパクトパス](#compactpath)|パスコンポーネントを楕円で置き換えることで、指定したピクセル幅に収まるようにファイル パスを切り捨てます。|
|[CPathT::コンパクトパスエックス](#compactpathex)|パスの構成要素を省略記号で置き換えることによって、指定した文字数に収まるようにファイル パスを切り捨てます。|
|[CPathT::ファイルは存在します](#fileexists)|このパス名のファイルが存在するかどうかを確認します。|
|[CPathT::拡張を検索](#findextension)|パス内のファイル拡張子の位置を検索します。|
|[ファイル名を検索します。](#findfilename)|パス内のファイル名の位置を検索します。|
|[Cパス::ゲットドライブナンバー](#getdrivenumber)|'A' から 'Z' の範囲内のドライブ文字のパスを検索し、対応するドライブ番号を返します。|
|[CPathT::拡張機能を取得します。](#getextension)|パスからファイル拡張子を取得します。|
|[Cパス::イズディレクトリ](#isdirectory)|パスが有効なディレクトリかどうかを確認します。|
|[CPathT::ファイルスペック](#isfilespec)|パス区切り文字 (':' や ' '\\など) を検索します。 パス区切り文字が存在しない場合、パスはファイル仕様パスと見なされます。|
|[Cパス::Isプレフィックス](#isprefix)|*パスに、pszPrefix*によって渡される型の有効なプレフィックスが含まれているかどうかを調べます。|
|[Cパス::イズ相対](#isrelative)|パスが相対パスかどうかを調べます。|
|[CPathT::イズルート](#isroot)|パスがディレクトリ ルートかどうかを調べます。|
|[CPathT::イササミルート](#issameroot)|現在のパスを持つ共通のルート コンポーネントが別のパスにあるかどうかを調べます。|
|[CPathT::IsUNC](#isunc)|パスがサーバーと共有の有効な UNC (汎用名前付け規則) パスであるかどうかを確認します。|
|[Cパス::サーバー](#isuncserver)|パスがサーバーのみの有効な UNC (汎用名前付け規則) パスであるかどうかを確認します。|
|[Cパス::サーバーシェア](#isuncservershare)|パスが有効な UNC \\ \ (汎用名前付け規則) 共有*パスである*\ サーバー共有かどうかを*確認します。*|
|[Cパス::メイクプリティ](#makepretty)|パスをすべての小文字に変換して、パスの外観に一貫性を持たせる場合に、このメソッドを呼び出します。|
|[Cパス:マッチスペック](#matchspec)|ワイルドカード一致の種類を含む文字列のパスを検索します。|
|[CPathT::引用スペース](#quotespaces)|パスにスペースが含まれている場合は、このメソッドを呼び出して、パスを引用符で囲みます。|
|[Cパス::相対パス](#relativepathto)|あるファイルまたはフォルダーから別のファイルまたはフォルダーへの相対パスを作成します。|
|[CPathT::削除引数](#removeargs)|パスからコマンド ライン引数を削除します。|
|[CPathT::削除バックスラッシュ](#removebackslash)|パスから末尾の円記号を削除します。|
|[CPathT::ブランクの削除](#removeblanks)|パスから先頭と末尾の空白をすべて削除します。|
|[CPathT::拡張機能の削除](#removeextension)|パスからファイル拡張子を削除します (存在する場合)。|
|[ファイルの削除](#removefilespec)|パスに末尾のファイル名と円記号がある場合は、このメソッドを呼び出します。|
|[CPathT::拡張機能の名前の変更](#renameextension)|パス内のファイル名拡張子を新しい拡張子で置き換えます。 ファイル名に拡張子が含まれていない場合、拡張子は文字列の末尾に付加されます。|
|[CPathT::スキップルート](#skiproot)|ドライブ文字または UNC サーバー/共有パスの部分を無視してパスを解析します。|
|[Cパス::ストリップパス](#strippath)|完全修飾パスとファイル名のパス部分を削除します。|
|[CPathT::ストリップトルート](#striptoroot)|ルート情報を除くパスのすべての部分を削除します。|
|[CPathT::クォートなしスペース](#unquotespaces)|パスの先頭と末尾から引用符を削除します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[&型を指定します。](#operator_const_stringtype_amp)|この演算子を使用すると、オブジェクトを文字列として扱うことができます。|
|[CPathT::オペレーター CPathT::PCXSTR](#operator_cpatht__pcxstr)|この演算子を使用すると、オブジェクトを文字列として扱うことができます。|
|[&型の演算子](#operator_stringtype_amp)|この演算子を使用すると、オブジェクトを文字列として扱うことができます。|
|[CPathT::演算子 +=](#operator_add_eq)|この演算子は、パスに文字列を追加します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPathT::m_strPath](#m_strpath)|パス。|

## <a name="remarks"></a>解説

`CPath`、、`CPathA`および`CPathW`は次のように`CPathT`定義されたインスタンス化です。

`typedef CPathT< CString > CPath;`

`typedef CPathT< CStringA > CPathA;`

`typedef CPathT< CStringW > CPathW;`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlpath.h

## <a name="cpathtaddbackslash"></a><a name="addbackslash"></a>CPathT::バックスラッシュの追加

文字列の末尾に円記号を追加して、パスの正しい構文を作成します。 パスに既に末尾の円記号がある場合、バックスラッシュは追加されません。

```cpp
void AddBackslash();
```

### <a name="remarks"></a>解説

詳細については、「[パスの追加バックスラッシュ](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)」を参照してください。

## <a name="cpathtaddextension"></a><a name="addextension"></a>CPathT::拡張機能の追加

パスにファイル拡張子を追加します。

```
BOOL AddExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>パラメーター

*拡張*<br/>
追加するファイル拡張子。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスの追加拡張機能](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)」を参照してください。

## <a name="cpathtappend"></a><a name="append"></a>CPathT::追加

現在のパスに文字列を追加します。

```
BOOL Append(PCXSTR pszMore);
```

### <a name="parameters"></a>パラメーター

*pszもっと*<br/>
追加する文字列。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスの追加](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)」を参照してください。

## <a name="cpathtbuildroot"></a><a name="buildroot"></a>CPathT::ビルドルート

指定したドライブ番号からルート パスを作成します。

```cpp
void BuildRoot(int iDrive);
```

### <a name="parameters"></a>パラメーター

*Idrive*<br/>
ドライブ番号 (0 は A:、1 は B:、など)。

### <a name="remarks"></a>解説

詳細については、「[パスビルドルート](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)」を参照してください。

## <a name="cpathtcanonicalize"></a><a name="canonicalize"></a>CPathT::正規化

パスを正規形式に変換します。

```cpp
void Canonicalize();
```

### <a name="remarks"></a>解説

詳細については、「[パス正規化](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)」を参照してください。

## <a name="cpathtcombine"></a><a name="combine"></a>CPathT::コンバイン

ディレクトリ名を表す文字列と、ファイル パス名を表す文字列を 1 つのパスに連結します。

```cpp
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
ディレクトリのパスです。

*ファイル*<br/>
ファイル パス。

### <a name="remarks"></a>解説

詳細については、「 [PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)」を参照してください。

## <a name="cpathtcommonprefix"></a><a name="commonprefix"></a>CPathT::コモンプレフィックス

指定したパスが現在のパスと共通のプレフィックスを共有しているかどうかを調べます。

```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```

### <a name="parameters"></a>パラメーター

*その他*<br/>
現在のパスと比較するパス。

### <a name="return-value"></a>戻り値

共通のプレフィックスを返します。

### <a name="remarks"></a>解説

接頭辞は次のタイプの 1\\\\つです。\\\\". 詳細については、「[パスコモン プレフィックス](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)」を参照してください。

## <a name="cpathtcompactpath"></a><a name="compactpath"></a>Cパス::コンパクトパス

パスコンポーネントを楕円で置き換えることで、指定したピクセル幅に収まるようにファイル パスを切り捨てます。

```
BOOL CompactPath(HDC hDC, UINT nWidth);
```

### <a name="parameters"></a>パラメーター

*Hdc*<br/>
フォント メトリックに使用されるデバイス コンテキスト。

*n幅*<br/>
文字列が強制的に収まる幅 (ピクセル単位)。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスのパスをパスパス」](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)を参照してください。

## <a name="cpathtcompactpathex"></a><a name="compactpathex"></a>CPathT::コンパクトパスエックス

パスの構成要素を省略記号で置き換えることによって、指定した文字数に収まるようにファイル パスを切り捨てます。

```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```

### <a name="parameters"></a>パラメーター

*nMaxChars*<br/>
新しい文字列に含まれる最大文字数 (終端の NULL 文字を含む)。

*dwFlags*<br/>
予約済み。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスパスパス」を参照してください](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)。

## <a name="cpathtcpatht"></a><a name="cpatht"></a>Cパス::Cパスト

コンストラクターです。

```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
パス文字列へのポインター。

*path*<br/>
パス文字列。

## <a name="cpathtfileexists"></a><a name="fileexists"></a>CPathT::ファイルは存在します

このパス名のファイルが存在するかどうかを確認します。

```
BOOL FileExists() const;
```

### <a name="return-value"></a>戻り値

ファイルが存在する場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスファイルが存在する](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)」を参照してください。

## <a name="cpathtfindextension"></a><a name="findextension"></a>CPathT::拡張を検索

パス内のファイル拡張子の位置を検索します。

```
int FindExtension() const;
```

### <a name="return-value"></a>戻り値

拡張子の前の "." の位置を返します。 拡張子が見つからない場合は、-1 を返します。

### <a name="remarks"></a>解説

詳細については、「[パス検索拡張機能](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)」を参照してください。

## <a name="cpathtfindfilename"></a><a name="findfilename"></a>ファイル名を検索します。

パス内のファイル名の位置を検索します。

```
int FindFileName() const;
```

### <a name="return-value"></a>戻り値

ファイル名の位置を返します。 ファイル名が見つからない場合は、-1 を返します。

### <a name="remarks"></a>解説

詳細については、「 [PathFind ファイル名](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)」を参照してください。

## <a name="cpathtgetdrivenumber"></a><a name="getdrivenumber"></a>Cパス::ゲットドライブナンバー

'A' から 'Z' の範囲内のドライブ文字のパスを検索し、対応するドライブ番号を返します。

```
int GetDriveNumber() const;
```

### <a name="return-value"></a>戻り値

パスにドライブ文字がある場合は、0 から 25 までの整数 ('A から 'Z' に対応) を返します。

### <a name="remarks"></a>解説

詳細については、「[パスGetドライブ番号](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)」を参照してください。

## <a name="cpathtgetextension"></a><a name="getextension"></a>CPathT::拡張機能を取得します。

パスからファイル拡張子を取得します。

```
StringType GetExtension() const;
```

### <a name="return-value"></a>戻り値

ファイル拡張子を返します。

## <a name="cpathtisdirectory"></a><a name="isdirectory"></a>Cパス::イズディレクトリ

パスが有効なディレクトリかどうかを確認します。

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>戻り値

パスがディレクトリの場合は 0 以外の値 (16) を返します。

### <a name="remarks"></a>解説

詳細については、「 [PathIsDirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)」を参照してください。

## <a name="cpathtisfilespec"></a><a name="isfilespec"></a>CPathT::ファイルスペック

パス区切り文字 (':' や ' '\\など) を検索します。 パス区切り文字が存在しない場合、パスはファイル仕様パスと見なされます。

```
BOOL IsFileSpec() const;
```

### <a name="return-value"></a>戻り値

パス内にパス区切り文字がない場合は TRUE を返し、パス区切り文字がある場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスIsFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)」を参照してください。

## <a name="cpathtisprefix"></a><a name="isprefix"></a>Cパス::Isプレフィックス

*パスに、pszPrefix*によって渡される型の有効なプレフィックスが含まれているかどうかを調べます。

```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```

### <a name="parameters"></a>パラメーター

*プレフィックス*<br/>
検索対象のプレフィックス。 接頭辞は次のタイプの 1\\\\つです。\\\\".

### <a name="return-value"></a>戻り値

パスにプレフィックスが含まれている場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「 [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)」を参照してください。

## <a name="cpathtisrelative"></a><a name="isrelative"></a>Cパス::イズ相対

パスが相対パスかどうかを調べます。

```
BOOL IsRelative() const;
```

### <a name="return-value"></a>戻り値

パスが相対パスの場合は TRUE を返し、絶対パスの場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「 [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)」を参照してください。

## <a name="cpathtisroot"></a><a name="isroot"></a>CPathT::イズルート

パスがディレクトリ ルートかどうかを調べます。

```
BOOL IsRoot() const;
```

### <a name="return-value"></a>戻り値

パスがルートの場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「 [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)」を参照してください。

## <a name="cpathtissameroot"></a><a name="issameroot"></a>CPathT::イササミルート

現在のパスを持つ共通のルート コンポーネントが別のパスにあるかどうかを調べます。

```
BOOL IsSameRoot(PCXSTR pszOther) const;
```

### <a name="parameters"></a>パラメーター

*その他*<br/>
もう一方のパス。

### <a name="return-value"></a>戻り値

両方の文字列が同じルート コンポーネントを持つ場合は TRUE を返し、そうでない場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「 [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)」を参照してください。

## <a name="cpathtisunc"></a><a name="isunc"></a>CPathT::IsUNC

パスがサーバーと共有の有効な UNC (汎用名前付け規則) パスであるかどうかを確認します。

```
BOOL IsUNC() const;
```

### <a name="return-value"></a>戻り値

パスが有効な UNC パスの場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「 [PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)」を参照してください。

## <a name="cpathtisuncserver"></a><a name="isuncserver"></a>Cパス::サーバー

パスがサーバーのみの有効な UNC (汎用名前付け規則) パスであるかどうかを確認します。

```
BOOL IsUNCServer() const;
```

### <a name="return-value"></a>戻り値

文字列がサーバーのみの有効な UNC パス (共有名なし) の場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスIsUNCサーバー](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)」を参照してください。

## <a name="cpathtisuncservershare"></a><a name="isuncservershare"></a>Cパス::サーバーシェア

パスが有効な UNC \\ \ (汎用名前付け規則) 共有*パスである*\ サーバー共有かどうかを*確認します。*

```
BOOL IsUNCServerShare() const;
```

### <a name="return-value"></a>戻り値

パスが\\\ *フォーム サーバー*\ *共有*にある場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[サーバーの共有」](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)を参照してください。

## <a name="cpathtm_strpath"></a><a name="m_strpath"></a>CPathT::m_strPath

パス。

```
StringType m_strPath;
```

### <a name="remarks"></a>解説

`StringType`は テンプレート パラメータ`CPathT`です。

## <a name="cpathtmakepretty"></a><a name="makepretty"></a>Cパス::メイクプリティ

パスをすべての小文字に変換して、パスの外観に一貫性を持たせる場合に、このメソッドを呼び出します。

```
BOOL MakePretty();
```

### <a name="return-value"></a>戻り値

パスが変換されている場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスメイクプリティ](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)」を参照してください。

## <a name="cpathtmatchspec"></a><a name="matchspec"></a>Cパス:マッチスペック

ワイルドカード一致の種類を含む文字列のパスを検索します。

```
BOOL MatchSpec(PCXSTR pszSpec) const;
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
検索対象のファイルの種類を持つ null で終わる文字列へのポインター。 たとえば、現在のパスにあるファイルが DOC ファイルかどうかをテストするには *、pszSpec*を "*.doc" に設定する必要があります。

### <a name="return-value"></a>戻り値

文字列が一致する場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスマッチ仕様](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)」を参照してください。

## <a name="cpathtoperator-"></a><a name="operator_add_eq"></a>CPathT::演算子 +=

この演算子は、パスに文字列を追加します。

```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```

### <a name="parameters"></a>パラメーター

*pszもっと*<br/>
追加する文字列。

### <a name="return-value"></a>戻り値

更新されたパスを返します。

## <a name="cpathtoperator-const-stringtype-amp"></a><a name="operator_const_stringtype_amp"></a>CPathT::演算子定数文字列型&amp;

この演算子を使用すると、オブジェクトを文字列として扱うことができます。

```
operator const StringType&() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトが管理する現在のパスを表す文字列を返します。

## <a name="cpathtoperator-cpathtpcxstr"></a><a name="operator_cpatht__pcxstr"></a>CPathT::オペレーター CPathT::PCXSTR

この演算子を使用すると、オブジェクトを文字列として扱うことができます。

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトが管理する現在のパスを表す文字列を返します。

## <a name="cpathtoperator-stringtype-amp"></a><a name="operator_stringtype_amp"></a>CPathT::演算子文字列型&amp;

この演算子を使用すると、オブジェクトを文字列として扱うことができます。

```
operator StringType&() throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトが管理する現在のパスを表す文字列を返します。

## <a name="cpathtpcxstr"></a><a name="pcxstr"></a>次のサービスを:P

定数文字列型。

```
typedef StringType::PCXSTR PCXSTR;
```

### <a name="remarks"></a>解説

`StringType`は テンプレート パラメータ`CPathT`です。

## <a name="cpathtpxstr"></a><a name="pxstr"></a>:PXSTR

文字列型。

```
typedef StringType::PXSTR PXSTR;
```

### <a name="remarks"></a>解説

`StringType`は テンプレート パラメータ`CPathT`です。

## <a name="cpathtquotespaces"></a><a name="quotespaces"></a>CPathT::引用スペース

パスにスペースが含まれている場合は、このメソッドを呼び出して、パスを引用符で囲みます。

```cpp
void QuoteSpaces();
```

### <a name="remarks"></a>解説

詳細については、「[パスクオートスペース](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)」を参照してください。

## <a name="cpathtrelativepathto"></a><a name="relativepathto"></a>Cパス::相対パス

あるファイルまたはフォルダーから別のファイルまたはフォルダーへの相対パスを作成します。

```
BOOL RelativePathTo(
    PCXSTR pszFrom,
    DWORD dwAttrFrom,
    PCXSTR pszTo,
    DWORD dwAttrTo);
```

### <a name="parameters"></a>パラメーター

*を起*<br/>
相対パスの始点。

*ドワトトルフロ*<br/>
*pszFrom*のファイル属性。 この値にFILE_ATTRIBUTE_DIRECTORYが含まれている場合 *、pszFrom*はディレクトリであると見なされます。それ以外の場合 *、pszFrom*はファイルであると見なされます。

*pszTo*<br/>
相対パスの終点。

*ドワトルト*<br/>
*pszTo*のファイル属性。 この値にFILE_ATTRIBUTE_DIRECTORYが含まれている場合 *、pszTo*はディレクトリであると見なされます。それ以外の場合 *、pszTo*はファイルであると見なされます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パス相対パス」を参照](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)してください。

## <a name="cpathtremoveargs"></a><a name="removeargs"></a>CPathT::削除引数

パスからコマンド ライン引数を削除します。

```cpp
void RemoveArgs();
```

### <a name="remarks"></a>解説

詳細については、「[パス削除引数 」](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)を参照してください。

## <a name="cpathtremovebackslash"></a><a name="removebackslash"></a>CPathT::削除バックスラッシュ

パスから末尾の円記号を削除します。

```cpp
void RemoveBackslash();
```

### <a name="remarks"></a>解説

詳細については、「[パス削除バックスラッシュ](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)」を参照してください。

## <a name="cpathtremoveblanks"></a><a name="removeblanks"></a>CPathT::ブランクの削除

パスから先頭と末尾の空白をすべて削除します。

```cpp
void RemoveBlanks();
```

### <a name="remarks"></a>解説

詳細については、「[パス削除空白](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)」を参照してください。

## <a name="cpathtremoveextension"></a><a name="removeextension"></a>CPathT::拡張機能の削除

パスからファイル拡張子を削除します (存在する場合)。

```cpp
void RemoveExtension();
```

### <a name="remarks"></a>解説

詳細については、「[パスの削除拡張](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)」を参照してください。

## <a name="cpathtremovefilespec"></a><a name="removefilespec"></a>ファイルの削除

パスに末尾のファイル名と円記号がある場合は、このメソッドを呼び出します。

```
BOOL RemoveFileSpec();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスの削除ファイルの種類](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)」を参照してください。

## <a name="cpathtrenameextension"></a><a name="renameextension"></a>CPathT::拡張機能の名前の変更

パス内のファイル名拡張子を新しい拡張子で置き換えます。 ファイル名に拡張子が含まれていない場合、拡張子はパスの末尾に付加されます。

```
BOOL RenameExtension(PCXSTR pszExtension);
```

### <a name="parameters"></a>パラメーター

*拡張*<br/>
新しいファイル名拡張子 (その前に "." 文字が付きます)。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「[パスの名前変更拡張機能](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)」を参照してください。

## <a name="cpathtskiproot"></a><a name="skiproot"></a>CPathT::スキップルート

ドライブ文字または UNC (汎用名前付け規則) サーバー/共有パス部分を無視してパスを解析します。

```
int SkipRoot() const;
```

### <a name="return-value"></a>戻り値

ルート (ドライブ文字または UNC サーバー/共有) に続くサブパスの先頭の位置を返します。

### <a name="remarks"></a>解説

詳細については、「[パススキップルート](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)」を参照してください。

## <a name="cpathtstrippath"></a><a name="strippath"></a>Cパス::ストリップパス

完全修飾パスとファイル名のパス部分を削除します。

```cpp
void StripPath();
```

### <a name="remarks"></a>解説

詳細については、「[パスストリップパス](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)」を参照してください。

## <a name="cpathtstriptoroot"></a><a name="striptoroot"></a>CPathT::ストリップトルート

ルート情報を除くパスのすべての部分を削除します。

```
BOOL StripToRoot();
```

### <a name="return-value"></a>戻り値

パス内に有効なドライブ文字が見つかった場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、「 [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)」を参照してください。

## <a name="cpathtunquotespaces"></a><a name="unquotespaces"></a>CPathT::クォートなしスペース

パスの先頭と末尾から引用符を削除します。

```cpp
void UnquoteSpaces();
```

### <a name="remarks"></a>解説

詳細については、「[パスアンクォートスペース](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)」を参照してください。

## <a name="cpathtxchar"></a><a name="xchar"></a>CPathT::XCHAR

文字型。

```
typedef StringType::XCHAR XCHAR;
```

### <a name="remarks"></a>解説

`StringType`は テンプレート パラメータ`CPathT`です。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)<br/>
[CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)
