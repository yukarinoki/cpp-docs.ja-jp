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
ms.openlocfilehash: ad0db4641731f4c92550fad075b759957383c52a
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027578"
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
|[ATLPath::AddBackslash](#addbackslash)|この関数はオーバー ロードされたラッパー [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561)します。|  
|[ATLPath::AddExtension](#addextension)|この関数はオーバー ロードされたラッパー [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563)します。|  
|[ATLPath::Append](#append)|この関数はオーバー ロードされたラッパー [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565)します。|  
|[ATLPath::BuildRoot](#buildroot)|この関数はオーバー ロードされたラッパー [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567)します。|  
|[ATLPath::Canonicalize](#canonicalize)|この関数はオーバー ロードされたラッパー [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569)します。|  
|[ATLPath::Combine](#combine)|この関数はオーバー ロードされたラッパー [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571)します。|  
|[ATLPath::CommonPrefix](#commonprefix)|この関数はオーバー ロードされたラッパー [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574)します。|  
|[ATLPath::CompactPath](#compactpath)|この関数はオーバー ロードされたラッパー [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575)します。|  
|[ATLPath::CompactPathEx](#compactpathex)|この関数はオーバー ロードされたラッパー [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578)します。|  
|[ATLPath::FileExists](#fileexists)|この関数はオーバー ロードされたラッパー [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584)します。|  
|[ATLPath::FindExtension](#findextension)|この関数はオーバー ロードされたラッパー [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587)します。|  
|[ATLPath::FindFileName](#findfilename)|この関数はオーバー ロードされたラッパー [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)します。|  
|[ATLPath::GetDriveNumber](#getdrivenumber)|この関数はオーバー ロードされたラッパー [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612)します。|  
|[ATLPath::IsDirectory](#isdirectory)|この関数はオーバー ロードされたラッパー [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621)します。|  
|[ATLPath::IsFileSpec](#isfilespec)|この関数はオーバー ロードされたラッパー [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627)します。|  
|[ATLPath::IsPrefix](#isprefix)|この関数はオーバー ロードされたラッパー [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650)します。|  
|[ATLPath::IsRelative](#isrelative)|この関数はオーバー ロードされたラッパー [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660)します。|  
|[ATLPath::IsRoot](#isroot)|この関数はオーバー ロードされたラッパー [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674)します。|  
|[ATLPath::IsSameRoot](#issameroot)|この関数はオーバー ロードされたラッパー [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687)します。|  
|[ATLPath::IsUNC](#isunc)|この関数はオーバー ロードされたラッパー [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712)します。|  
|[ATLPath::IsUNCServer](#isuncserver)|この関数はオーバー ロードされたラッパー [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722)します。|  
|[ATLPath::IsUNCServerShare](#isuncservershare)|この関数はオーバー ロードされたラッパー [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723)します。|  
|[ATLPath::MakePretty](#makepretty)|この関数はオーバー ロードされたラッパー [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725)します。|  
|[ATLPath::MatchSpec](#matchspec)|この関数はオーバー ロードされたラッパー [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727)します。|  
|[ATLPath::QuoteSpaces](#quotespaces)|この関数はオーバー ロードされたラッパー [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739)します。|  
|[ATLPath::RelativePathTo](#relativepathto)|この関数はオーバー ロードされたラッパー [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740)します。|  
|[ATLPath::RemoveArgs](#removeargs)|この関数はオーバー ロードされたラッパー [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742)します。|  
|[ATLPath::RemoveBackslash](#removebackslash)|この関数はオーバー ロードされたラッパー [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743)します。|  
|[ATLPath::RemoveBlanks](#removeblanks)|この関数はオーバー ロードされたラッパー [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745)します。|  
|[ATLPath::RemoveExtension](#removeextension)|この関数はオーバー ロードされたラッパー [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746)します。|  
|[ATLPath::RemoveFileSpec](#removefilespec)|この関数はオーバー ロードされたラッパー [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748)します。|  
|[ATLPath::RenameExtension](#renameextension)|この関数はオーバー ロードされたラッパー [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749)します。|  
|[ATLPath::SkipRoot](#skiproot)|この関数はオーバー ロードされたラッパー [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754)します。|  
|[ATLPath::StripPath](#strippath)|この関数はオーバー ロードされたラッパー [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756)します。|  
|[ATLPath::StripToRoot](#striptoroot)|この関数はオーバー ロードされたラッパー [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757)します。|  
|[ATLPath::UnquoteSpaces](#unquotespaces)|この関数はオーバー ロードされたラッパー [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763)します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlpath.h  

## <a name="addbackslash"></a> ATLPath::AddBackSlash

この関数はオーバー ロードされたラッパー [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline char* AddBackslash(char* pszPath);  
inline wchar_t* AddBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561)詳細についてはします。  
  
 
  

## <a name="addextension"></a> ATLPath::AddExtension
 この関数はオーバー ロードされたラッパー [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL AddExtension(char* pszPath, const char* pszExtension);  
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563)詳細についてはします。 
  
## <a name="append"></a> ATLPath::Append
 この関数はオーバー ロードされたラッパー [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL Append(char* pszPath, const char* pszMore);  
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565)詳細についてはします。  
  
 
  

## <a name="buildroot"></a> ATLPath::BuildRoot
 この関数はオーバー ロードされたラッパー [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline char* BuildRoot(char* pszPath, int iDrive);  
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567)詳細についてはします。  
  
 
  

## <a name="canonicalize"></a> ATLPath::Canonicalize
 この関数はオーバー ロードされたラッパー [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);  
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569)詳細についてはします。  
  
 
  

## <a name="combine"></a> ATLPath::Combine 
この関数はオーバー ロードされたラッパー [PathCombine](https://msdn.microsoft.com/library/windows/desktop/bb773571)します。  

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
 この関数はオーバー ロードされたラッパー [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574)します。  
  
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
 参照してください[PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574)詳細についてはします。  
  
 
  

## <a name="compactpath"></a> ATLPath::CompactPath
 この関数はオーバー ロードされたラッパー [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575)します。  
  
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
 参照してください[PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575)詳細についてはします。  
  
 
  

## <a name="compactpathex"></a> ATLPath::CompactPathEx
 この関数はオーバー ロードされたラッパー [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578)します。  
  
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
 参照してください[PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578)詳細についてはします。  
  
 
  

## <a name="fileexists"></a> ATLPath::FileExists
 この関数はオーバー ロードされたラッパー [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL FileExists(const char* pszPath);  
inline BOOL FileExists(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584)詳細についてはします。  
  
 
  

## <a name="findextension"></a> ATLPath::FindExtension
 この関数はオーバー ロードされたラッパー [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline char* FindExtension(const char* pszPath);  
inline wchar_t* FindExtension(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587)詳細についてはします。  
  
 
  

## <a name="findfilename"></a> ATLPath::FindFileName
 この関数はオーバー ロードされたラッパー [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline char* FindFileName(const char* pszPath);  
inline wchar_t* FindFileName(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)詳細についてはします。  
  
 
  

## <a name="getdrivenumber"></a> ATLPath::GetDriveNumber  
 この関数はオーバー ロードされたラッパー [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline int GetDriveNumber(const char* pszPath);  
inline int GetDriveNumber(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612)詳細についてはします。  
  
 


## <a name="isdirectory"></a>  ATLPath::IsDirectory 
この関数はオーバー ロードされたラッパー [PathIsDirectory](https://msdn.microsoft.com/library/windows/desktop/bb773621)します。

```  
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```  
### <a name="remarks"></a>Remarks
詳細については、PathIsDirectory を参照してください。  

## <a name="isfilespec"></a> ATLPath::IsFileSpec
 この関数はオーバー ロードされたラッパー [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL IsFileSpec(const char* pszPath);  
inline BOOL IsFileSpec(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627)詳細についてはします。  
  
 
  

## <a name="isprefix"></a> ATLPath::IsPrefix
 この関数はオーバー ロードされたラッパー [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);  
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650)詳細についてはします。  
  
 
  

## <a name="isrelative"></a> ATLPath::IsRelative
 この関数はオーバー ロードされたラッパー [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL IsRelative(const char* pszPath);  
inline BOOL IsRelative(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660)詳細についてはします。  
  
 
  

## <a name="isroot"></a> ATLPath::IsRoot
 この関数はオーバー ロードされたラッパー [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL IsRoot(const char* pszPath);  
inline BOOL IsRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674)詳細についてはします。  
  
 
  

## <a name="issameroot"></a> ATLPath::IsSameRoot
 この関数はオーバー ロードされたラッパー [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);  
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687)詳細についてはします。  
  
 
  

## <a name="isunc"></a> ATLPath::IsUNC
 この関数はオーバー ロードされたラッパー [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL IsUNC(const char* pszPath);  
inline BOOL IsUNC(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712)詳細についてはします。  
  
 
  

## <a name="isuncserver"></a> ATLPath::IsUNCServer
 この関数はオーバー ロードされたラッパー [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL IsUNCServer(const char* pszPath);  
inline BOOL IsUNCServer(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722)詳細についてはします。  
  
 
  

## <a name="isuncservershare"></a> ATLPath::IsUNCServerShare
 この関数はオーバー ロードされたラッパー [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL IsUNCServerShare(const char* pszPath);  
inline BOOL IsUNCServerShare(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723)詳細についてはします。  
  
 
  

## <a name="makepretty"></a> ATLPath::MakePretty
 この関数はオーバー ロードされたラッパー [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL MakePretty(char* pszPath);  
inline BOOL MakePretty(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725)詳細についてはします。  
  
 
  

## <a name="matchspec"></a> ATLPath::MatchSpec  
 この関数はオーバー ロードされたラッパー [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);  
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727)詳細についてはします。  
  
 
  

## <a name="quotespaces"></a> ATLPath::QuoteSpaces  
 この関数はオーバー ロードされたラッパー [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline void QuoteSpaces(char* pszPath);  
inline void QuoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739)詳細についてはします。  
  
 
  

## <a name="relativepathto"></a> ATLPath::RelativePathTo
 この関数はオーバー ロードされたラッパー [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740)します。  
  
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
 参照してください[PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740)詳細についてはします。  
  
 
  

## <a name="removeargs"></a> ATLPath::RemoveArgs  
 この関数はオーバー ロードされたラッパー [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline void RemoveArgs(char* pszPath);  
inline void RemoveArgs(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742)詳細についてはします。  
  
 
  

## <a name="removebackslash"></a> ATLPath::RemoveBackslash
 この関数はオーバー ロードされたラッパー [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline char* RemoveBackslash(char* pszPath);  
inline wchar_t* RemoveBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743)詳細についてはします。  
  
 
  

## <a name="removeblanks"></a> ATLPath::RemoveBlanks
 この関数はオーバー ロードされたラッパー [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline void RemoveBlanks(char* pszPath);  
inline void RemoveBlanks(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745)詳細についてはします。  
  
 
  

## <a name="removeextension"></a> ATLPath::RemoveExtension
 この関数はオーバー ロードされたラッパー [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline void RemoveExtension(char* pszPath);  
inline void RemoveExtension(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746)詳細についてはします。  
  
 
  

## <a name="removefilespec"></a> ATLPath::RemoveFileSpec
 この関数はオーバー ロードされたラッパー [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL RemoveFileSpec(char* pszPath);  
inline BOOL RemoveFileSpec(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748)詳細についてはします。  
  
 
  

## <a name="renameextension"></a> ATLPath::RenameExtension
 この関数はオーバー ロードされたラッパー [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL RenameExtension(char* pszPath, const char* pszExt);  
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749)詳細についてはします。  
  
 
  

## <a name="skiproot"></a> ATLPath::SkipRoot
 この関数はオーバー ロードされたラッパー [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline char* SkipRoot(const char* pszPath);  
inline wchar_t* SkipRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754)詳細についてはします。  
  
 
  

## <a name="strippath"></a> ATLPath::StripPath
 この関数はオーバー ロードされたラッパー [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline void StripPath(char* pszPath);  
inline void StripPath(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756)詳細についてはします。  
  
 
  


## <a name="striptoroot"></a> ATLPath::StripToRoot
 この関数はオーバー ロードされたラッパー [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline BOOL StripToRoot(char* pszPath);  
inline BOOL StripToRoot(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757)詳細についてはします。  
  
 
  

## <a name="unquotespaces"></a> ATLPath::UnquoteSpaces
 この関数はオーバー ロードされたラッパー [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763)します。  
  
### <a name="syntax"></a>構文  
  
```  
inline void UnquoteSpaces(char* pszPath);  
inline void UnquoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763)詳細についてはします。  
  
 
  
 
