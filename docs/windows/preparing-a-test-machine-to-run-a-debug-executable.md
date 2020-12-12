---
description: '詳細情報: デバッグ実行可能ファイルを実行するためのテストコンピューターの準備'
title: デバッグ バージョンのアプリケーションを実行するテスト用コンピューターの準備
ms.date: 07/02/2019
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
ms.openlocfilehash: 28bc1d328cf1ea1d7c9738012407f3190e3a65bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180007"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>デバッグ バージョンのアプリケーションを実行するテスト用コンピューターの準備

Visual C++ でビルドしたデバッグ バージョンのアプリケーションをテストする際は、そのアプリケーションが依存している Visual C++ ライブラリ DLL のデバッグ バージョンをテスト用のコンピューターに配置する必要があります。 配置する必要がある DLL を特定するには、「[Visual C++ アプリケーションの依存関係の理解](understanding-the-dependencies-of-a-visual-cpp-application.md)」の手順に従ってください。 Visual C++ ライブラリ DLL のデバッグ バージョンには、通常、"d" で終わる名前が付いています。たとえば、msvcr100.dll のデバッグ バージョンには、msvcr100d.dll という名前が付けられています。

> [!NOTE]
> アプリケーションのデバッグ バージョンは再配布できません。また、Visual C++ ライブラリ DLL のデバッグ バージョンも再配布できません。 アプリケーションおよび Visual C++ DLL のデバッグ バージョンは、Visual Studio がインストールされていないコンピューターでアプリケーションのデバッグとテストを行う目的でのみ、他のコンピューターにインストールできます。 詳細については、「[Visual C++ ファイルの再配布](redistributing-visual-cpp-files.md)」を参照してください。

アプリケーションのデバッグ バージョンと共に Visual C++ ライブラリ DLL のデバッグ バージョンを配置する場合、次の 3 とおりの方法があります。

- アプリケーションに適したライブラリ バージョンとアーキテクチャのマージ モジュールを含むセットアップ プロジェクトを使用して %windir%\system32\ ディレクトリに特定の Visual C++ DLL のデバッグ バージョンをインストールするには、集中配置を使用します。 マージ モジュールは \Common Files\Merge Modules\\ の Program Files または Program Files (x86) ディレクトリにあります。 マージ モジュールのデバッグ バージョンには Microsoft_VC110_DebugCRT_x86.msm のような名前の Debug があります。 この配置の例は「[チュートリアル: セットアップ プロジェクトを使用した Visual C++ アプリケーションの配置](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)」でも見つけられる可能性があります。

- ローカル配置を使用して、\Microsoft Visual Studio \Vc\redist\ Debug_NonRedist の Program Files または Program Files (x86) ディレクトリにあるファイルを使用して、アプリケーションのインストールディレクトリに特定の Visual C++ DLL のデバッグバージョンをインストールし \<version> \\ ます。

    > [!NOTE]
    >  別のコンピューターで Visual Studio 2005 または Visual Studio 2008 を使用してビルドされたアプリケーションのリモートデバッグを行う場合は、Visual C++ ライブラリ Dll のデバッグバージョンを共有 side-by-side アセンブリとして配置する必要があります。 セットアップ プロジェクトまたは Windows インストーラーを使用して、対応するマージ モジュールをインストールできます。

- Visual Studio の **[構成マネージャー]** ダイアログ ボックスの **[配置]** オプションを使用して、プロジェクトの出力やその他のファイルをリモート コンピューターにコピーします。

Visual C++ DLL をインストールした後、ネットワーク共有でリモート デバッガーを実行できます。 リモート デバッグの詳細については、「[リモート デバッグ](/visualstudio/debugger/remote-debugging)」を参照してください。

## <a name="see-also"></a>関連項目

[Visual C++ での配置](deployment-in-visual-cpp.md)<br>
[Windows インストーラーのコマンド ライン オプション](/windows/win32/Msi/command-line-options)<br>
[デプロイの例](deployment-examples.md)<br>
[Remote Debugging](/visualstudio/debugger/remote-debugging)
