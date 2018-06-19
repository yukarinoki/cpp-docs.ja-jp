---
title: ATL ユーティリティのリファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b802d8764dda321e2e313f793f4f2e4745dbcc7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363824"
---
# <a name="atl-utilities-reference"></a>ATL ユーティリティのリファレンス
ATL の形式でパスと Url を操作するためのコードには、 [CPathT](../atl/reference/cpatht-class.md)と[CUrl](../atl/reference/curl-class.md)です。 スレッド プール、 [CThreadPool](../atl/reference/cthreadpool-class.md)アプリケーションで使用できます。 このコードは、atlpath.h と atlutil.h 含まれています。  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[CPathT クラス](../atl/reference/cpatht-class.md)|このクラスは、パスを表します。|  
|[CDebugReportHook クラス](../atl/reference/cdebugreporthook-class.md)|このクラスを使用すると、名前付きパイプにデバッグ レポートを送信します。|  
|[CNonStatelessWorker クラス](../atl/reference/cnonstatelessworker-class.md)|スレッド プールからの要求を受信し、各要求の作成し、破棄がワーカー オブジェクトに渡されます。|  
|[CNoWorkerThread クラス](../atl/reference/cnoworkerthread-class.md)|引数としてこのクラスを使用して、`MonitorClass`動的キャッシュのメンテナンスを無効にする場合、キャッシュ クラスをテンプレート パラメーター。|  
|[CThreadPool クラス](../atl/reference/cthreadpool-class.md)|このクラスは、作業項目のキューを処理するワーカー スレッドのプールを提供します。|  
|[CUrl クラス](../atl/reference/curl-class.md)|このクラスは、URL を表します。 既存の URL を解析するかどうか、他のユーザーとは無関係に、URL の各要素を操作することができます文字列または文字列を最初から作成します。|  
|[CWorkerThread クラス](../atl/reference/cworkerthread-class.md)|このクラスは、ワーカー スレッドを作成または既存のものを使用して化し、1 つまたは複数のカーネル オブジェクトのハンドルを待機がシグナルを受け取るハンドルのいずれかに指定されたクライアント関数を実行します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[CPath](../atl/reference/atl-typedefs.md#cpath)|特殊化した[CPathT](../atl/reference/cpatht-class.md)を使用して`CString`です。|  
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|特殊化した[CPathT](../atl/reference/cpatht-class.md)を使用して`CStringA`です。|  
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|特殊化した[CPathT](../atl/reference/cpatht-class.md)を使用して`CStringW`です。|  
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|によって使用される種類[CUrl](../atl/reference/curl-class.md)のポート番号を指定します。|  
  
### <a name="enums"></a>列挙体  
  
|||  
|-|-|  
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|この列挙体のメンバーがで認識されるスキームの定数を提供[CUrl](../atl/reference/curl-class.md)です。|  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|URL を標準形式に変換します。安全でない文字や空白をエスケープ シーケンスに変換する処理などが含まれます。|  
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|ベース URL と相対 URL を結合して、1 つの標準形式の URL にします。|  
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|すべての安全でない文字をエスケープ シーケンスに変換します。|  
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|この関数では、特定のインターネット プロトコルまたはスキームに関連付けられている既定のポート番号を取得します。|  
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|16 進数の数値を取得します。|  
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|URL で使用しても安全な文字かどうかを判断します。|  
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|エスケープされた文字を元の値に変換します。|  
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|システム時刻を HTTP ヘッダーで使用できる形式の文字列に変換します。|  

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)|この関数は、用のオーバー ロードされたラッパー [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561)|。  
|[ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)|この関数は、用のオーバー ロードされたラッパー [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563)|。  
|[ATLPath::Append](../atl/reference/atl-path-functions.md#append)|この関数は、用のオーバー ロードされたラッパー [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565)|。  
|[ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)|この関数は、用のオーバー ロードされたラッパー [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567)|。  
|[ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)|この関数は、用のオーバー ロードされたラッパー [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569)|。  
|[ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)|この関数は、用のオーバー ロードされたラッパー [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571)|。  
|[ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)|この関数は、用のオーバー ロードされたラッパー [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574)|。  
|[ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)|この関数は、用のオーバー ロードされたラッパー [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575)|。  
|[ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)|この関数は、用のオーバー ロードされたラッパー [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578)|。  
|[ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)|この関数は、用のオーバー ロードされたラッパー [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584)|。  
|[ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)|この関数は、用のオーバー ロードされたラッパー [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587)|。  
|[ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)|この関数は、用のオーバー ロードされたラッパー [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)|。  
|[ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)|この関数は、用のオーバー ロードされたラッパー [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612)|。  
|[ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)|この関数は、用のオーバー ロードされたラッパー [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621)|。  
|[ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)|この関数は、用のオーバー ロードされたラッパー [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627)|。  
|[ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)|この関数は、用のオーバー ロードされたラッパー [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650)|。  
|[ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)|この関数は、用のオーバー ロードされたラッパー [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660)|。  
|[ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)|この関数は、用のオーバー ロードされたラッパー [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674)|。  
|[ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)|この関数は、用のオーバー ロードされたラッパー [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687)|。  
|[ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)|この関数は、用のオーバー ロードされたラッパー [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712)|。  
|[ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)|この関数は、用のオーバー ロードされたラッパー [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722)|。  
|[ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)|この関数は、用のオーバー ロードされたラッパー [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723)|。  
|[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)|この関数は、用のオーバー ロードされたラッパー [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725)|。  
|[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)|この関数は、用のオーバー ロードされたラッパー [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727)|。  
|[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)|この関数は、用のオーバー ロードされたラッパー [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739)|。  
|[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)|この関数は、用のオーバー ロードされたラッパー [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740)|。  
|[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)|この関数は、用のオーバー ロードされたラッパー [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742)|。  
|[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)|この関数は、用のオーバー ロードされたラッパー [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743)|。  
|[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)|この関数は、用のオーバー ロードされたラッパー [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745)|。  
|[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)|この関数は、用のオーバー ロードされたラッパー [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746)|。  
|[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)|この関数は、用のオーバー ロードされたラッパー [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748)|。  
|[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)|この関数は、用のオーバー ロードされたラッパー [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749)|。  
|[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)|この関数は、用のオーバー ロードされたラッパー [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754)|。  
|[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)|この関数は、用のオーバー ロードされたラッパー [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756)|。  
|[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)|この関数は、用のオーバー ロードされたラッパー [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757)|。  
|[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)|この関数は、用のオーバー ロードされたラッパー [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763)|。  
  

## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)
