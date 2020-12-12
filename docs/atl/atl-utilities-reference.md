---
description: 詳細については、「ATL ユーティリティリファレンス」を参照してください。
title: ATL ユーティリティのリファレンス
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: 8545881c5cd48aaff1bb25448ba443829128dc41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148578"
---
# <a name="atl-utilities-reference"></a>ATL ユーティリティのリファレンス

ATL には、 [Cpatht](../atl/reference/cpatht-class.md) および [CUrl](../atl/reference/curl-class.md)の形式でパスと url を操作するためのコードが用意されています。 スレッドプール [CThreadPool](../atl/reference/cthreadpool-class.md)は、アプリケーションで使用できます。 このコードは、atlpath.h および atlutil.h に含まれます。

## <a name="classes"></a>クラス

| &nbsp; | &nbsp; |
|--|--|
| [CPathT クラス](../atl/reference/cpatht-class.md) | このクラスは、パスを表します。 |
| [CDebugReportHook クラス](../atl/reference/cdebugreporthook-class.md) | このクラスを使用して、デバッグレポートを名前付きパイプに送信します。 |
| [CNonStatelessWorker クラス](../atl/reference/cnonstatelessworker-class.md) | は、スレッドプールから要求を受信し、各要求で作成および破棄されたワーカーオブジェクトにそれらを渡します。 |
| [CNoWorkerThread クラス](../atl/reference/cnoworkerthread-class.md) | 動的キャッシュのメンテナンスを無効にする場合は、このクラスをテンプレートパラメーターの引数として `MonitorClass` キャッシュクラスに使用します。 |
| [CThreadPool クラス](../atl/reference/cthreadpool-class.md) | このクラスは、作業項目のキューを処理するワーカースレッドのプールを提供します。 |
| [CUrl クラス](../atl/reference/curl-class.md) | このクラスは、URL を表します。 これにより、既存の URL 文字列を解析するか、文字列をゼロから構築するかどうかに関係なく、URL の各要素を他のユーザーとは独立して操作できます。 |
| [CWorkerThread クラス](../atl/reference/cworkerthread-class.md) | このクラスは、ワーカースレッドを作成するか、既存のスレッドを使用して1つ以上のカーネルオブジェクトハンドルで待機し、いずれかのハンドルがシグナル状態になったときに、指定されたクライアント関数を実行します。 |

## <a name="typedefs"></a>Typedefs

| &emsp; | &emsp; |
|--|--|
| [CPath](../atl/reference/atl-typedefs.md#cpath) | を使用した [Cpatht](../atl/reference/cpatht-class.md) の特殊化 `CString` 。 |
| [CPathA](../atl/reference/atl-typedefs.md#cpatha) | を使用した [Cpatht](../atl/reference/cpatht-class.md) の特殊化 `CStringA` 。 |
| [CPathW](../atl/reference/atl-typedefs.md#cpathw) | を使用した [Cpatht](../atl/reference/cpatht-class.md) の特殊化 `CStringW` 。 |
| [ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port) | ポート番号を指定するために [CUrl](../atl/reference/curl-class.md) によって使用される型。 |

## <a name="enums"></a>列挙型

| &emsp; | &emsp; |
|--|--|
| [ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md) | この列挙体のメンバーは、 [CUrl](../atl/reference/curl-class.md)によって認識されるスキームの定数を提供します。 |

## <a name="functions"></a>関数

| &emsp; | &emsp; |
|--|--|
| [AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl) | URL を標準形式に変換します。安全でない文字や空白をエスケープ シーケンスに変換する処理などが含まれます。 |
| [AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl) | ベース URL と相対 URL を結合して、1 つの標準形式の URL にします。 |
| [AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl) | すべての安全でない文字をエスケープ シーケンスに変換します。 |
| [AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport) | この関数を呼び出して、特定のインターネットプロトコルまたはスキームに関連付けられている既定のポート番号を取得します。 |
| [AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue) | 16 進数の数値を取得します。 |
| [AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar) | URL で使用しても安全な文字かどうかを判断します。 |
| [AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl) | エスケープされた文字を元の値に変換します。 |
| [SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate) | システム時刻を HTTP ヘッダーで使用できる形式の文字列に変換します。 |
| [ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash) | この関数は、[PathAddBackslash ラッシュ] (/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha) 用のオーバーロードされたラッパーです。 |
| ). |
| [ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension) | [Pathaddextension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)用のオーバーロードされたラッパーです。 |
| [ATLPath::Append](../atl/reference/atl-path-functions.md#append) | [Pathappend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)用のオーバーロードされたラッパーです。 |
| [ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot) | この関数は、 [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)のオーバーロードされたラッパーです。 |
| [ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize) | [Pathcanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)用のオーバーロードされたラッパーです。 |
| [ATLPath::Combine](../atl/reference/atl-path-functions.md#combine) | [Pathcombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)用のオーバーロードされたラッパーです。 |
| [ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix) | この関数は、 [Pathcommonprefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)用のオーバーロードされたラッパーです。 |
| [ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath) | この関数は、 [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)のオーバーロードされたラッパーです。 |
| [ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex) | この関数は、 [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)のオーバーロードされたラッパーです。 |
| [ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists) | [Pathfileexists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)用のオーバーロードされたラッパーです。 |
| [ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension) | この関数は、 [Pathfindextension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)用のオーバーロードされたラッパーです。 |
| [ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename) | [Pathfindfilename](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)用のオーバーロードされたラッパーです。 |
| [ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber) | この関数は、 [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)のオーバーロードされたラッパーです。 |
| [ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory) | [Pathisdirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)用のオーバーロードされたラッパーです。 |
| [ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec) | [Pathisfilespec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)用のオーバーロードされたラッパーです。 |
| [ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix) | この関数は、 [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)のオーバーロードされたラッパーです。 |
| [ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative) | [Pathisrelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)用のオーバーロードされたラッパーです。 |
| [ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot) | この関数は、 [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)のオーバーロードされたラッパーです。 |
| [ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot) | [Pathissameroot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)用のオーバーロードされたラッパーです。 |
| [ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc) | [Pathisunc](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)用のオーバーロードされたラッパーです。 |
| [ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver) | この関数は、 [Pathis出ないサーバー](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)用のオーバーロードされたラッパーです。 |
| [ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare) | [Pathisの Servershare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)用のオーバーロードされたラッパーです。 |
| [ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty) | この関数は、 [Pathmakepretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)用のオーバーロードされたラッパーです。 |
| [ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec) | [Pathmatchspec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)用のオーバーロードされたラッパーです。 |
| [ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces) | この関数は、 [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)のオーバーロードされたラッパーです。 |
| [ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto) | この関数は、 [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)のオーバーロードされたラッパーです。 |
| [ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs) | [Pathremoveargs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)用のオーバーロードされたラッパーです。 |
| [ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash) | [Pathremovebackslash ラッシュ](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)用のオーバーロードされたラッパーです。 |
| [ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks) | [Pathremoveblanks](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)用のオーバーロードされたラッパーです。 |
| [ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension) | [Pathremoveextension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)用のオーバーロードされたラッパーです。 |
| [ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec) | [Pathremovefilespec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)用のオーバーロードされたラッパーです。 |
| [ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension) | [Pathrenameextension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)用のオーバーロードされたラッパーです。 |
| [ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot) | この関数は、 [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)のオーバーロードされたラッパーです。 |
| [ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath) | [Pathの Ppath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)用のオーバーロードされたラッパーです。 |
| [ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot) | [Pathtoroot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)用のオーバーロードされたラッパーです。 |
| [ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces) | この関数は、 [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)のオーバーロードされたラッパーです。 |

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM デスクトップコンポーネント](../atl/atl-com-desktop-components.md)
