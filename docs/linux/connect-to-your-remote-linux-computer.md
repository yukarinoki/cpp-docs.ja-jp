---
title: Visual Studio でターゲットの Linux システムに接続する
description: Visual Studio の C++ プロジェクト内からリモートの Linux マシンまたは WSL に接続する方法です。
ms.date: 06/19/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: 00d7facca2857efb0b8b43b5aaf38edce348a511
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861144"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Visual Studio でターゲットの Linux システムに接続する

::: moniker range="vs-2015"

Linux サポートは Visual Studio 2017 以降で使用できます。

::: moniker-end

::: moniker range=">=vs-2017"

リモート マシンまたは Windows Subsystem for Linux (WSL) をターゲットにするように、Linux プロジェクトを構成できます。 リモート マシンおよび Visual Studio 2017 上の WSL の場合は、接続を設定する必要があります。 

## <a name="connect-to-a-remote-linux-computer"></a>リモートの Linux コンピューターに接続する

リモートの Linux システム (VM または物理マシン) 用に C++ の Linux プロジェクトをビルドする場合、Linux コードはリモートの Linux コンピューターにコピーされ、Visual Studio の設定に基づいてコンパイルされます。

このリモート接続をセットアップするには、次のようにします。

1. 最初にプロジェクトをビルドするか、新しいエントリを手動で作成します。その場合、 **[ツール]、[オプション]** の順に選択し、 **[クロス プラットフォーム]、[接続マネージャー]** ノードの順に開き、 **[追加]** ボタンをクリックします。

   ![接続マネージャー](media/settings_connectionmanager.png)

   いずれの場合も、 **[Connect to Remote System]** (リモート システムへの接続) ウィンドウが表示されます。

   ![リモート システムへの接続](media/connect.png)

1. 次の情報を入力します。

   | 入力 | 説明
   | ----- | ---
   | **ホスト名**           | ターゲット デバイスの名前または IP アドレス
   | **ポート**                | SSH サービスが実行されているポート (通常は 22)
   | **ユーザー名**           | 認証するユーザー
   | **認証の種類** | パスワードと秘密キーの両方がサポートされます。
   | **パスワード**            | 入力したユーザー名のパスワード
   | **秘密キー ファイル**    | ssh 接続用に作成された秘密キー ファイル
   | **パスフレーズ**          | 上で選択した秘密キーで使用されるパスフレーズ

   認証には、パスワードまたはキー ファイルとパスフレーズを使用することができます。 多くの開発シナリオでは、パスワード認証で十分です。 公開/秘密キー ファイルを使う方がよい場合は、新しいものを作成するか、[既存のものを再利用する](https://security.stackexchange.com/questions/10203/reusing-private-public-keys)ことができます。 現在は、RSA および DSA キーのみがサポートされています。 
   
   秘密 RSA キー ファイルを作成するには、次の手順のようにします。

    1. Windows コンピューターで、`ssh-keygen -t rsa` を使って ssh キー ペアを作成します。 これにより、公開キーと秘密キーが作成されます。 既定では、キーは `id_rsa.pub` および `id_rsa` という名前で `C:\Users\%USERNAME%\.ssh` に配置されます。

    1. Windows から Linux マシンに公開キーをコピーします: `scp -p C:\Users\%USERNAME%\.ssh\id_rsa.pub user@hostname`。

    1. Linux システムで、承認済みキーのリストにキーを追加します (および、ファイルに適切なアクセス許可があることを確認します): `cat ~/id_rsa.pub >> ~/.ssh/authorized_keys; chmod 600 ~/.ssh/authorized_keys`

1. **[接続]** ボタンをクリックすると、リモート コンピューターへの接続が試行されます。 

   接続が成功すると、Visual Studio ではリモートのヘッダーを使うように IntelliSense の構成が開始されます。 詳しくは、「[リモート システムのヘッダーでの IntelliSense](configure-a-linux-project.md#remote_intellisense)」をご覧ください。

   接続に失敗した場合は、変更する必要がある入力ボックスが赤色で示されます。

   ![接続マネージャーのエラー](media/settings_connectionmanagererror.png)

   キー ファイルを認証に使う場合は、ターゲット マシンの SSH サーバーが実行され、正しく構成されていることを確認します。

   ::: moniker-end

   ::: moniker range="vs-2019"

   **[ツール] > [オプション] > [クロス プラットフォーム] > [ログ]** に移動し、接続に関する問題のトラブルシューティングに役立つログ記録を有効にします。

   ![リモート ログ記録](media/remote-logging-vs2019.png)

   ログには、接続、リモート マシンに送信されたすべてのコマンド (そのテキスト、終了コード、実行時間)、および Visual Studio からシェルへのすべての出力が含まれます。 ログ記録は、Visual Studio でのすべてのクロスプラットフォーム CMake プロジェクトまたは MSBuild ベースの Linux プロジェクトで機能します。

   ファイルまたは出力ウィンドウの **[クロス プラットフォームのログ]** ウィンドウに送られるように、出力を構成できます。 MSBuild ベースの Linux プロジェクトの場合、MSBuild によってリモート マシンに発行されたコマンドは、プロセス外で出力されるため、 **[出力ウィンドウ]** にはルーティングされません。 代わりに、"msbuild_" というプレフィックスが付いたファイルに記録されます。

   ::: moniker-end

## <a name="connect-to-wsl"></a>WSL に接続する

::: moniker range="vs-2017"

Visual Studio 2017 では、この記事で前に説明したリモート Linux マシンへの接続と同じ手順を使って、WSL に接続します。 **ホスト名**には **localhost** を使います。

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 バージョン 16.1 では、WSL をターゲットにするときに、リモート接続を追加したり、SSH を構成したりする必要はありません。 Linux システムで必要なものは、gcc、gdb、make、rsync、zip だけです。 Visual Studio では、IntelliSense でヘッダー ファイルを初めて使うときに、WSL インスタンスから Windows ファイル システムに抽出するためだけに、rsync と zip が必要です。 Visual Studio 2019 バージョン 16.1 では、WSL のサポートは Windows バージョン 1809 に基づきます。 それより後のバージョンの Windows を実行できますが、Visual Studio では新しい WSL の機能はまだ利用されません。

お使いのディストリビューションで apt がサポートされている場合、このコマンドで必要なパッケージをインストールできます。

```bash
sudo apt install g++ gdb make rsync zip
```

WSL 用にプロジェクトを構成するには、プロジェクトの種類に応じて、「[Linux プロジェクトを構成する](configure-a-linux-project.md)」または「[Linux CMake プロジェクトを構成する](cmake-linux-project.md)」をご覧ください。

::: moniker-end

## <a name="see-also"></a>関連項目

[Linux プロジェクトを構成する](configure-a-linux-project.md)<br />
[Linux CMake プロジェクトを構成する](cmake-linux-project.md)<br />
[Linux プロジェクトの配置、実行、デバッグ](deploy-run-and-debug-your-linux-project.md)<br />




