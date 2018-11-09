---
title: ユニバーサル CRT の配置
ms.date: 05/11/2018
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 90f859eb0e9134c997e7eecad118cfb8ec00b782
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657692"
---
# <a name="universal-crt-deployment"></a>ユニバーサル CRT の配置

Visual Studio .NET から Visual Studio 2013 では、各メジャー リリースの C++ コンパイラとツールに、新しいスタンドアロン バージョンの Microsoft C ランタイム (CRT) ライブラリが組み込まれました。 これらのスタンドアロン バージョンの CRT は互いに独立しており、程度の差はありますが、互換性はありませんでした。 たとえば、Visual Studio 2012 で使用される CRT ライブラリはバージョン 11 (名前は msvcr110.dll ) で、Visual Studio 2013 で使用される CRT はバージョン 12 (名前は msvcr120.dll) でした。 これは、Visual Studio 2015 以降には当てはまりません。 Visual Studio 2015 以降のバージョンの Visual Studio ではすべて 1 つのユニバーサル CRT を使用します。

ユニバーサル CRT は、Microsoft Windows オペレーティング システム コンポーネントです。 Windows 10 では、オペレーティング システムの一部として含まれており、Windows Vista から Windows 8.1 までの旧バージョンのオペレーティング システムでは、Windows Update を使用して入手できます。 さらに、ユニバーサル CRT のローカル配置がいくつかの制限付きでサポートされます。

## <a name="central-deployment"></a>集中配置

ユニバーサル CRT を集中インストールするための推奨される方法は、Microsoft Windows Update を使用することです。 ユニバーサル CRT は、サポートされるすべての Microsoft Windows オペレーティング システムに対して推奨される更新プログラムです。したがって、既定では、ほとんどのコンピューターで通常の更新プロセスの一環としてインストールされます。 ユニバーサル CRT の初期リリースは [KB2999226](https://support.microsoft.com/kb/2999226) です。後続の更新プログラム [KB3118401](https://support.microsoft.com/kb/3118401) ではさまざまなバグが修正され、追加の更新プログラムではさらにバグが修正され、新機能が提供されました。 より新しい更新プログラムについては、[support.microsoft.com](https://support.microsoft.com) で Universal C ランタイムまたはユニバーサル CRT を検索してください。

すべての Microsoft Windows コンピューターで Windows Update を使用して定期的に更新プログラムがインストールされるわけではありません。一部のコンピューターでは推奨される更新プログラムがすべてインストールされない場合があります。 そのようなコンピューターで Visual Studio 2015 以降の C++ ツールセットを使ってビルドされたアプリケーションの使用をサポートするために、オフライン配布用のユニバーサル CRT 再頒布可能パッケージを利用できます。 これらの再頒布可能パッケージは、上記の KB リンクのいずれかからダウンロードできます。 ユニバーサル CRT の再頒布可能パッケージを利用するには、コンピューターが現在のサービス パックに更新されている必要があることに注意してください。 したがって、たとえば、Windows 7 用の再頒布可能パッケージは、Windows 7 RTM ではなく、Windows 7 SP1 にのみインストールされます。

ユニバーサル CRT は C++ ライブラリの基本的な依存関係であるため、Visual C++ の再頒布可能パッケージ (VCRedist) では、C++ ライブラリの依存関係を満たすのに十分なバージョンがまだインストールされていないコンピューター上に基本バージョンのユニバーサル CRT がインストールされます。 ご利用のアプリケーションがユニバーサル CRT のより新しいバージョンに依存している場合、そのより新しいバージョンを明示的にインストールする必要があります。 何度も再起動しなくて済むように、VCRedist の前にこれをインストールすることをお勧めします。

## <a name="local-deployment"></a>ローカル配置

ユニバーサル CRT のローカル配置はサポートされていますが、パフォーマンスとセキュリティの両方の理由から推奨されません。  ローカル配置用の DLL は Windows SDK の一部として、コンピューター アーキテクチャ固有の、Windows Kits\\10\\Redist\\ucrt\\DLLs のサブディレクトリに含まれています。 必要な DLL には、ucrtbase.dll、および api-ms-win-\*.dll という名前の APISet forwarder DLL のセットなどがあります。 必要な DLL のセットはオペレーティング システムごとに異なるため、ローカルに配置するときにすべての DLL を含めることを強くお勧めします。

ローカル配置の場合は、次の 2 つの制限事項に注意してください。

- Windows 10 では、アプリケーションにユニバーサル CRT のアプリケーションのローカル コピーが含まれている場合でも、システム ディレクトリのユニバーサル CRT が常に使用されます。 これは、ユニバーサル CRT のローカル コピーの方が新しい場合でも当てはまります。 これは、ユニバーサル CRT が Windows 10 上のコア オペレーティング システム コンポーネントであるためです。

- Windows 8 より前のバージョンの Windows では、アプリのメイン実行可能ファイルを含むディレクトリ以外のディレクトリに配置されるプラグインと共にローカルでユニバーサル CRT をパッケージ化することはできません。 この場合、APISet forwarder DLL で ucrtbase.dll を正常に解決することはできません。 推奨される代替ソリューションをいくつか以下に示します。

  - ユニバーサル CRT を静的にリンクする。
  - ユニバーサル CRT を集中配置する。
  - アプリと同じディレクトリにユニバーサル CRT ファイルを配置する。

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP での配置

Visual Studio 2015 と Visual Studio 2017 では、Microsoft Windows XP で使用されるソフトウェアの開発が引き続きサポートされます。 このサポートのために、Microsoft Windows XP ではあるバージョンのユニバーサル CRT が機能します。 Microsoft Windows XP オペレーティング システムはメインストリーム サポートや延長サポートの対象外となったため、Microsoft Windows XP へのユニバーサル CRT の集中配置は他のオペレーティング システムとは異なります。

Visual C++ の再頒布可能パッケージを Windows XP にインストールすると、Windows Update をインストールすることなく、また Windows Update に依存することなく、システム ディレクトリにユニバーサル CRT とそのすべての依存関係が直接インストールされます。 再頒布可能マージ モジュールの Microsoft_VC*バージョン*_CRT_\*.msm でも同様です。

Windows XP でのユニバーサル CRT のローカル配置は、サポートされている他のオペレーティング システムの場合と同じです。

## <a name="see-also"></a>関連項目

- [Visual C++ での配置](deployment-in-visual-cpp.md)
