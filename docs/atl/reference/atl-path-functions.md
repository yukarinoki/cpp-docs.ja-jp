---
title: ATL パス関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdb658b179e3e3488b070203ad7f0909610d4fd8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054645"
---
# <a name="atl-path-functions"></a>ATL パス関数

ATL ATLPath クラスの形式でパスを操作するためには、 [CPathT](cpatht-class.md)します。 このコードは、atlpath.h で確認できます。

### <a name="related-classes"></a>関連するクラス

|||
|-|-|
|[CPathT クラス](cpatht-class.md)|このクラスは、パスを表します。|

### <a name="related-typedefs"></a>関連の Typedef

|||
|-|-|
|`CPath`|特殊化[CPathT](cpatht-class.md)を使用して`CString`します。|
|`CPathA`|特殊化[CPathT](cpatht-class.md)を使用して`CStringA`します。|
|`CPathW`|特殊化[CPathT](cpatht-class.md)を使用して`CStringW`します。|

### <a name="functions"></a>関数

|||
|-|-|
|[ATLPath::AddBackslash](#addbackslash)|この関数はオーバー ロードされたラッパー [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha)します。|
|[ATLPath::AddExtension](#addextension)|この関数はオーバー ロードされたラッパー [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona)します。|
|[ATLPath::Append](#append)|この関数はオーバー ロードされたラッパー [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda)します。|
|[ATLPath::BuildRoot](#buildroot)|この関数はオーバー ロードされたラッパー [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota)します。|
|[ATLPath::Canonicalize](#canonicalize)|この関数はオーバー ロードされたラッパー [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea)します。|
|[ATLPath::Combine](#combine)|この関数はオーバー ロードされたラッパー [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea)します。|
|[ATLPath::CommonPrefix](#commonprefix)|この関数はオーバー ロードされたラッパー [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa)します。|
|[ATLPath::CompactPath](#compactpath)|この関数はオーバー ロードされたラッパー [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha)します。|
|[ATLPath::CompactPathEx](#compactpathex)|この関数はオーバー ロードされたラッパー [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa)します。|
|[ATLPath::FileExists](#fileexists)|この関数はオーバー ロードされたラッパー [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa)します。|
|[ATLPath::FindExtension](#findextension)|この関数はオーバー ロードされたラッパー [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona)します。|
|[ATLPath::FindFileName](#findfilename)|この関数はオーバー ロードされたラッパー [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea)します。|
|[ATLPath::GetDriveNumber](#getdrivenumber)|この関数はオーバー ロードされたラッパー [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera)します。|
|[ATLPath::IsDirectory](#isdirectory)|この関数はオーバー ロードされたラッパー [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya)します。|
|[ATLPath::IsFileSpec](#isfilespec)|この関数はオーバー ロードされたラッパー [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca)します。|
|[ATLPath::IsPrefix](#isprefix)|この関数はオーバー ロードされたラッパー [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa)します。|
|[ATLPath::IsRelative](#isrelative)|この関数はオーバー ロードされたラッパー [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea)します。|
|[ATLPath::IsRoot](#isroot)|この関数はオーバー ロードされたラッパー [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota)します。|
|[ATLPath::IsSameRoot](#issameroot)|この関数はオーバー ロードされたラッパー [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota)します。|
|[ATLPath::IsUNC](#isunc)|この関数はオーバー ロードされたラッパー [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca)します。|
|[ATLPath::IsUNCServer](#isuncserver)|この関数はオーバー ロードされたラッパー [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera)します。|
|[ATLPath::IsUNCServerShare](#isuncservershare)|この関数はオーバー ロードされたラッパー [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea)します。|
|[ATLPath::MakePretty](#makepretty)|この関数はオーバー ロードされたラッパー [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya)します。|
|[ATLPath::MatchSpec](#matchspec)|この関数はオーバー ロードされたラッパー [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca)します。|
|[ATLPath::QuoteSpaces](#quotespaces)|この関数はオーバー ロードされたラッパー [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa)します。|
|[ATLPath::RelativePathTo](#relativepathto)|この関数はオーバー ロードされたラッパー [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa)します。|
|[ATLPath::RemoveArgs](#removeargs)|この関数はオーバー ロードされたラッパー [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa)します。|
|[ATLPath::RemoveBackslash](#removebackslash)|この関数はオーバー ロードされたラッパー [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha)します。|
|[ATLPath::RemoveBlanks](#removeblanks)|この関数はオーバー ロードされたラッパー [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa)します。|
|[ATLPath::RemoveExtension](#removeextension)|この関数はオーバー ロードされたラッパー [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona)します。|
|[ATLPath::RemoveFileSpec](#removefilespec)|この関数はオーバー ロードされたラッパー [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca)します。|
|[ATLPath::RenameExtension](#renameextension)|この関数はオーバー ロードされたラッパー [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona)します。|
|[ATLPath::SkipRoot](#skiproot)|この関数はオーバー ロードされたラッパー [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota)します。|
|[ATLPath::StripPath](#strippath)|この関数はオーバー ロードされたラッパー [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha)します。|
|[ATLPath::StripToRoot](#striptoroot)|この関数はオーバー ロードされたラッパー [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota)します。|
|[ATLPath::UnquoteSpaces](#unquotespaces)|この関数はオーバー ロードされたラッパー [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa)します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlpath.h

## <a name="addbackslash"></a> ATLPath::AddBackSlash

この関数はオーバー ロードされたラッパー [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha)します。

### <a name="syntax"></a>構文

```
inline char* AddBackslash(char* pszPath);
inline wchar_t* AddBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha)詳細についてはします。

## <a name="addextension"></a> ATLPath::AddExtension

この関数はオーバー ロードされたラッパー [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona)します。

### <a name="syntax"></a>構文

```
inline BOOL AddExtension(char* pszPath, const char* pszExtension);
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);
```

### <a name="remarks"></a>Remarks

参照してください[PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona)詳細についてはします。

## <a name="append"></a> ATLPath::Append

この関数はオーバー ロードされたラッパー [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda)します。

### <a name="syntax"></a>構文

```
inline BOOL Append(char* pszPath, const char* pszMore);
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);
```

### <a name="remarks"></a>Remarks

参照してください[PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda)詳細についてはします。

## <a name="buildroot"></a> ATLPath::BuildRoot

この関数はオーバー ロードされたラッパー [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota)します。

### <a name="syntax"></a>構文

```
inline char* BuildRoot(char* pszPath, int iDrive);
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);
```

### <a name="remarks"></a>Remarks

参照してください[PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota)詳細についてはします。

## <a name="canonicalize"></a> ATLPath::Canonicalize

この関数はオーバー ロードされたラッパー [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea)します。

### <a name="syntax"></a>構文

```
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);
```

### <a name="remarks"></a>Remarks

参照してください[PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea)詳細についてはします。

## <a name="combine"></a> ATLPath::Combine

この関数はオーバー ロードされたラッパー [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea)します。

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

### <a name="remarks"></a>Remarks

詳細については、PathCombine を参照してください。

## <a name="commonprefix"></a> ATLPath::CommonPrefix

この関数はオーバー ロードされたラッパー [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa)します。

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

### <a name="remarks"></a>Remarks

参照してください[PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa)詳細についてはします。

## <a name="compactpath"></a> ATLPath::CompactPath

この関数はオーバー ロードされたラッパー [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha)します。

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

### <a name="remarks"></a>Remarks

参照してください[PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha)詳細についてはします。

## <a name="compactpathex"></a> ATLPath::CompactPathEx

この関数はオーバー ロードされたラッパー [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa)します。

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

### <a name="remarks"></a>Remarks

参照してください[PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa)詳細についてはします。

## <a name="fileexists"></a> ATLPath::FileExists

この関数はオーバー ロードされたラッパー [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa)します。

### <a name="syntax"></a>構文

```
inline BOOL FileExists(const char* pszPath);
inline BOOL FileExists(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa)詳細についてはします。

## <a name="findextension"></a> ATLPath::FindExtension

この関数はオーバー ロードされたラッパー [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona)します。

### <a name="syntax"></a>構文

```
inline char* FindExtension(const char* pszPath);
inline wchar_t* FindExtension(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona)詳細についてはします。

## <a name="findfilename"></a> ATLPath::FindFileName

この関数はオーバー ロードされたラッパー [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea)します。

### <a name="syntax"></a>構文

```
inline char* FindFileName(const char* pszPath);
inline wchar_t* FindFileName(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea)詳細についてはします。

## <a name="getdrivenumber"></a> ATLPath::GetDriveNumber

この関数はオーバー ロードされたラッパー [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera)します。

### <a name="syntax"></a>構文

```
inline int GetDriveNumber(const char* pszPath);
inline int GetDriveNumber(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera)詳細についてはします。

## <a name="isdirectory"></a>  ATLPath::IsDirectory

この関数はオーバー ロードされたラッパー [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya)します。

```
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

詳細については、PathIsDirectory を参照してください。

## <a name="isfilespec"></a> ATLPath::IsFileSpec

この関数はオーバー ロードされたラッパー [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca)します。

### <a name="syntax"></a>構文

```
inline BOOL IsFileSpec(const char* pszPath);
inline BOOL IsFileSpec(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca)詳細についてはします。

## <a name="isprefix"></a> ATLPath::IsPrefix

この関数はオーバー ロードされたラッパー [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa)します。

### <a name="syntax"></a>構文

```
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa)詳細についてはします。

## <a name="isrelative"></a> ATLPath::IsRelative

この関数はオーバー ロードされたラッパー [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea)します。

### <a name="syntax"></a>構文

```
inline BOOL IsRelative(const char* pszPath);
inline BOOL IsRelative(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea)詳細についてはします。

## <a name="isroot"></a> ATLPath::IsRoot

この関数はオーバー ロードされたラッパー [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota)します。

### <a name="syntax"></a>構文

```
inline BOOL IsRoot(const char* pszPath);
inline BOOL IsRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota)詳細についてはします。

## <a name="issameroot"></a> ATLPath::IsSameRoot

この関数はオーバー ロードされたラッパー [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota)します。

### <a name="syntax"></a>構文

```
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);
```

### <a name="remarks"></a>Remarks

参照してください[PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota)詳細についてはします。

## <a name="isunc"></a> ATLPath::IsUNC

この関数はオーバー ロードされたラッパー [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca)します。

### <a name="syntax"></a>構文

```
inline BOOL IsUNC(const char* pszPath);
inline BOOL IsUNC(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca)詳細についてはします。

## <a name="isuncserver"></a> ATLPath::IsUNCServer

この関数はオーバー ロードされたラッパー [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera)します。

### <a name="syntax"></a>構文

```
inline BOOL IsUNCServer(const char* pszPath);
inline BOOL IsUNCServer(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera)詳細についてはします。

## <a name="isuncservershare"></a> ATLPath::IsUNCServerShare

この関数はオーバー ロードされたラッパー [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea)します。

### <a name="syntax"></a>構文

```
inline BOOL IsUNCServerShare(const char* pszPath);
inline BOOL IsUNCServerShare(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea)詳細についてはします。

## <a name="makepretty"></a> ATLPath::MakePretty

この関数はオーバー ロードされたラッパー [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya)します。

### <a name="syntax"></a>構文

```
inline BOOL MakePretty(char* pszPath);
inline BOOL MakePretty(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya)詳細についてはします。

## <a name="matchspec"></a> ATLPath::MatchSpec

この関数はオーバー ロードされたラッパー [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca)します。

### <a name="syntax"></a>構文

```
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);
```

### <a name="remarks"></a>Remarks

参照してください[PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca)詳細についてはします。

## <a name="quotespaces"></a> ATLPath::QuoteSpaces

この関数はオーバー ロードされたラッパー [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa)します。

### <a name="syntax"></a>構文

```
inline void QuoteSpaces(char* pszPath);
inline void QuoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa)詳細についてはします。

## <a name="relativepathto"></a> ATLPath::RelativePathTo

この関数はオーバー ロードされたラッパー [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa)します。

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

### <a name="remarks"></a>Remarks

参照してください[PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa)詳細についてはします。

## <a name="removeargs"></a> ATLPath::RemoveArgs

この関数はオーバー ロードされたラッパー [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa)します。

### <a name="syntax"></a>構文

```
inline void RemoveArgs(char* pszPath);
inline void RemoveArgs(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa)詳細についてはします。

## <a name="removebackslash"></a> ATLPath::RemoveBackslash

この関数はオーバー ロードされたラッパー [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha)します。

### <a name="syntax"></a>構文

```
inline char* RemoveBackslash(char* pszPath);
inline wchar_t* RemoveBackslash(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha)詳細についてはします。

## <a name="removeblanks"></a> ATLPath::RemoveBlanks

この関数はオーバー ロードされたラッパー [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa)します。

### <a name="syntax"></a>構文

```
inline void RemoveBlanks(char* pszPath);
inline void RemoveBlanks(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa)詳細についてはします。

## <a name="removeextension"></a> ATLPath::RemoveExtension

この関数はオーバー ロードされたラッパー [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona)します。

### <a name="syntax"></a>構文

```
inline void RemoveExtension(char* pszPath);
inline void RemoveExtension(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona)詳細についてはします。

## <a name="removefilespec"></a> ATLPath::RemoveFileSpec

この関数はオーバー ロードされたラッパー [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca)します。

### <a name="syntax"></a>構文

```
inline BOOL RemoveFileSpec(char* pszPath);
inline BOOL RemoveFileSpec(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca)詳細についてはします。

## <a name="renameextension"></a> ATLPath::RenameExtension

この関数はオーバー ロードされたラッパー [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona)します。

### <a name="syntax"></a>構文

```
inline BOOL RenameExtension(char* pszPath, const char* pszExt);
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);
```

### <a name="remarks"></a>Remarks

参照してください[PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona)詳細についてはします。

## <a name="skiproot"></a> ATLPath::SkipRoot

この関数はオーバー ロードされたラッパー [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota)します。

### <a name="syntax"></a>構文

```
inline char* SkipRoot(const char* pszPath);
inline wchar_t* SkipRoot(const wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota)詳細についてはします。

## <a name="strippath"></a> ATLPath::StripPath

この関数はオーバー ロードされたラッパー [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha)します。

### <a name="syntax"></a>構文

```
inline void StripPath(char* pszPath);
inline void StripPath(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha)詳細についてはします。

## <a name="striptoroot"></a> ATLPath::StripToRoot

この関数はオーバー ロードされたラッパー [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota)します。

### <a name="syntax"></a>構文

```
inline BOOL StripToRoot(char* pszPath);
inline BOOL StripToRoot(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota)詳細についてはします。

## <a name="unquotespaces"></a> ATLPath::UnquoteSpaces

この関数はオーバー ロードされたラッパー [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa)します。

### <a name="syntax"></a>構文

```
inline void UnquoteSpaces(char* pszPath);
inline void UnquoteSpaces(wchar_t* pszPath);
```

### <a name="remarks"></a>Remarks

参照してください[PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa)詳細についてはします。

