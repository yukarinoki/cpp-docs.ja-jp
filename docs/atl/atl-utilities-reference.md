---
title: ATL ユーティリティのリファレンス |Microsoft Docs
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
ms.openlocfilehash: 5cc56d4e0f9c31a9b37fb5044a284a229a6ed669
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758493"
---
# <a name="atl-utilities-reference"></a>ATL ユーティリティのリファレンス

ATL コードの形式でパスと Url を操作するためには、 [CPathT](../atl/reference/cpatht-class.md)と[CUrl](../atl/reference/curl-class.md)します。 スレッド プールでは、 [CThreadPool](../atl/reference/cthreadpool-class.md)アプリケーションで使用できます。 このコードは、atlpath.h および atlutil.h 記載されています。

### <a name="classes"></a>クラス

|||
|-|-|
|[CPathT クラス](../atl/reference/cpatht-class.md)|このクラスは、パスを表します。|
|[CDebugReportHook クラス](../atl/reference/cdebugreporthook-class.md)|このクラスを使用すると、名前付きパイプにデバッグ レポートを送信します。|
|[CNonStatelessWorker クラス](../atl/reference/cnonstatelessworker-class.md)|スレッド プールからの要求を受信し、要求ごとに作成および破棄される worker オブジェクトに渡されます。|
|[CNoWorkerThread クラス](../atl/reference/cnoworkerthread-class.md)|引数としてこのクラスを使用して、`MonitorClass`動的キャッシュのメンテナンスを無効にしたい場合はキャッシュ クラスをテンプレート パラメーター。|
|[CThreadPool クラス](../atl/reference/cthreadpool-class.md)|このクラスは、作業項目のキューを処理するワーカー スレッドのプールを提供します。|
|[CUrl クラス](../atl/reference/curl-class.md)|このクラスは、URL を表します。 既存の URL を解析するかどうか、他のユーザーとは無関係に、URL の各要素を操作できる文字列またはゼロからの文字列を作成します。|
|[CWorkerThread クラス](../atl/reference/cworkerthread-class.md)|このクラスは、ワーカー スレッドを作成します。 または、既存のものを使用して化し、1 つ以上のカーネル オブジェクトのハンドルを待機ハンドルがシグナル通知されたときに、指定したクライアント関数を実行します。|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[CPath](../atl/reference/atl-typedefs.md#cpath)|特殊化[CPathT](../atl/reference/cpatht-class.md)を使用して`CString`します。|
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|特殊化[CPathT](../atl/reference/cpatht-class.md)を使用して`CStringA`します。|
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|特殊化[CPathT](../atl/reference/cpatht-class.md)を使用して`CStringW`します。|
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|使用される型[CUrl](../atl/reference/curl-class.md)のポート番号を指定します。|

### <a name="enums"></a>列挙体

|||
|-|-|
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|この列挙体のメンバーで認識されるスキーマの定数を提供する[CUrl](../atl/reference/curl-class.md)します。|

### <a name="functions"></a>関数

|||
|-|-|
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|URL を標準形式に変換します。安全でない文字や空白をエスケープ シーケンスに変換する処理などが含まれます。|
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|ベース URL と相対 URL を結合して、1 つの標準形式の URL にします。|
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|すべての安全でない文字をエスケープ シーケンスに変換します。|
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|特定のインターネット プロトコルまたはスキームに関連付けられた既定のポート番号を取得するには、この関数を呼び出します。|
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|16 進数の数値を取得します。|
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|URL で使用しても安全な文字かどうかを判断します。|
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|エスケープされた文字を元の値に変換します。|
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|システム時刻を HTTP ヘッダーで使用できる形式の文字列に変換します。|  

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)|この関数はオーバー ロードされたラッパー [PathAddBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha
). | |[ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)|この関数はオーバー ロードされたラッパー [PathAddExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathaddextensiona). | |[ATLPath::Append](../atl/reference/atl-path-functions.md#append)|この関数はオーバー ロードされたラッパー [PathAppend](/windows/desktop/api/shlwapi/nf-shlwapi-pathappenda). | |[ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)|この関数はオーバー ロードされたラッパー [PathBuildRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathbuildroota). | |[ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)|この関数はオーバー ロードされたラッパー [PathCanonicalize](/windows/desktop/api/shlwapi/nf-shlwapi-pathcanonicalizea). | |[ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)|この関数はオーバー ロードされたラッパー [PathCombine](/windows/desktop/api/shlwapi/nf-shlwapi-pathcombinea). | |[ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)|この関数はオーバー ロードされたラッパー [PathCommonPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathcommonprefixa). | |[ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)|この関数はオーバー ロードされたラッパー [PathCompactPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpatha). | |[ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)|この関数はオーバー ロードされたラッパー [PathCompactPathEx](/windows/desktop/api/shlwapi/nf-shlwapi-pathcompactpathexa). | |[ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)|この関数はオーバー ロードされたラッパー [PathFileExists](/windows/desktop/api/shlwapi/nf-shlwapi-pathfileexistsa). | |[ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)|この関数はオーバー ロードされたラッパー [PathFindExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindextensiona). | |[ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)|この関数はオーバー ロードされたラッパー [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea). | |[ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)|この関数はオーバー ロードされたラッパー [PathGetDriveNumber](/windows/desktop/api/shlwapi/nf-shlwapi-pathgetdrivenumbera). | |[ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)|この関数はオーバー ロードされたラッパー [PathIsDirectory](/windows/desktop/api/shlwapi/nf-shlwapi-pathisdirectorya). | |[ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)|この関数はオーバー ロードされたラッパー [PathIsFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathisfilespeca). | |[ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)|この関数はオーバー ロードされたラッパー [PathIsPrefix](/windows/desktop/api/shlwapi/nf-shlwapi-pathisprefixa). | |[ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)|この関数はオーバー ロードされたラッパー [PathIsRelative](/windows/desktop/api/shlwapi/nf-shlwapi-pathisrelativea). | |[ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)|この関数はオーバー ロードされたラッパー [PathIsRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathisroota). | |[ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)|この関数はオーバー ロードされたラッパー [PathIsSameRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathissameroota). | |[ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)|この関数はオーバー ロードされたラッパー [PathIsUNC](/windows/desktop/api/shlwapi/nf-shlwapi-pathisunca). | |[ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)|この関数はオーバー ロードされたラッパー [PathIsUNCServer](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncservera). | |[ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)|この関数はオーバー ロードされたラッパー [PathIsUNCServerShare](/windows/desktop/api/shlwapi/nf-shlwapi-pathisuncserversharea).| |[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)|This function is an overloaded wrapper for [PathMakePretty](/windows/desktop/api/shlwapi/nf-shlwapi-pathmakeprettya).| |[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)|This function is an overloaded wrapper for [PathMatchSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathmatchspeca).| |[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)|This function is an overloaded wrapper for [PathQuoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathquotespacesa).| |[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)|This function is an overloaded wrapper for [PathRelativePathTo](/windows/desktop/api/shlwapi/nf-shlwapi-pathrelativepathtoa).| |[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)|This function is an overloaded wrapper for [PathRemoveArgs](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveargsa).| |[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)|This function is an overloaded wrapper for [PathRemoveBackslash](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovebackslasha).| |[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)|This function is an overloaded wrapper for [PathRemoveBlanks](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveblanksa).| |[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)|This function is an overloaded wrapper for [PathRemoveExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathremoveextensiona).| |[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)|This function is an overloaded wrapper for [PathRemoveFileSpec](/windows/desktop/api/shlwapi/nf-shlwapi-pathremovefilespeca).| |[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)|This function is an overloaded wrapper for [PathRenameExtension](/windows/desktop/api/shlwapi/nf-shlwapi-pathrenameextensiona).| |[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)|This function is an overloaded wrapper for [PathSkipRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathskiproota).| |[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)|This function is an overloaded wrapper for [PathStripPath](/windows/desktop/api/shlwapi/nf-shlwapi-pathstrippatha).| |[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)|This function is an overloaded wrapper for [PathStripToRoot](/windows/desktop/api/shlwapi/nf-shlwapi-pathstriptoroota).| |[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)|This function is an overloaded wrapper for [PathUnquoteSpaces](/windows/desktop/api/shlwapi/nf-shlwapi-pathunquotespacesa).|

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)   
[ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)
