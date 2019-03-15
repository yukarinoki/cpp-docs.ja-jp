---
title: さまざまな Visual Studio エディションの Visual C++ ツールおよび機能
ms.date: 02/28/2018
helpviewer_keywords:
- versions [C++]
- Visual C++, versions
- editions [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
ms.openlocfilehash: 3d3c6e25594eb3bb01ad3fc995a24cdc723d5726
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751896"
---
# <a name="visual-c-tools-and-features-in-visual-studio-editions"></a>さまざまな Visual Studio エディションの Visual C++ ツールおよび機能

Visual Studio で使用できる Visual C++ の機能を次の表に示します。 セル内の X は機能が使用できることを示し、空のセルは機能が使用できないことを示します。 かっこ内の説明は機能が制限付きで使用できることを示します。

## <a name="platforms"></a>プラットフォーム

||||||
|-|-|-|-|-|
|プラットフォーム|Visual Studio Express for Windows 10|Visual Studio Express for Windows Desktop|Visual Studio Community/Professional|Visual Studio Enterprise|
|Windows デスクトップ||x|x|x|
|ユニバーサル Windows プラットフォーム ((電話、タブレット、PC、Xbox、IoT、HoloLens))|x||x|x|
|Microsoft ストア 8.1|||x|x|
|Windows Phone 8.0|||x|x|
|Android|||x|x|
|iOS|||x|x|

## <a name="compilers"></a>コンパイラ

|コンパイラ|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|32 ビット X86 コンパイラ|x|x|x|x|
|X86_arm cross-compiler|x||x|x|
|64 ビット x64 コンパイラ|||x|x|
|X86_ x64 クロス コンパイラ|x|x|x|x|

## <a name="libraries-and-headers"></a>ライブラリおよびヘッダー

|ライブラリまたはヘッダー|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Windows ヘッダー、ライブラリ、CRT ライブラリ|(X)|x|x|x|
|C++ 標準ライブラリ|x|x|x|x|
|ATL|||x|x|
|MFC|||x|x|
|.NET Framework クラス ライブラリ||x|x|x|
|.NET 用 C++ サポート ライブラリ||x|x|x|
|OpenMP|x|x|x|x|

## <a name="project-templates"></a>プロジェクト テンプレート

|テンプレート|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|UWP、Windows 8.1、Windows Phone 8.0 向け XAML テンプレート|x||x|x|
|Direct3D アプリケーション|x||x|x|
|DLL (ユニバーサル Windows)|x||x|x|
|スタティック ライブラリ (ユニバーサル Windows)|x||x|x|
|Windows ランタイム コンポーネント|x||x|x|
|単体テスト アプリ (ユニバーサル Windows)|x||x|x|
|ATL プロジェクト|||x|x|
|クラス ライブラリ (CLR)||x|x|x|
|CLR コンソール アプリケーション||x|x|x|
|CLR 空プロジェクト||x|x|x|
|カスタム ウィザード|||x|x|
|空のプロジェクト||x|x|x|
|メイクファイル プロジェクト||x|x|x|
|MFC ActiveX コントロール|||x|x|
|MFC アプリケーション|||x|x|
|MFC DLL|||x|x|
|テスト プロジェクト|x|x|x|x|
|Win32 コンソール アプリケーション||x|x|x|
|Win32 プロジェクト||x|x|x|

## <a name="tools"></a>ツール

|ツール|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|----------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|インクリメンタル リンカー (Link.exe)|x|x|x|x|
|Program Maintenance Utility (Nmake.exe)||x|x|x|
|Lib ジェネレーター (Lib.exe)|x|x|x|x|
|Windows リソース コンパイラ (Rc.exe)|x|x|x|x|
|Windows Resource to Object Converter (CvtRes.exe)||x|x|x|
|Browse Information Maintenance Utility (BscMake.exe)|x|x|x|x|
|C++ Name Undecorator (Undname.exe)|x|x|x|x|
|COFF/PE Dumper (Dumpbin.exe)|x|x|x|x|
|COFF/PE Editor (Editbin.exe)|x|x|x|x|
|MASM (Ml.exe)|||x|x|
|Spy++|||x|x|
|ErrLook|||x|x|
|AtlTrace|||x|x|
|Devenv.com|||x|x|
|推論規則|||x|x|
|VCBuild .vcproj プロジェクトの MSBuild (VCUpgrade.exe) へのアップグレード|x|x|x|x|
|ガイド付き最適化のプロファイル|||x|x|

## <a name="debugging-features"></a>デバッグ機能

|デバッグ機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|ネイティブ デバッグ|x|x|x|x|
|natvis (ネイティブ型の視覚エフェクト)|x|x|x|x|
|グラフィックスのデバッグ|x||x|x|
|マネージド デバッグ||x|x|x|
|GPU 使用率|x||x|x|
|メモリ使用量|x||x|x|
|Remote Debugging|x|x|x|x|
|SQL デバッグ|||x|x|
|スタティック コード分析|制限|制限|x|x|

## <a name="designers-and-editors"></a>デザイナーおよびエディター

|デザイナーまたはエディター|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|XAML デザイナー|x||x|x|
|CSS スタイル デザイナー/エディター|x|x|x|x|
|HTML デザイナー/エディター|x|x|x|x|
|XML エディター|x|x|x|x|
|ソース コード エディター|x|x|x|x|
|生産性機能: リファクタリング、IntelliSense、C++ コードの書式設定|x|x|x|x|
|Windows フォーム デザイナー||x|x|x|
|データ デザイナー|||x|x|
|ネイティブ リソース エディター (.rc ファイル)|||x|x|
|リソース エディター|x|x|x|x|
|モデル エディター|x||x|x|
|シェーダー デザイナー|x||x|x|

## <a name="data-features"></a>データ機能

|データ機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|データ デザイナー|||x|x|
|データ オブジェクト|||x|x|
|Web サービス|||x|x|
|サーバー エクスプローラー|||x|x|

## <a name="build-and-project-systems"></a>ビルド システムとプロジェクト システム

|ビルドまたはプロジェクトの機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|コマンド ライン ビルド (msbuild.exe)|x|x|x|x|
|ネイティブ マルチ ターゲット||x|x|x|
|マネージド マルチ ターゲット||x|x|x|
|平行ビルド|x|x|x|x|
|カスタマイズのビルド|x|x|x|x|
|プロパティ ページの機能拡張|x|x|x|x|

## <a name="automation-and-extensibility"></a>オートメーションおよび機能拡張

|オートメーションおよび機能拡張|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|----------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|機能拡張オブジェクト モデル|||x|x|
|コード モデル|||x|x|
|プロジェクト モデル|||x|x|
|リソース エディター モデル|||x|x|
|ウィザード モデル|||x|x|
|デバッガー オブジェクト モデル|||x|x|

## <a name="application-lifecycle-management-tools"></a>アプリケーション ライフサイクル管理ツール

||||||
|-|-|-|-|-|
|ツール|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|単体テスト (ネイティブ フレームワーク)|x|x|x|x|
|単体テスト (マネージド フレームワーク)||x|x|x|
|コード カバレッジ||||x|
|手動テスト||||x|
|探索的テスト||||x|
|テスト ケース管理||||x|
|コード マップと依存関係グラフ|||読み取り専用|x|
|コード マップ デバッグ||||x|

## <a name="see-also"></a>関連項目

[Visual Studio のインストール](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio の新機能](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Visual C++ プロジェクトの種類](../ide/visual-cpp-project-types.md)<br/>
[SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686)<br/>
