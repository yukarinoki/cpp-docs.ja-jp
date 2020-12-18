---
description: '詳細情報: さまざまな Visual Studio エディションの C++ ツールと機能'
title: さまざまな Visual Studio エディションの C++ ツールと機能
ms.date: 05/21/2019
helpviewer_keywords:
- tools and platforms [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
ms.openlocfilehash: 6253e52fa300cc60de4b2700b384fde6f5ffe1ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254626"
---
# <a name="c-tools-and-features-in-visual-studio-editions"></a>さまざまな Visual Studio エディションの C++ ツールおよび機能

::: moniker range=">=msvc-160"

次の C++ 機能を Visual Studio 2019 で使用できます。 特に示されていない限り、すべての機能をすべてのエディションで使用できます。Visual Studio Community、Visual Studio Professional、Visual Studio Enterprise。 一部の機能には、特定のワークロードまたはオプション コンポーネントが必要です。これは、Visual Studio インストーラーを使ってインストールできます。

## <a name="platforms"></a>プラットフォーム

- Windows デスクトップ
- ユニバーサル Windows プラットフォーム ((タブレット、PC、Xbox、IoT、HoloLens))
- Linux
- Android
- iOS

## <a name="compilers"></a>コンパイラ

- x86、x64、ARM、ARM64 用の MSVC 32 ビット コンパイラ
- x86、x64、ARM、ARM64 用の MSVC 64 ビット コンパイラ
- ARM 用の GCC クロス コンパイラ
- Clang/LLVM
  - Windows 上の x86 または x64 を対象とする Clang/LLVM 7.0 (CMake サポートのみ)。 その他の Clang バージョンは機能しますが、公式にはサポートされません。
  - Linux 上で配布によってサポートされる任意の Clang/LLVM インストール。

## <a name="c-workloads"></a>C++ ワークロード

Visual Studio には C++ 開発に対して次のワークロードが含まれます。 .NET デスクトップ開発、Python 開発、Azure の開発、Visual Studio 拡張機能の開発など、その他のワークロードと共に、これらの一部またはすべてをインストールできます。

### <a name="desktop-development-with-c"></a>C++ によるデスクトップ開発

対象: 

- C++ コア デスクトップ機能

オプション コンポーネント: 

- MSVC v142 - VS 2019 C++ x64/x86 ビルド ツール (v14.21)
- Windows 10 SDK (10.0.17763.0)
- Just-In-Time デバッガー
- C++ のプロファイル ツール
- Windows 用 C++ CMake ツール
- v142 ビルド ツールの C++ ATL (x86 & x64)
- Test Adapter for Boost.Test
- Test Adapter for Google Test
- Live Share
- IntelliCode
- IntelliTrace (Enterprise のみ)
- v142 ビルド ツールの C++ MFC (x86 & x64)
- v142 ビルド ツールの C++/CLI サポート (14.21)
- v142 ビルド ツール用の C++ モジュール (x64/x86 – 実験)
- Windows 用 Clang コンパイラ
- IncrediBuild - ビルド アクセラレーション
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- MSVC v141 - VS 2017 C++ x64/x86 ビルド ツール (v14.16)
- MSVC v140 - VS 2015 C++ ビルド ツール (v14.00)

### <a name="linux-development-with-c"></a>C++ による Linux 開発

対象: 

- C++ コア機能
- Windows ユニバーサル C ランタイム
- Linux 開発用 C++

オプション コンポーネント: 

- Linux 用の C++ CMake ツール
- 埋め込み開発ツールと IoT 開発ツール

### <a name="universal-windows-platform-development"></a>ユニバーサル Windows プラットフォームの開発

対象: 

- Blend for Visual Studio
- .NET ネイティブと .NET Standard
- NuGet パッケージ マネージャー
- ユニバーサル Windows プラットフォーム ツール
- Windows 10 SDK (10.0.17763.0)

オプション コンポーネント: 

- IntelliCode
- IntelliTrace (Enterprise のみ)
- USB デバイスの接続
- C++ (v142) ユニバーサル Windows プラットフォーム ツール
- C++ (v141) ユニバーサル Windows プラットフォーム ツール
- DirectX 用グラフィックス デバッガーおよび GPU プロファイラー
- Windows 10 SDK (10.0.18362.0)
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- アーキテクチャおよび分析ツール

### <a name="c-game-development"></a>C++ ゲーム開発

対象: 

- C++ コア機能
- Windows ユニバーサル C ランタイム
- C++ 2019 再頒布可能パッケージの更新プログラム
- MSVC v142 - VS 2019 C++ x64/x86 ビルド ツール (v14.21)

オプション コンポーネント: 

- C++ のプロファイル ツール
- Windows 10 SDK (10.0.17763.0)
- IntelliCode
- IntelliTrace (Enterprise のみ)
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- IncrediBuild - ビルド アクセラレーション
- Cocos
- Unreal Engine のインストーラー
- Unreal Engine 用の Android IDE サポート

### <a name="mobile-development-with-c"></a>C++ でのモバイル開発

対象: 

- C++ コア機能
- Android SDK セットアップ (API レベル 25) (C++ を使用したモバイル開発のためにローカルにインストール)

オプション コンポーネント: 

- Android NDK (R16B)
- Apache Ant (1.9.3)
- C++ Android 開発ツール
- IntelliCode
- Google Android Emulator (API レベル 25) (ローカル インストール)
- Intel Hardware Accelerated Execution Manager (HAXM) (ローカル インストール)
- Android NDK (R16B) (32 ビット)
- C++ iOS 開発ツール
- IncrediBuild - ビルド アクセラレーション

## <a name="individual-components"></a>個々のコンポーネント

任意のワークロードからこれらのコンポーネントを個別にインストールできます。

- JavaScript 診断
- Live Share
- v142 ビルド ツールの C++ ユニバーサル Windows プラットフォーム ランタイム
- ClickOnce Publishing
- Microsoft Visual Studio インストーラー プロジェクト

## <a name="libraries-and-headers"></a>ライブラリとヘッダー

- Windows ヘッダーおよびライブラリ
- Windows ユニバーサル C ランタイム (CRT)
- C++ 標準ライブラリ
- ATL
- MFC
- .NET Framework クラス ライブラリ
- .NET 用 C++ サポート ライブラリ
- OpenMP 2.0
- vcpkg カタログ経由の 900 個を超えるオープンソース ライブラリ

## <a name="build-and-project-systems"></a>ビルド システムとプロジェクト システム

- CMake
- [フォルダーを開く] による任意のビルド システム
- コマンド ライン ビルド (msbuild.exe)
- ネイティブ マルチ ターゲット
- マネージド マルチ ターゲット
- 平行ビルド
- カスタマイズのビルド
- プロパティ ページの機能拡張

## <a name="project-templates"></a>プロジェクト テンプレート

次のプロジェクト テンプレートは、インストールしたワークロードによって利用できるものが異なります。

Windows デスクトップ:

- 空のプロジェクト
- コンソール アプリ
- Windows デスクトップ ウィザード
- Windows デスクトップ アプリケーション
- 共有アイテム プロジェクト
- MFC アプリ
- ダイナミック リンク ライブラリ
- CLR 空プロジェクト
- CLR コンソール アプリ
- スタティック ライブラリ
- CMake プロジェクト
- ATL プロジェクト
- MFC ダイナミック リンク ライブラリ
- CLR クラス ライブラリ
- メイクファイル プロジェクト (Windows)
- MFC ActiveXControl
- ネイティブ単体テスト プロジェクト
- Google Test

ユニバーサル Windows プラットフォーム (C++/CX): 

- 空のアプリ
- DirectX 11 および XAML アプリ
- DirectX 11 アプリ
- DirectX 12 アプリ
- 単体テスト アプリ
- [DLL]
- Windows ランタイム コンポーネント
- スタティック ライブラリ
- Windows アプリケーション パッケージ プロジェクト

Linux:

- コンソール アプリ (Linux)
- 空のプロジェクト (Linux)
- Raspberry Pi Blink
- メイクファイル プロジェクト (Linux)

## <a name="tools"></a>ツール

- インクリメンタル リンカー (Link.exe)
- Microsoft メイクファイル ユーティリティ (Nmake.exe)
- Lib ジェネレーター (Lib.exe)
- Windows リソース コンパイラ (Rc.exe)
- Windows Resource to Object Converter (CvtRes.exe)
- Browse Information Maintenance Utility (BscMake.exe)
- C++ Name Undecorator (Undname.exe)
- COFF/PE Dumper (Dumpbin.exe)
- COFF/PE Editor (Editbin.exe)
- MASM (Ml.exe)
- Spy++
- ErrLook
- AtlTrace
- 推論規則
- ガイド付き最適化のプロファイル

## <a name="debugging-features"></a>デバッグ機能

- ネイティブ デバッグ
- natvis (ネイティブ型の視覚エフェクト)
- グラフィックスのデバッグ
- マネージド デバッグ
- GPU 使用率
- メモリ使用量
- リモート デバッグ
- SQL デバッグ
- スタティック コード分析

## <a name="designers-and-editors"></a>デザイナーおよびエディター

- XAML デザイナー
- CSS スタイル デザイナー/エディター
- HTML デザイナー/エディター
- XML エディター
- ソース コード エディター
- 生産性機能: リファクタリング、EDG IntelliSense エンジン、C++ コードの書式設定
- Windows フォーム デザイナー
- データ デザイナー
- ネイティブ リソース エディター (.rc ファイル)
- リソース エディター
- モデル エディター
- シェーダー デザイナー
- ライブ依存関係検証 (Enterprise のみ)
- アーキテクチャ レイヤー図 (Enterprise のみ)
- アーキテクチャの検証 (Enterprise のみ)
- コード クローン (Enterprise のみ)

## <a name="data-features"></a>データ機能

- データ デザイナー
- データ オブジェクト
- Web サービス
- [サーバー エクスプローラー]

## <a name="automation-and-extensibility"></a>オートメーションおよび機能拡張

- 機能拡張オブジェクト モデル
- コード モデル
- プロジェクト モデル
- リソース エディター モデル
- ウィザード モデル
- デバッガー オブジェクト モデル

## <a name="application-lifecycle-management-tools"></a>アプリケーション ライフサイクル管理ツール

- 単体テスト (Microsoft Native C++、Boost.Test、Google Test、CTest)
- コード マップと依存関係グラフ (Professional と Enterprise)
- コード カバレッジ (Enterprise のみ)
- 手動テスト (Enterprise のみ)
- 探索的テスト (Enterprise のみ)
- テスト ケースの管理 (Enterprise のみ)
- コード マップ デバッガーの統合 (Enterprise のみ)
- Live Unit Testing (Enterprise のみ)
- IntelliTrace (Enterprise のみ)
- IntelliTest (Enterprise のみ)
- Microsoft Fakes (単体テストの分離) (Enterprise のみ)
- コード カバレッジ (Enterprise のみ)

## <a name="see-also"></a>関連項目

[Visual Studio のインストール](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio の新機能](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Visual Studio の C++ プロジェクトの種類](../build/reference/visual-cpp-project-types.md)

::: moniker-end

::: moniker range="<=msvc-150"

Visual Studio 2017 で使用できる Visual C++ の機能を次の表に示します。 セル内の X は機能が使用できることを示し、空のセルは機能が使用できないことを示します。 かっこ内の説明は機能が制限付きで使用できることを示します。

## <a name="platforms"></a>プラットフォーム

|プラットフォーム|Visual Studio Express for Windows 10|Visual Studio Express for Windows Desktop|Visual Studio Community/Professional|Visual Studio Enterprise|
|-|-|-|-|-|
|Windows デスクトップ||x|x|X|
|ユニバーサル Windows プラットフォーム ((電話、タブレット、PC、Xbox、IoT、HoloLens))|x||x|X|
|Linux|x|X|
|Microsoft ストア 8.1|||x|X|
|Windows Phone 8.0|||x|X|
|Android|||x|X|
|iOS|||x|X|

## <a name="compilers"></a>コンパイラ

|コンパイラ|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|MSVC 32 ビット X86 コンパイラ|x|x|x|X|
|X86_arm cross-compiler|x||x|X|
|MSVC 64 ビット x64 コンパイラ|||x|X|
|X86_ x64 クロス コンパイラ|x|x|x|X|

## <a name="libraries-and-headers"></a>ライブラリとヘッダー

|ライブラリまたはヘッダー|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Windows ヘッダー、ライブラリ、CRT ライブラリ|(X)|x|x|x|
|C++ 標準ライブラリ|x|x|x|x|
|ATL|||x|x|
|MFC|||x|X|
|.NET Framework クラス ライブラリ||x|x|X|
|.NET 用 C++ サポート ライブラリ||x|x|X|
|OpenMP 2.0|x|x|x|X|

## <a name="project-templates"></a>プロジェクト テンプレート

|テンプレート|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|UWP、Windows 8.1、Windows Phone 8.0 向け XAML テンプレート|x||x|X|
|Direct3D アプリケーション|x||x|X|
|DLL (ユニバーサル Windows)|x||x|X|
|スタティック ライブラリ (ユニバーサル Windows)|x||x|X|
|Windows ランタイム コンポーネント|x||x|X|
|単体テスト アプリ (ユニバーサル Windows)|x||x|X|
|ATL プロジェクト|||x|X|
|クラス ライブラリ (CLR)||x|x|X|
|CLR コンソール アプリケーション||x|x|X|
|CLR 空プロジェクト||x|x|X|
|カスタム ウィザード|||x|X|
|空のプロジェクト||x|x|X|
|メイクファイル プロジェクト||x|x|X|
|MFC ActiveX コントロール|||x|X|
|MFC アプリケーション|||x|X|
|MFC DLL|||x|X|
|テスト プロジェクト|x|x|x|X|
|Win32 コンソール アプリケーション||x|x|X|
|Win32 プロジェクト||x|x|X|

## <a name="tools"></a>ツール

|ツール|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|----------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|インクリメンタル リンカー (Link.exe)|x|x|x|X|
|Program Maintenance Utility (Nmake.exe)||x|x|X|
|Lib ジェネレーター (Lib.exe)|x|x|x|X|
|Windows リソース コンパイラ (Rc.exe)|x|x|x|X|
|Windows Resource to Object Converter (CvtRes.exe)||x|x|X|
|Browse Information Maintenance Utility (BscMake.exe)|x|x|x|X|
|C++ Name Undecorator (Undname.exe)|x|x|x|X|
|COFF/PE Dumper (Dumpbin.exe)|x|x|x|X|
|COFF/PE Editor (Editbin.exe)|x|x|x|X|
|MASM (Ml.exe)|||x|X|
|Spy++|||x|X|
|ErrLook|||x|X|
|AtlTrace|||x|X|
|Devenv.com|||x|X|
|推論規則|||x|X|
|VCBuild .vcproj プロジェクトの MSBuild (VCUpgrade.exe) へのアップグレード|x|x|x|X|
|ガイド付き最適化のプロファイル|||x|X|

## <a name="debugging-features"></a>デバッグ機能

|デバッグ機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|ネイティブ デバッグ|x|x|x|X|
|natvis (ネイティブ型の視覚エフェクト)|x|x|x|X|
|グラフィックスのデバッグ|x||x|X|
|マネージド デバッグ||x|x|X|
|GPU 使用率|x||x|X|
|メモリ使用量|x||x|X|
|リモート デバッグ|x|x|x|X|
|SQL デバッグ|||x|X|
|スタティック コード分析|制限|制限あり|x|X|

## <a name="designers-and-editors"></a>デザイナーおよびエディター

|デザイナーまたはエディター|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|XAML デザイナー|x||x|X|
|CSS スタイル デザイナー/エディター|x|x|x|X|
|HTML デザイナー/エディター|x|x|x|X|
|XML エディター|x|x|x|X|
|ソース コード エディター|x|x|x|X|
|生産性機能: リファクタリング、IntelliSense、C++ コードの書式設定|x|x|x|X|
|Windows フォーム デザイナー||x|x|X|
|データ デザイナー|||x|X|
|ネイティブ リソース エディター (.rc ファイル)|||x|X|
|リソース エディター|x|x|x|X|
|モデル エディター|x||x|X|
|シェーダー デザイナー|x||x|X|

## <a name="data-features"></a>データ機能

|データ機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|データ デザイナー|||x|X|
|データ オブジェクト|||x|X|
|Web サービス|||x|X|
|[サーバー エクスプローラー]|||x|X|

## <a name="build-and-project-systems"></a>ビルド システムとプロジェクト システム

|ビルドまたはプロジェクトの機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|コマンド ライン ビルド (msbuild.exe)|x|x|x|X|
|ネイティブ マルチ ターゲット||x|x|X|
|マネージド マルチ ターゲット||x|x|X|
|平行ビルド|x|x|x|X|
|カスタマイズのビルド|x|x|x|X|
|プロパティ ページの機能拡張|x|x|x|X|

## <a name="automation-and-extensibility"></a>オートメーションおよび機能拡張

|オートメーションおよび機能拡張|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|----------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|機能拡張オブジェクト モデル|||x|X|
|コード モデル|||x|X|
|プロジェクト モデル|||x|X|
|リソース エディター モデル|||x|X|
|ウィザード モデル|||x|X|
|デバッガー オブジェクト モデル|||x|X|

## <a name="application-lifecycle-management-tools"></a>アプリケーション ライフサイクル管理ツール

|ツール|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|
|-|-|-|-|-|
|単体テスト (ネイティブ フレームワーク)|x|x|x|X|
|単体テスト (マネージド フレームワーク)||x|x|X|
|コード カバレッジ||||X|
|手動テスト||||X|
|探索的テスト||||X|
|テスト ケース管理||||X|
|コード マップと依存関係グラフ|||読み取り専用|X|
|コード マップ デバッグ||||X|

## <a name="see-also"></a>関連項目

[Visual Studio のインストール](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio の新機能](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Visual Studio の C++ プロジェクトの種類](../build/reference/visual-cpp-project-types.md)

::: moniker-end
