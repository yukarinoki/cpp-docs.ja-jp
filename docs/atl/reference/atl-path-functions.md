---
title: ATL パス関数
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, path
f1_keywords:
- ATLPATH/ATL::ATLPath::AddBackslash
- ATLPATH/ATL::ATLPath::AddExtension
- ATLPATH/ATL::ATLPath::Append
- ATLPATH/ATL::ATLPath::BuildRoot
- ATLPATH/ATL::ATLPath::Canonicalize
- ATLPATH/ATL::ATLPath::Combine
- ATLPATH/ATL::ATLPath::CommonPrefix
- ATLPATH/ATL::ATLPath::CompactPath
- ATLPATH/ATL::ATLPath::CompactPathEx
- ATLPATH/ATL::ATLPath::FileExists
- ATLPATH/ATL::ATLPath::FindExtension
- ATLPATH/ATL::ATLPath::FindFileName
- ATLPATH/ATL::ATLPath::GetDriveNumber
- ATLPATH/ATL::ATLPath::IsDirectory
- ATLPATH/ATL::ATLPath::IsFileSpec
- ATLPATH/ATL::ATLPath::IsPrefix
- ATLPATH/ATL::ATLPath::IsRelative
- ATLPATH/ATL::ATLPath::IsRoot
- ATLPATH/ATL::ATLPath::IsSameRoot
- ATLPATH/ATL::ATLPath::IsUNC
- ATLPATH/ATL::ATLPath::IsUNCServer
- ATLPATH/ATL::ATLPath::IsUNCServerShare
- ATLPATH/ATL::ATLPath::MakePretty
- ATLPATH/ATL::ATLPath::MatchSpec
- ATLPATH/ATL::ATLPath::QuoteSpaces
- ATLPATH/ATL::ATLPath::RelativePathTo
- ATLPATH/ATL::ATLPath::RemoveArgs
- ATLPATH/ATL::ATLPath::RemoveBackslash
- ATLPATH/ATL::ATLPath::RemoveBlanks
- ATLPATH/ATL::ATLPath::RemoveExtension
- ATLPATH/ATL::ATLPath::RemoveFileSpec
- ATLPATH/ATL::ATLPath::RenameExtension
- ATLPATH/ATL::ATLPath::SkipRoot
- ATLPATH/ATL::ATLPath::StripPath
- ATLPATH/ATL::ATLPath::StripToRoot
- ATLPATH/ATL::ATLPath::UnquoteSpaces
ms.assetid: d1ec2b8d-7ec7-43ea-90dd-0a740d2a742b
ms.openlocfilehash: f3d8fa63e7fd20f8a0d6759fee8417b3fbc29486
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319215"
---
# <a name="atl-path-functions"></a>ATL パス関数

ATL は[、パスを CPathT](cpatht-class.md)の形式で操作するための ATLPath クラスを提供します。 このコードは atlpath.h にあります。

### <a name="related-classes"></a>関連するクラス

|||
|-|-|
|[CPathT クラス](cpatht-class.md)|このクラスはパスを表します。|

### <a name="related-typedefs"></a>関連する型定義

|||
|-|-|
|`CPath`|を使用した`CString` [CPathT](cpatht-class.md)の特殊化。|
|`CPathA`|を使用した`CStringA` [CPathT](cpatht-class.md)の特殊化。|
|`CPathW`|を使用した`CStringW` [CPathT](cpatht-class.md)の特殊化。|

### <a name="functions"></a>関数

|||
|-|-|
|[ATLPath::AddBackslash](#addbackslash)|この関数は、[パスの追加バックスラッシュ](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)のオーバーロードされたラッパーです。|
|[ATLPath::AddExtension](#addextension)|この関数は、[パスの追加拡張機能](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)のラッパーをオーバーロードします。|
|[ATLPath::Append](#append)|この関数は、[パスアペント](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)のオーバーロードされたラッパーです。|
|[ATLPath::BuildRoot](#buildroot)|この関数は、[パスビルドルート](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)のオーバーロードされたラッパーです。|
|[ATLPath::Canonicalize](#canonicalize)|この関数は[、PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)のオーバーロードされたラッパーです。|
|[ATLPath::Combine](#combine)|この関数は[、PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)のオーバーロードされたラッパーです。|
|[ATLPath::CommonPrefix](#commonprefix)|この関数は、[パスコモン プレフィックス](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)のオーバーロードされたラッパーです。|
|[ATLPath::CompactPath](#compactpath)|この関数は、[パスのパスのラッパーをオーバーロードします](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)。|
|[ATLPath::CompactPathEx](#compactpathex)|この関数は、[パスコンパクトパスエックス](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)のオーバーロードされたラッパーです。|
|[ATLPath::FileExists](#fileexists)|この関数は、[パスファイルの](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)オーバーロードされたラッパーです。|
|[ATLPath::FindExtension](#findextension)|この関数は、[パス FindExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)のオーバーロードされたラッパーです。|
|[ATLPath::FindFileName](#findfilename)|この関数は、[パス検索ファイル名](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)のオーバーロードされたラッパーです。|
|[ATLPath::GetDriveNumber](#getdrivenumber)|この関数は、[パス取得ドライブ番号](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)のオーバーロードされたラッパーです。|
|[ATLPath::IsDirectory](#isdirectory)|この関数は[、PathIsDirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)のオーバーロードされたラッパーです。|
|[ATLPath::IsFileSpec](#isfilespec)|この関数は、[オーバーロードされたラッパーです](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)。|
|[ATLPath::IsPrefix](#isprefix)|この関数は[、PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)のオーバーロードされたラッパーです。|
|[ATLPath::IsRelative](#isrelative)|この関数は[、PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)のオーバーロードされたラッパーです。|
|[ATLPath::IsRoot](#isroot)|この関数は[、PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)のオーバーロードされたラッパーです。|
|[ATLPath::IsSameRoot](#issameroot)|この関数は[、PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)のオーバーロードされたラッパーです。|
|[ATLPath::IsUNC](#isunc)|この関数は[、PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)のオーバーロードされたラッパーです。|
|[ATLPath::IsUNCServer](#isuncserver)|この関数は、[パスIsUNCサーバー](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)のオーバーロードされたラッパーです。|
|[ATLPath::IsUNCServerShare](#isuncservershare)|この関数は、[パスシスUNCサーバーシェア](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)のオーバーロードされたラッパーです。|
|[ATLPath::MakePretty](#makepretty)|この関数は、[パスメイクプリティ](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)のオーバーロードされたラッパーです。|
|[ATLPath::MatchSpec](#matchspec)|この関数は、[パスマッチペック](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)のオーバーロードされたラッパーです。|
|[ATLPath::QuoteSpaces](#quotespaces)|この関数は、[パスクオーテーションスペース](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)のオーバーロードされたラッパーです。|
|[ATLPath::RelativePathTo](#relativepathto)|この関数は、[パス相対パスの](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)オーバーロードされたラッパーです。|
|[ATLPath::RemoveArgs](#removeargs)|この関数は、[オーバーロードされたラッパーです](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)。|
|[ATLPath::RemoveBackslash](#removebackslash)|この関数は、[パス削除バックスラッシュ](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)のオーバーロードされたラッパーです。|
|[ATLPath::RemoveBlanks](#removeblanks)|この関数は、[パス除去空白](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)のオーバーロードされたラッパーです。|
|[ATLPath::RemoveExtension](#removeextension)|この関数は、オーバーロードされたラッパー[です](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)。|
|[ATLPath::RemoveFileSpec](#removefilespec)|この関数は、オーバーロードされたラッパー[です](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)。|
|[ATLPath::RenameExtension](#renameextension)|この関数は、[パスの名前を変更拡張機能](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)のオーバーロードされたラッパーです。|
|[ATLPath::SkipRoot](#skiproot)|この関数は、[パススキップルート](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)のオーバーロードされたラッパーです。|
|[ATLPath::StripPath](#strippath)|この関数は、[パスストリップパス](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)のオーバーロードされたラッパーです。|
|[ATLPath::StripToRoot](#striptoroot)|この関数は、[パスストリップルートルート](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)のオーバーロードされたラッパーです。|
|[ATLPath::UnquoteSpaces](#unquotespaces)|この関数は、[パスアンクォートスペース](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)のオーバーロードされたラッパーです。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlpath.h

## <a name="atlpathaddbackslash"></a><a name="addbackslash"></a>ATLパス::AddBackSlash

この関数は、[パスの追加バックスラッシュ](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、「パスの追加バックスラッシュ](/windows/win32/api/shlwapi/nf-shlwapi-pathaddbackslashw)」を参照してください。

## <a name="atlpathaddextension"></a><a name="addextension"></a>アトルパス::拡張機能の追加

この関数は、[パスの追加拡張機能](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)のラッパーをオーバーロードします。

### <a name="syntax"></a>構文

```
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>解説

詳細については[、「パスの追加拡張](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)」を参照してください。

## <a name="atlpathappend"></a><a name="append"></a>ATLパス::追加

この関数は、[パスアペント](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>解説

詳細については[、パスの追加](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)を参照してください。

## <a name="atlpathbuildroot"></a><a name="buildroot"></a>ATLパス::ビルドルート

この関数は、[パスビルドルート](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>解説

詳細については[、「パスビルドルート](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)」を参照してください。

## <a name="atlpathcanonicalize"></a><a name="canonicalize"></a>ATLPath::正規化

この関数は[、PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>解説

詳細については[、「パス正規化](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)」を参照してください。

## <a name="atlpathcombine"></a><a name="combine"></a>ATLパス::コンバイン

この関数は[、PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline char* Combine(
   char* pszDest,
   const char* pszDir,
   const char* pszFile
);

inline wchar_t* Combine(
   wchar_t* pszDest,
   const wchar_t* pszDir,
   const wchar_t* pszFile);
```

### <a name="remarks"></a>解説

詳細については、「パス結合」を参照してください。

## <a name="atlpathcommonprefix"></a><a name="commonprefix"></a>ATL パス::コモンプレフィックス

この関数は、[パスコモン プレフィックス](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline int CommonPrefix(
   const char* pszFile1,
   const char* pszFile2,
   char* pszDest);

inline int CommonPrefix(
   const wchar_t* pszFile1,
   const wchar_t* pszFile2,
   wchar_t* pszDest);
```

### <a name="remarks"></a>解説

詳細については[、「パスコモン プレフィックス](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)」を参照してください。

## <a name="atlpathcompactpath"></a><a name="compactpath"></a>ATLパス::コンパクトパス

この関数は、[パスのパスのラッパーをオーバーロードします](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)。

### <a name="syntax"></a>構文

```
inline BOOL CompactPath(
   HDC hDC,
   char* pszPath,
   UINT dx);

inline BOOL CompactPath(
   HDC hDC,
   wchar_t* pszPath,
   UINT dx);
```

### <a name="remarks"></a>解説

詳細については、[パスのパスを](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)参照してください。

## <a name="atlpathcompactpathex"></a><a name="compactpathex"></a>ATLパス::コンパクトパスエックス

この関数は、[パスコンパクトパスエックス](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL CompactPathEx(
   char* pszDest,
   const char* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);

inline BOOL CompactPathEx(
   wchar_t* pszDest,
   const wchar_t* pszSrc,
   UINT nMaxChars,
   DWORD dwFlags);
```

### <a name="remarks"></a>解説

詳細については[、パスコンパクトパスを](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)参照してください。

## <a name="atlpathfileexists"></a><a name="fileexists"></a>ファイルパス::ファイルが存在します

この関数は、[パスファイルの](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)オーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、パスファイルの存在](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)を参照してください。

## <a name="atlpathfindextension"></a><a name="findextension"></a>アトルパス::拡張を検索

この関数は、[パス FindExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、「パス検索拡張機能」](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)を参照してください。

## <a name="atlpathfindfilename"></a><a name="findfilename"></a>ファイル名を検索します。

この関数は、[パス検索ファイル名](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、パスファイル名](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)を参照してください。

## <a name="atlpathgetdrivenumber"></a><a name="getdrivenumber"></a>アトルパス::ゲットドライブナンバー

この関数は、[パス取得ドライブ番号](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については、「[パスの取得ドライブ番号」](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)を参照してください。

## <a name="atlpathisdirectory"></a><a name="isdirectory"></a>アトルパス::イズディレクトリ

この関数は[、PathIsDirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)のオーバーロードされたラッパーです。

```
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については、PathIsDirectory を参照してください。

## <a name="atlpathisfilespec"></a><a name="isfilespec"></a>ファイルスペック

この関数は、[オーバーロードされたラッパーです](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)。

### <a name="syntax"></a>構文

```
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、パスを参照してください](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)。

## <a name="atlpathisprefix"></a><a name="isprefix"></a>を使用します。

この関数は[、PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については、[パスのプレフィックス](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)を参照してください。

## <a name="atlpathisrelative"></a><a name="isrelative"></a>ATLパス::イズアブール

この関数は[、PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)を参照してください。

## <a name="atlpathisroot"></a><a name="isroot"></a>ATLパス::イズルート

この関数は[、PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)を参照してください。

## <a name="atlpathissameroot"></a><a name="issameroot"></a>ATLパス::イササミルート

この関数は[、PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>解説

詳細については[、PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)を参照してください。

## <a name="atlpathisunc"></a><a name="isunc"></a>ATLパス::イスUNC

この関数は[、PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)を参照してください。

## <a name="atlpathisuncserver"></a><a name="isuncserver"></a>アトルパス::サーバー

この関数は、[パスIsUNCサーバー](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、パスリスンサーバー](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)を参照してください。

## <a name="atlpathisuncservershare"></a><a name="isuncservershare"></a>を使用します。

この関数は、[パスシスUNCサーバーシェア](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、パスリスンサーバーの共有](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)を参照してください。

## <a name="atlpathmakepretty"></a><a name="makepretty"></a>ATLパス::メイクプリティ

この関数は、[パスメイクプリティ](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については、「[パスメイクプリティ](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)」を参照してください。

## <a name="atlpathmatchspec"></a><a name="matchspec"></a>ATLパス:マッチスペック

この関数は、[パスマッチペック](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>解説

詳細については[、パスマッチの仕様](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)を参照してください。

## <a name="atlpathquotespaces"></a><a name="quotespaces"></a>ATLパス::引用スペース

この関数は、[パスクオーテーションスペース](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、「パスクオートスペース](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)」を参照してください。

## <a name="atlpathrelativepathto"></a><a name="relativepathto"></a>アトルパス::相対パス

この関数は、[パス相対パスの](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)オーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL RelativePathTo(
   char* pszPath,
   const char* pszFrom,
   DWORD dwAttrFrom,
   const char* pszTo,
   DWORD dwAttrTo);

inline BOOL RelativePathTo(
   wchar_t* pszPath,
   const wchar_t* pszFrom,
   DWORD dwAttrFrom,
   const wchar_t* pszTo,
   DWORD dwAttrTo);
```

### <a name="remarks"></a>解説

詳細については、「[パス相対パスを](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)参照してください。

## <a name="atlpathremoveargs"></a><a name="removeargs"></a>アトルパス::削除引数

この関数は、[オーバーロードされたラッパーです](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)。

### <a name="syntax"></a>構文

```
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については、「[パスの削除引数](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)」を参照してください。

## <a name="atlpathremovebackslash"></a><a name="removebackslash"></a>ATLパス::削除バックスラッシュ

この関数は、[パス削除バックスラッシュ](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については、「[パス削除バックスラッシュ](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)」を参照してください。

## <a name="atlpathremoveblanks"></a><a name="removeblanks"></a>ATLパス::ブランクの削除

この関数は、[パス除去空白](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については、「[パス削除ブランク」](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)を参照してください。

## <a name="atlpathremoveextension"></a><a name="removeextension"></a>拡張の削除

この関数は、オーバーロードされたラッパー[です](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)。

### <a name="syntax"></a>構文

```
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、「パスの削除拡張](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)」を参照してください。

## <a name="atlpathremovefilespec"></a><a name="removefilespec"></a>ファイルの削除

この関数は、オーバーロードされたラッパー[です](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)。

### <a name="syntax"></a>構文

```
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については、「[パスの削除ファイルの指定」](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)を参照してください。

## <a name="atlpathrenameextension"></a><a name="renameextension"></a>ATLパス::拡張機能の名前の変更

この関数は、[パスの名前を変更拡張機能](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>解説

詳細については、「[パスの名前変更拡張機能」](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)を参照してください。

## <a name="atlpathskiproot"></a><a name="skiproot"></a>ATLパス::スキップルート

この関数は、[パススキップルート](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、「パススキップルート」](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)を参照してください。

## <a name="atlpathstrippath"></a><a name="strippath"></a>ATLパス::ストリップパス

この関数は、[パスストリップパス](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については、「[パスストリップパス](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)」を参照してください。

## <a name="atlpathstriptoroot"></a><a name="striptoroot"></a>ATLパス::ストリップトルート

この関数は、[パスストリップルートルート](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、「パスストリップルート」](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)を参照してください。

## <a name="atlpathunquotespaces"></a><a name="unquotespaces"></a>ATLPath::クォートなしスペース

この関数は、[パスアンクォートスペース](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)のオーバーロードされたラッパーです。

### <a name="syntax"></a>構文

```
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>解説

詳細については[、「パスアンクォートスペース](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)」を参照してください。
