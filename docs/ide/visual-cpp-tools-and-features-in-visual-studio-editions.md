---
title: Visual C ツールおよび Visual Studio のエディションで機能 |Microsoft ドキュメント
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- versions [C++]
- Visual C++, versions
- editions [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5eace3ef3cfd07847c995151554ba70ca23f820
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="visual-c-tools-and-features-in-visual-studio-editions"></a>Visual C ツールおよび Visual Studio のエディションの機能

Visual Studio で使用できる Visual C++ の機能を次の表に示します。 セル内の X は機能が使用できることを示し、空のセルは機能が使用できないことを示します。 かっこ内の説明は機能が制限付きで使用できることを示します。

## <a name="platforms"></a>プラットフォーム

||||||
|-|-|-|-|-|
|プラットフォーム|Visual Studio Express for Windows 10|Visual Studio Express for Windows Desktop|Visual Studio Community/Professional|Visual Studio Enterprise|
|Windows デスクトップ||x|X|x|
|ユニバーサル Windows プラットフォーム ((電話、タブレット、PC、Xbox、IoT、HoloLens))|x||X|x|
|Microsoft Store 8.1|||x|x|
|Windows Phone 8.0|||x|x|
|Android|||x|x|
|iOS|||x|x|

## <a name="compilers"></a>コンパイラ

|コンパイラ|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|32 ビット X86 コンパイラ|x|X|X|x|
|X86_arm cross-compiler|x||X|x|
|64 ビット [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] コンパイラ|||x|x|
|X86_ [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] cross-compiler|x|X|X|x|

## <a name="libraries-and-headers"></a>ライブラリおよびヘッダー

|ライブラリまたはヘッダー|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Windows ヘッダー、ライブラリ、CRT ライブラリ|(X)|x|X|x|
|C++ 標準ライブラリ|x|X|X|X|
|[ATL]|||X|X|
|MFC|||X|x|
|.NET Framework クラス ライブラリ||x|X|x|
|.NET 用 C++ サポート ライブラリ||x|X|x|
|OpenMP|x|X|X|x|

## <a name="project-templates"></a>プロジェクト テンプレート

|テンプレート|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|UWP、Windows 8.1、Windows Phone 8.0 向け XAML テンプレート|x||X|x|
|Direct3D アプリケーション|x||X|x|
|DLL (ユニバーサル Windows)|x||X|x|
|スタティック ライブラリ (ユニバーサル Windows)|x||X|x|
|Windows ランタイム コンポーネント|x||X|x|
|単体テスト アプリ (ユニバーサル Windows)|x||X|x|
|ATL プロジェクト|||x|x|
|クラス ライブラリ (CLR)||x|X|x|
|CLR コンソール アプリケーション||x|X|x|
|CLR 空プロジェクト||x|X|x|
|カスタム ウィザード|||x|x|
|空のプロジェクト||x|X|x|
|メイクファイル プロジェクト||x|X|x|
|MFC ActiveX コントロール|||x|x|
|MFC アプリケーション|||x|x|
|MFC DLL|||x|x|
|テスト プロジェクト|x|X|X|x|
|Win32 コンソール アプリケーション||x|X|x|
|Win32 プロジェクト||x|X|x|

## <a name="tools"></a>ツール

|ツール|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|----------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|インクリメンタル リンカー (Link.exe)|x|X|X|x|
|Program Maintenance Utility (Nmake.exe)||x|X|x|
|Lib ジェネレーター (Lib.exe)|x|X|X|x|
|Windows リソース コンパイラ (Rc.exe)|x|X|X|x|
|Windows Resource to Object Converter (CvtRes.exe)||x|X|x|
|Browse Information Maintenance Utility (BscMake.exe)|x|X|X|x|
|C++ Name Undecorator (Undname.exe)|x|X|X|x|
|COFF/PE Dumper (Dumpbin.exe)|x|X|X|x|
|COFF/PE Editor (Editbin.exe)|x|X|X|x|
|MASM (Ml.exe)|||x|x|
|Spy++|||x|x|
|ErrLook|||x|x|
|AtlTrace|||x|x|
|Devenv.com|||x|x|
|推論規則|||x|x|
|VCBuild .vcproj プロジェクトの MSBuild (VCUpgrade.exe) へのアップグレード|x|X|X|x|
|ガイド付き最適化のプロファイル|||x|x|

## <a name="debugging-features"></a>デバッグ機能

|デバッグ機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|ネイティブ デバッグ|x|X|X|x|
|natvis (ネイティブ型の視覚エフェクト)|x|X|X|x|
|グラフィックスのデバッグ|x||X|x|
|マネージ デバッグ||x|X|x|
|GPU 使用率|x||X|x|
|メモリ使用量|x||X|x|
|リモート デバッグ|x|X|X|x|
|SQL デバッグ|||x|x|
|スタティック コード分析|制限|制限|x|x|

## <a name="designers-and-editors"></a>デザイナーおよびエディター

|デザイナーまたはエディター|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|XAML デザイナー|x||X|x|
|CSS スタイル デザイナー/エディター|x|X|X|x|
|HTML デザイナー/エディター|x|X|X|x|
|XML エディター|x|X|X|x|
|ソース コード エディター|x|X|X|x|
|生産性機能: リファクタリング、IntelliSense、C++ コードの書式設定|x|X|X|x|
|Windows フォーム デザイナー||x|X|x|
|データ デザイナー|||x|x|
|ネイティブ リソース エディター (.rc ファイル)|||x|x|
|リソース エディター|x|X|X|x|
|モデル エディター|x||X|x|
|シェーダー デザイナー|x||X|x|

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
|コマンド ライン ビルド (msbuild.exe)|x|X|X|x|
|ネイティブ マルチ ターゲット||x|X|x|
|マネージ マルチ ターゲット||x|X|x|
|平行ビルド|x|X|X|x|
|カスタマイズのビルド|x|X|X|x|
|プロパティ ページの機能拡張|x|X|X|x|

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
|単体テスト (ネイティブ フレームワーク)|x|X|X|x|
|単体テスト (マネージ フレームワーク)||x|X|x|
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
