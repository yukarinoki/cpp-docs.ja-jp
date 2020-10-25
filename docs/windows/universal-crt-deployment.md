---
title: ユニバーサル CRT の配置
description: アプリのユニバーサル CRT ライブラリをいつ、いつ、どこに配置するかについて説明します。
ms.date: 10/23/2020
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 50ab23f3b0276b058685e9c9ef6634caf5a96186
ms.sourcegitcommit: bf54b407169900bb668c85a67b31dbc0f069fe65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92497199"
---
# <a name="universal-crt-deployment"></a>ユニバーサル CRT の配置

Visual Studio .NET から Visual Studio 2013 では、各メジャー リリースの C++ コンパイラとツールに、新しいスタンドアロン バージョンの Microsoft C ランタイム (CRT) ライブラリが組み込まれました。 これらのスタンドアロン バージョンの CRT は互いに独立しており、程度の差はありますが、互換性はありませんでした。 たとえば、Visual Studio 2012 で使用される CRT ライブラリはバージョン 11 (名前は msvcr110.dll ) で、Visual Studio 2013 で使用される CRT はバージョン 12 (名前は msvcr120.dll) でした。 Visual Studio 2015 以降では、そうではなくなりました。 Visual Studio 2015 以降のバージョンの Visual Studio ではすべて 1 つのユニバーサル CRT を使用します。

ユニバーサル CRT (UCRT) は、Microsoft Windows オペレーティングシステムコンポーネントです。 これは、Windows 10 および Windows Server 2016 以降のオペレーティングシステムの一部として含まれています。 UCRT は、まだ拡張サポートに含まれている古いオペレーティングシステムで Windows Update を使用して利用できます。 ユニバーサル CRT のローカル配置はサポートされていますが、いくつかの制限があります。

## <a name="central-deployment"></a>集中配置

ユニバーサル CRT を集中インストールするための推奨される方法は、Microsoft Windows Update を使用することです。 ユニバーサル CRT は、サポートされるすべての Microsoft Windows オペレーティング システムに対して推奨される更新プログラムです。したがって、既定では、ほとんどのコンピューターで通常の更新プロセスの一環としてインストールされます。 ユニバーサル CRT の最初のリリースは [KB2999226](https://support.microsoft.com/kb/2999226)でした。 [KB3118401](https://support.microsoft.com/kb/3118401)で、さまざまなバグ修正が適用された後の更新プログラムが追加され、バグ修正と新機能が追加されました。 より新しい更新プログラムについては、[support.microsoft.com](https://support.microsoft.com) で Universal C ランタイムまたはユニバーサル CRT を検索してください。

すべての Microsoft Windows コンピューターで Windows Update を使用して定期的に更新プログラムがインストールされるわけではありません。一部のコンピューターでは推奨される更新プログラムがすべてインストールされない場合があります。 これらのコンピューターで Visual Studio 2015 以降の C++ ツールセットを使用してビルドされたアプリケーションの使用をサポートするために、オフライン配布に使用できるユニバーサル CRT 再頒布可能ファイルがあります。 これらの再頒布可能ファイルは、上記のいずれかの KB リンクからダウンロードできます。 ユニバーサル CRT 再頒布可能パッケージでは、コンピューターが現在の Service Pack に更新されている必要があります。 したがって、たとえば、Windows 7 用の再頒布可能パッケージは、Windows 7 RTM ではなく、Windows 7 SP1 にのみインストールされます。

ユニバーサル CRT は C++ ライブラリの基本的な依存関係であるため、Visual C++ 再頒布可能パッケージ (VCRedist) は、ユニバーサル CRT の初期バージョン (バージョン 10.0.10240) をインストールされていないコンピューターにインストールします。 このバージョンでは、C++ ライブラリの依存関係を満たすのに十分です。 アプリケーションが最新バージョンのユニバーサル CRT に依存している場合は、Windows Update を使用してコンピューターを完全に最新の状態にするか、そのバージョンを明示的にインストールする必要があります。 VCRedist をインストールする前に、Windows Update または MSU を使用してユニバーサル C ランタイムをインストールすることをお勧めします。これにより、複数の必要な再起動が必要になる可能性を回避できます。

すべてのオペレーティングシステムが、Windows Update を通じて最新のユニバーサル C ランタイムの対象になるわけではありません。 Windows 10 では、中央に配置されたバージョンがオペレーティングシステムのバージョンと一致します。 ユニバーサル C ランタイムをさらに更新するには、オペレーティングシステムを更新する必要があります。 Windows Vista から Windows 8.1 の場合、現在使用可能なユニバーサル C ランタイムは、Windows 10 の記念日更新に含まれているバージョンと、追加の修正プログラム (バージョン 10.0.14393) に基づいています。

## <a name="local-deployment"></a>ローカル デプロイ

ユニバーサル CRT のローカル配置はサポートされていますが、パフォーマンスとセキュリティの両方の理由から推奨されません。 ローカル配置用の DLL は Windows SDK の一部として、コンピューター アーキテクチャ固有の、Windows Kits\\10\\Redist\\ucrt\\DLLs のサブディレクトリに含まれています。 必要な DLL には、ucrtbase.dll、および api-ms-win-\*.dll という名前の APISet forwarder DLL のセットなどがあります。 各オペレーティングシステムに必要な一連の Dll はさまざまです。 ローカルに配置する場合は、すべての Dll を含めることを強くお勧めします。

ローカル配置の場合は、次の 2 つの制限事項に注意してください。

- Windows 10 では、アプリケーションにユニバーサル CRT のアプリケーションのローカル コピーが含まれている場合でも、システム ディレクトリのユニバーサル CRT が常に使用されます。 ユニバーサル CRT は Windows 10 のコアオペレーティングシステムコンポーネントであるため、ローカルコピーが新しい場合でも当てはまります。

- Windows 8 より前のバージョンの Windows では、ユニバーサル CRT は、メインアプリの実行可能ファイルのディレクトリ以外のディレクトリにある場合、プラグインと共にローカルにパッケージすることはできません。 この場合、APISet forwarder DLL で ucrtbase.dll を正常に解決することはできません。 推奨される代替ソリューションをいくつか以下に示します。

  - ユニバーサル CRT を静的にリンクする。
  - ユニバーサル CRT を集中配置する。
  - アプリと同じディレクトリにユニバーサル CRT ファイルを配置する。

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP での配置

Visual Studio 2015 と Visual Studio 2017 では、Microsoft Windows XP で使用されるソフトウェアの開発が引き続きサポートされます。 この開発をサポートするために、ユニバーサル CRT のバージョンは、Microsoft Windows XP で動作します。 Microsoft Windows XP オペレーティング システムはメインストリーム サポートや延長サポートの対象外となったため、Microsoft Windows XP へのユニバーサル CRT の集中配置は他のオペレーティング システムとは異なります。

Visual C++ 再頒布可能パッケージが Windows XP にインストールされると、ユニバーサル CRT とそのすべての依存関係がシステムディレクトリに直接インストールされます。 Windows Update はインストールされません。 再頒布可能マージ モジュールの Microsoft_VC*バージョン*_CRT_\*.msm でも同様です。

Windows XP でのユニバーサル CRT のローカル配置は、サポートされている他のオペレーティング システムの場合と同じです。

## <a name="see-also"></a>関連項目

- [Visual C++ での配置](deployment-in-visual-cpp.md)
