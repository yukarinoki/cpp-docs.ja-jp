---
title: CPathT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CPathT class
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37f669ddc7912f45222d52f10311ff70110e170f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366381"
---
# <a name="cpatht-class"></a>CPathT クラス
このクラスは、パスを表します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <typename StringType>
class CPathT
```  
  
#### <a name="parameters"></a>パラメーター  
 `StringType`  
 パスを使用する、ATL と MFC 文字列クラス (を参照してください[CStringT](../../atl-mfc-shared/reference/cstringt-class.md))。  
  
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
|[CPathT::CPathT](#cpatht)|パスのコンス トラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPathT::AddBackslash](#addbackslash)|パスの正しい構文を作成する文字列の末尾に円記号を追加するには、このメソッドを呼び出します。|  
|[CPathT::AddExtension](#addextension)|パスにファイル拡張子を追加するには、このメソッドを呼び出します。|  
|[CPathT::Append](#append)|現在のパスを文字列に追加するには、このメソッドを呼び出します。|  
|[CPathT::BuildRoot](#buildroot)|特定のドライブ番号からルートのパスを作成するには、このメソッドを呼び出します。|  
|[CPathT::Canonicalize](#canonicalize)|このメソッドを呼び出して、パスを正規の形式に変換します。|  
|[CPathT::Combine](#combine)|ディレクトリ名を表す文字列および 1 つのパスにファイルのパス名を表す文字列を連結するには、このメソッドを呼び出します。|  
|[CPathT::CommonPrefix](#commonprefix)|このメソッドを呼び出して、指定されたパスが、現在のパスと、共通のプレフィックスを共有するかどうかを判断します。|  
|[CPathT::CompactPath](#compactpath)|省略記号をパス コンポーネントを置き換えることで、特定のピクセル幅に収まるようにファイル パスを短くには、このメソッドを呼び出します。|  
|[CPathT::CompactPathEx](#compactpathex)|省略記号をパス コンポーネントを置き換えることで、指定した文字数内に収まるようにファイル パスを短くには、このメソッドを呼び出します。|  
|[CPathT::FileExists](#fileexists)|このパス名でファイルが存在するかどうかを確認するには、このメソッドを呼び出します。|  
|[CPathT::FindExtension](#findextension)|パス内のファイル拡張子の位置を検索するには、このメソッドを呼び出します。|  
|[CPathT::FindFileName](#findfilename)|パス内のファイル名の位置を検索するには、このメソッドを呼び出します。|  
|[CPathT::GetDriveNumber](#getdrivenumber)|このメソッドを呼び出して、ドライブ文字 'A' ~ 'Z' の範囲内のパスを検索し、対応するドライブの数を返します。|  
|[CPathT::GetExtension](#getextension)|パスからファイルの拡張子を取得するには、このメソッドを呼び出します。|  
|[CPathT::IsDirectory](#isdirectory)|このメソッドを呼び出して、パスが有効なディレクトリであるかどうかを確認します。|  
|[CPathT::IsFileSpec](#isfilespec)|任意のパス区切り文字のパスを検索するには、このメソッドを呼び出す (たとえば、':' または '\\')。 パス区切り文字がない場合は、パスがファイルの仕様がパスであると見なされます。|  
|[CPathT::IsPrefix](#isprefix)|渡される型の有効なプレフィックスが、パスに含まれているかどうかを決定するには、このメソッドを呼び出す`pszPrefix`です。|  
|[CPathT::IsRelative](#isrelative)|このメソッドでは、パスが相対かを判断します。|  
|[CPathT::IsRoot](#isroot)|このメソッドを呼び出して、パスがディレクトリのルートかどうかを判断します。|  
|[CPathT::IsSameRoot](#issameroot)|別のパスが、現在のパスで共通のルート コンポーネントを持つかどうかを決定するには、このメソッドを呼び出します。|  
|[CPathT::IsUNC](#isunc)|パスが、サーバーの有効な UNC (汎用名前付け規則) パスであるかどうかを確認するには、このメソッドを呼び出すし、共有できます。|  
|[CPathT::IsUNCServer](#isuncserver)|このメソッドを呼び出して、パスがサーバーだけを表す有効な UNC (汎用名前付け規則) パスであるかどうかを確認します。|  
|[CPathT::IsUNCServerShare](#isuncservershare)|パスが有効な UNC (汎用名前付け規則) 共有パスであるかどうかを確認するには、このメソッドを呼び出す\\ \ *サーバー*\ *共有*です。|  
|[CPathT::MakePretty](#makepretty)|このメソッドを呼び出して、パスを一貫した外観のパスを指定する文字をすべて小文字に変換します。|  
|[CPathT::MatchSpec](#matchspec)|ワイルドカード一致の種類を含む文字列へのパスを検索するには、このメソッドを呼び出します。|  
|[CPathT::QuoteSpaces](#quotespaces)|このメソッドを呼び出して、スペースが含まれている場合は、パスを引用符で囲みます。|  
|[CPathT::RelativePathTo](#relativepathto)|1 つのファイルまたはフォルダーから別の相対パスを作成するには、このメソッドを呼び出します。|  
|[CPathT::RemoveArgs](#removeargs)|パスからコマンドライン引数を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveBackslash](#removebackslash)|パスから、末尾に円記号を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveBlanks](#removeblanks)|パスからすべての先頭および末尾のスペースを削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveExtension](#removeextension)|1 つを使用する必要がある場合は、パスからファイルの拡張子を削除するには、このメソッドを呼び出します。|  
|[CPathT::RemoveFileSpec](#removefilespec)|それらがある場合は、パスから、末尾にファイル名と円記号を削除するには、このメソッドを呼び出します。|  
|[CPathT::RenameExtension](#renameextension)|このメソッドを呼び出して、新しい拡張機能で、パスにファイル名拡張子を置き換えます。 ファイル名に拡張機能が含まれていない場合、拡張機能は、文字列の末尾に添付されます。|  
|[CPathT::SkipRoot](#skiproot)|ドライブや UNC サーバー/共有のパス部分を無視する、パスを解析するには、このメソッドを呼び出します。|  
|[CPathT::StripPath](#strippath)|完全修飾パスとファイル名のパス部分を削除するには、このメソッドを呼び出します。|  
|[CPathT::StripToRoot](#striptoroot)|ただし、ルート情報、パスのすべての部分を削除するには、このメソッドを呼び出します。|  
|[CPathT::UnquoteSpaces](#unquotespaces)|先頭と末尾のパスから引用符を削除するには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CPathT::operator const 文字列型 (& a)](#operator_const_stringtype_amp)|この演算子は、文字列として処理するオブジェクトを使用します。|  
|[CPathT::operator CPathT::PCXSTR](#operator_cpatht__pcxstr)|この演算子は、文字列として処理するオブジェクトを使用します。|  
|[CPathT::operator 文字列型 (& a)](#operator_stringtype)|この演算子は、文字列として処理するオブジェクトを使用します。|  
|[CPathT::operator + =](#operator_add_eq)|この演算子は、パスに、文字列を追加します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPathT::m_strPath](#m_strpath)|パス。|  
  
## <a name="remarks"></a>コメント  
 `CPath`、 `CPathA`、および`CPathW`のインスタンス化は、`CPathT`次のように定義されています。  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlpath.h  
  
##  <a name="addbackslash"></a>  CPathT::AddBackslash  
 パスの正しい構文を作成する文字列の末尾に円記号を追加するには、このメソッドを呼び出します。 パスは、末尾に円記号を既に持っている場合は、円記号は追加されません。  
  
```
void AddBackslash();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathAddBackSlash](http://msdn.microsoft.com/library/windows/desktop/bb773561)です。  
  
##  <a name="addextension"></a>  CPathT::AddExtension  
 パスにファイル拡張子を追加するには、このメソッドを呼び出します。  
  
```
BOOL AddExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszExtension`  
 追加するファイル拡張子。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563)です。  
  
##  <a name="append"></a>  CPathT::Append  
 現在のパスを文字列に追加するには、このメソッドを呼び出します。  
  
```
BOOL Append(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszMore`  
 追加する文字列。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565)です。  
  
##  <a name="buildroot"></a>  CPathT::BuildRoot  
 特定のドライブ番号からルートのパスを作成するには、このメソッドを呼び出します。  
  
```
void BuildRoot(int iDrive);
```  
  
### <a name="parameters"></a>パラメーター  
 *ドライブ*  
 ドライブ数 (0 a: には、1 b: というように)。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567)です。  
  
##  <a name="canonicalize"></a>  CPathT::Canonicalize  
 このメソッドを呼び出して、パスを正規の形式に変換します。  
  
```
void Canonicalize();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569)です。  
  
##  <a name="combine"></a>  CPathT::Combine  
 ディレクトリ名を表す文字列および 1 つのパスにファイルのパス名を表す文字列を連結するには、このメソッドを呼び出します。  
  
```
void Combine(PCXSTR pszDir, PCXSTR  pszFile);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszDir`  
 ディレクトリのパス。  
  
 *pszFile*  
 ファイルのパス。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571)です。  
  
##  <a name="commonprefix"></a>  CPathT::CommonPrefix  
 このメソッドを呼び出して、指定されたパスが、現在のパスと、共通のプレフィックスを共有するかどうかを判断します。  
  
```
CPathT<StringType> CommonPrefix(PCXSTR pszOther);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszOther`  
 現在のものと比較するパス。  
  
### <a name="return-value"></a>戻り値  
 共通のプレフィックスを返します。  
  
### <a name="remarks"></a>コメント  
 プレフィックスは、これらの型のいずれかの:"c:\\\\「,」です","..","..。\\\\". 詳細については、次を参照してください。 [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574)です。  
  
##  <a name="compactpath"></a>  CPathT::CompactPath  
 省略記号をパス コンポーネントを置き換えることで、特定のピクセル幅に収まるようにファイル パスを短くには、このメソッドを呼び出します。  
  
```
BOOL CompactPath(HDC hDC, UINT nWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 `hDC`  
 フォント メトリックに使用されるデバイス コンテキスト。  
  
 `nWidth`  
 幅 (ピクセル単位) に収まるように、文字列が強制されることです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575)です。  
  
##  <a name="compactpathex"></a>  CPathT::CompactPathEx  
 省略記号をパス コンポーネントを置き換えることで、指定した文字数内に収まるようにファイル パスを短くには、このメソッドを呼び出します。  
  
```
BOOL CompactPathEx(UINT nMaxChars, DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMaxChars`  
 終端の NULL 文字を含む、新しい文字列に含まれている文字の最大数。  
  
 `dwFlags`  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578)です。  
  
##  <a name="cpatht"></a>  CPathT::CPathT  
 コンストラクターです。  
  
```
CPathT(PCXSTR pszPath);
CPathT(const CPathT<StringType>& path);
CPathT() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pszPath*  
 パス文字列へのポインター。  
  
 *path*  
 パス文字列。  
  
##  <a name="fileexists"></a>  CPathT::FileExists  
 このパス名でファイルが存在するかどうかを確認するには、このメソッドを呼び出します。  
  
```
BOOL FileExists() const;
```  
  
### <a name="return-value"></a>戻り値  
 ファイルが存在するかどうか、FALSE それ以外の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584)です。  
  
##  <a name="findextension"></a>  CPathT::FindExtension  
 パス内のファイル拡張子の位置を検索するには、このメソッドを呼び出します。  
  
```
int FindExtension() const;
```  
  
### <a name="return-value"></a>戻り値  
 位置を返します、"です。"前に、拡張機能です。 拡張機能が見つからない場合は、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587)です。  
  
##  <a name="findfilename"></a>  CPathT::FindFileName  
 パス内のファイル名の位置を検索するには、このメソッドを呼び出します。  
  
```
int FindFileName() const;
```  
  
### <a name="return-value"></a>戻り値  
 ファイル名の位置を返します。 ファイル名が見つからない場合は、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)です。  
  
##  <a name="getdrivenumber"></a>  CPathT::GetDriveNumber  
 このメソッドを呼び出して、ドライブ文字 'A' ~ 'Z' の範囲内のパスを検索し、対応するドライブの数を返します。  
  
```
int GetDriveNumber() const;
```  
  
### <a name="return-value"></a>戻り値  
 場合は、パスにドライブ文字、または-1 それ以外の場合に 0 ~ 25 (に対応する 'A' から 'Z') を整数としてドライブの数を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612)です。  
  
##  <a name="getextension"></a>  CPathT::GetExtension  
 パスからファイルの拡張子を取得するには、このメソッドを呼び出します。  
  
```
StringType GetExtension() const;
```  
  
### <a name="return-value"></a>戻り値  
 ファイル拡張子を返します。  
  
##  <a name="isdirectory"></a>  CPathT::IsDirectory  
 このメソッドを呼び出して、パスが有効なディレクトリであるかどうかを確認します。  
  
```
BOOL IsDirectory() const;
```  
  
### <a name="return-value"></a>戻り値  
 パスが、ディレクトリの場合は、0 以外の値 (16) を返します`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621)です。  
  
##  <a name="isfilespec"></a>  CPathT::IsFileSpec  
 任意のパス区切り文字のパスを検索するには、このメソッドを呼び出す (たとえば、':' または '\\')。 パス区切り文字がない場合は、パスがファイルの仕様がパスであると見なされます。  
  
```
BOOL IsFileSpec() const;
```  
  
### <a name="return-value"></a>戻り値  
 パス、パス区切り文字がない場合は TRUE またはパス区切り文字がある場合は FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627)です。  
  
##  <a name="isprefix"></a>  CPathT::IsPrefix  
 渡される型の有効なプレフィックスが、パスに含まれているかどうかを決定するには、このメソッドを呼び出す`pszPrefix`です。  
  
```
BOOL IsPrefix(PCXSTR pszPrefix) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPrefix`  
 検索対象のプレフィックス。 プレフィックスは、これらの型のいずれかの:"c:\\\\「,」です","..","..。\\\\".  
  
### <a name="return-value"></a>戻り値  
 パスが含まれる場合、プレフィックス、または FALSE それ以外の場合は、TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650)です。  
  
##  <a name="isrelative"></a>  CPathT::IsRelative  
 このメソッドでは、パスが相対かを判断します。  
  
```
BOOL IsRelative() const;
```  
  
### <a name="return-value"></a>戻り値  
 絶対である場合、パスが相対パス、または FALSE の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660)です。  
  
##  <a name="isroot"></a>  CPathT::IsRoot  
 このメソッドを呼び出して、パスがディレクトリのルートかどうかを判断します。  
  
```
BOOL IsRoot() const;
```  
  
### <a name="return-value"></a>戻り値  
 パスの場合、ルート、または FALSE それ以外の場合は、TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674)です。  
  
##  <a name="issameroot"></a>  CPathT::IsSameRoot  
 別のパスが、現在のパスで共通のルート コンポーネントを持つかどうかを決定するには、このメソッドを呼び出します。  
  
```
BOOL IsSameRoot(PCXSTR pszOther) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pszOther`  
 その他のパスです。  
  
### <a name="return-value"></a>戻り値  
 両方の文字列またはがある場合、ルート コンポーネントが同じ FALSE それ以外の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687)です。  
  
##  <a name="isunc"></a>  CPathT::IsUNC  
 パスが、サーバーの有効な UNC (汎用名前付け規則) パスであるかどうかを確認するには、このメソッドを呼び出すし、共有できます。  
  
```
BOOL IsUNC() const;
```  
  
### <a name="return-value"></a>戻り値  
 パスは有効な UNC パス、または FALSE をそれ以外の場合がある場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712)です。  
  
##  <a name="isuncserver"></a>  CPathT::IsUNCServer  
 このメソッドを呼び出して、パスがサーバーだけを表す有効な UNC (汎用名前付け規則) パスであるかどうかを確認します。  
  
```
BOOL IsUNCServer() const;
```  
  
### <a name="return-value"></a>戻り値  
 かどうか、文字列は有効なサーバーだけを表す UNC パス (共有名がない)、または FALSE それ以外の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722)です。  
  
##  <a name="isuncservershare"></a>  CPathT::IsUNCServerShare  
 パスが有効な UNC (汎用名前付け規則) 共有パスであるかどうかを確認するには、このメソッドを呼び出す\\ \ *サーバー*\ *共有*です。  
  
```
BOOL IsUNCServerShare() const;
```  
  
### <a name="return-value"></a>戻り値  
 パスが、フォームの場合は TRUE を返します\\ \ *サーバー*\ *共有*、FALSE、またはそれ以外の場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723)です。  
  
##  <a name="m_strpath"></a>  CPathT::m_strPath  
 パス。  
  
```
StringType m_strPath;
```  
  
### <a name="remarks"></a>コメント  
 `StringType` テンプレート パラメーターには、`CPathT`です。  
  
##  <a name="makepretty"></a>  CPathT::MakePretty  
 このメソッドを呼び出して、パスを一貫した外観のパスを指定する文字をすべて小文字に変換します。  
  
```
BOOL MakePretty();
```  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合、パスは、変換された場合は TRUE または FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725)です。  
  
##  <a name="matchspec"></a>  CPathT::MatchSpec  
 ワイルドカード一致の種類を含む文字列へのパスを検索するには、このメソッドを呼び出します。  
  
```
BOOL MatchSpec(PCXSTR pszSpec) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pszSpec`  
 検索対象のファイルの種類に null で終わる文字列へのポインター。 たとえば、現在のパスでファイルがドキュメントのファイルであるかどうかをテストする`pszSpec`に設定する必要があります"* .doc"です。  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合、文字列が一致する場合は TRUE または FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727)です。  
  
##  <a name="operator_add_eq"></a>  CPathT::operator + =  
 この演算子は、パスに、文字列を追加します。  
  
```
CPathT<StringType>& operator+=(PCXSTR pszMore);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszMore`  
 追加する文字列。  
  
### <a name="return-value"></a>戻り値  
 更新されたパスを返します。  
  
##  <a name="operator_const_stringtype_amp"></a>  CPathT::operator const 文字列型 &amp;  
 この演算子は、文字列として処理するオブジェクトを使用します。  
  
```
 operatorconst StringType&() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 このオブジェクトによって管理されている現在のパスを表す文字列を返します。  
  
##  <a name="operator_cpatht__pcxstr"></a>  CPathT::operator CPathT::PCXSTR  
 この演算子は、文字列として処理するオブジェクトを使用します。  
  
```
 operatorPCXSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 このオブジェクトによって管理されている現在のパスを表す文字列を返します。  
  
##  <a name="operator_stringtype__amp"></a>  CPathT::operator 文字列型 &amp;  
 この演算子は、文字列として処理するオブジェクトを使用します。  
  
```
 operatorStringType&() throw();
```  
  
### <a name="return-value"></a>戻り値  
 このオブジェクトによって管理されている現在のパスを表す文字列を返します。  
  
##  <a name="pcxstr"></a>  CPathT::PCXSTR  
 文字列定数の型。  
  
```
typedef StringType::PCXSTR PCXSTR;
```  
  
### <a name="remarks"></a>コメント  
 `StringType` テンプレート パラメーターには、`CPathT`です。  
  
##  <a name="pxstr"></a>  CPathT::PXSTR  
 文字列型です。  
  
```
typedef StringType::PXSTR PXSTR;
```  
  
### <a name="remarks"></a>コメント  
 `StringType` テンプレート パラメーターには、`CPathT`です。  
  
##  <a name="quotespaces"></a>  CPathT::QuoteSpaces  
 このメソッドを呼び出して、スペースが含まれている場合は、パスを引用符で囲みます。  
  
```
void QuoteSpaces();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739)です。  
  
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
 `pszFrom`  
 相対パスの開始時刻です。  
  
 *dwAttrFrom*  
 ファイル属性`pszFrom`です。 FILE_ATTRIBUTE_DIRECTORY がこの値に含まれている場合`pszFrom`がディレクトリであると仮定して、それ以外の`pszFrom`ファイルであると見なされます。  
  
 `pszTo`  
 相対パスの終点。  
  
 *dwAttrTo*  
 ファイル属性`pszTo`です。 FILE_ATTRIBUTE_DIRECTORY がこの値に含まれている場合`pszTo`がディレクトリであると仮定して、それ以外の`pszTo`ファイルであると見なされます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740)です。  
  
##  <a name="removeargs"></a>  CPathT::RemoveArgs  
 パスからコマンドライン引数を削除するには、このメソッドを呼び出します。  
  
```
void RemoveArgs();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742)です。  
  
##  <a name="removebackslash"></a>  CPathT::RemoveBackslash  
 パスから、末尾に円記号を削除するには、このメソッドを呼び出します。  
  
```
void RemoveBackslash();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743)です。  
  
##  <a name="removeblanks"></a>  CPathT::RemoveBlanks  
 パスからすべての先頭および末尾のスペースを削除するには、このメソッドを呼び出します。  
  
```
void RemoveBlanks();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745)です。  
  
##  <a name="removeextension"></a>  CPathT::RemoveExtension  
 1 つを使用する必要がある場合は、パスからファイルの拡張子を削除するには、このメソッドを呼び出します。  
  
```
void RemoveExtension();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746)です。  
  
##  <a name="removefilespec"></a>  CPathT::RemoveFileSpec  
 それらがある場合は、パスから、末尾にファイル名と円記号を削除するには、このメソッドを呼び出します。  
  
```
BOOL RemoveFileSpec();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748)です。  
  
##  <a name="renameextension"></a>  CPathT::RenameExtension  
 このメソッドを呼び出して、新しい拡張機能で、パスにファイル名拡張子を置き換えます。 ファイル名に拡張機能が含まれていない場合、拡張機能は、パスの末尾に添付されます。  
  
```
BOOL RenameExtension(PCXSTR pszExtension);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszExtension`  
 ファイル名の新しい拡張子を"です。"文字です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749)です。  
  
##  <a name="skiproot"></a>  CPathT::SkipRoot  
 ドライブや UNC (汎用名前付け規則) サーバー/共有のパス部分を無視する、パスを解析するには、このメソッドを呼び出します。  
  
```
int SkipRoot() const;
```  
  
### <a name="return-value"></a>戻り値  
 (ドライブ文字または UNC サーバー/共有) のルートに続くサブ パスの先頭の位置を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754)です。  
  
##  <a name="strippath"></a>  CPathT::StripPath  
 完全修飾パスとファイル名のパス部分を削除するには、このメソッドを呼び出します。  
  
```
void StripPath();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756)です。  
  
##  <a name="striptoroot"></a>  CPathT::StripToRoot  
 ただし、ルート情報、パスのすべての部分を削除するには、このメソッドを呼び出します。  
  
```
BOOL StripToRoot();
```  
  
### <a name="return-value"></a>戻り値  
 TRUE を指定すると有効なドライブ文字を返しますが見つかりました FALSE か、パスが、それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757)です。  
  
##  <a name="unquotespaces"></a>  CPathT::UnquoteSpaces  
 先頭と末尾のパスから引用符を削除するには、このメソッドを呼び出します。  
  
```
void UnquoteSpaces();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763)です。  
  
##  <a name="xchar"></a>  CPathT::XCHAR  
 文字型。  
  
```
typedef StringType::XCHAR XCHAR;
```  
  
### <a name="remarks"></a>コメント  
 `StringType` テンプレート パラメーターには、`CPathT`です。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/atl-classes.md)   
 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)