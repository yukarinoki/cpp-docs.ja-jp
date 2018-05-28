---
title: ユニバーサル CRT 展開 |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20006118d4bf27c379b78b84dc8807a4fd6c5e6c
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="universal-crt-deployment"></a>ユニバーサル CRT の配置

Visual Studio 2013 の Visual Studio .NET での C++ コンパイラおよびツールの各メジャー リリースは、Microsoft C ランタイム (CRT) ライブラリの新しいスタンドアロン バージョンを含まれます。 これらのスタンドアロン バージョンの CRT では、さまざまな段階で、相互に互換性のないしては独立していました。 たとえば、Visual Studio 2012 で使用される、CRT ライブラリがバージョン 11、名前付き msvcr110.dll、あり Visual Studio 2013 で使用される CRT バージョン 12、名前付き msvcr120.dll です。 Visual Studio 2015 以降では、これは不要になった場合です。 Visual Studio 2015 と Visual Studio のすべての以降のバージョンは、1 つのユニバーサル CRT を使用します。

ユニバーサル CRT は、Microsoft Windows オペレーティング システム コンポーネントです。 Windows 10 で、オペレーティング システムの一部として含まれてしは、Windows Update を使用して以前のオペレーティング システム、Windows 8.1 から Windows Vista 使用します。 さらに、ユニバーサル CRT のローカル配置、サポートがいくつかの制限があります。

## <a name="central-deployment"></a>集中配置

ユニバーサル CRT を一元的にインストールする推奨のメソッドは、Microsoft Windows Update を使用するがします。 ユニバーサル CRT では、既定、ほとんどのコンピューターとしてインストールし、定期的な更新プログラムのプロセスの一環ですべての推奨される更新プログラムに Microsoft Windows オペレーティング システムがサポートされています。 ユニバーサル CRT の最初のリリースが[KB2999226](https://support.microsoft.com/en-us/kb/2999226); 内でさまざまなバグの修正後の更新が行われた[KB3118401](https://support.microsoft.com/en-us/kb/3118401)、さらにバグの修正と新しい機能が追加の更新プログラムがあったとします。 新しい更新プログラムを検索して[support.microsoft.com](https://support.microsoft.com) Universal C Runtime またはユニバーサル CRT です。

すべての Microsoft Windows コンピューターが Windows Update を使用して定期的に更新プログラムをインストールし、すべての推奨される更新プログラムをインストールすることがありますしない一部です。 それらのコンピューターの Visual Studio 2015 およびそれ以降の C ツールセットを使用して構築されたアプリケーションの使用をサポートするためにはユニバーサル CRT 再頒布可能パッケージがオフラインの配布に使用できます。 それらの再頒布可能パッケージは、サポート技術情報へのリンクのいずれかからダウンロードできます。 ユニバーサル CRT の再頒布可能パッケージに、マシンが現在の service pack に更新されたことが必要なことに注意してください。 そのため、たとえば、Windows 7 の再頒布可能パッケージはのみインストールいない Windows 7 RTM、Windows 7 SP1 にします。

Visual C 再頒布可能パッケージ (VCRedist) が既にインストールされている、C++ のライブラリを満たすのに十分なバージョンがないコンピューターでユニバーサル CRT の基本バージョンをインストール、ユニバーサル CRT は C ライブラリの基本的な依存関係であるため、依存関係。 ユニバーサル CRT のより新しいバージョンに依存するアプリケーション場合、より新しいバージョンを明示的にインストールする必要があります。 再起動を回避するために必要な潜在的な複数に、VCRedist をインストールする前に、これをインストールすることをお勧めします。

## <a name="local-deployment"></a>ローカル配置

ユニバーサル CRT のローカル配置はサポートされています、パフォーマンスとセキュリティ上の理由をお勧めしません。  ローカル配置の Dll は、Windows キットで、Windows SDK の一部として含める\\10\\Redist\\ucrt\\コンピューターのアーキテクチャによって、Dll のサブディレクトリ。 Ucrtbase.dll APISet フォワーダー api という名前の Dll のセットは、Dll が必要な-ms-win-\*.dll です。 ローカルに展開するときにすべての Dll を含めることを強くお勧めように、各オペレーティング システムで必要な Dll のセットが異なります。

ローカル配置が認識する 2 つの制限があります。

- Windows 10 でユニバーサル CRT システム ディレクトリには、常に使用場合でも、アプリケーションには、ユニバーサル CRT のアプリケーションのローカル コピーが含まれています。 これは、ユニバーサル CRT のローカル コピーが新しい場合でも当てはまります。 これは、ユニバーサル CRT が Windows 10 でコア オペレーティング システムのコンポーネントであるためです。

- Windows 8 の前に Windows のバージョンは、ユニバーサル CRT ことはできませんとしてパッケージ化するローカル プラグインをアプリのメイン実行可能ファイルを含むディレクトリ以外のディレクトリに配置されています。 APISet フォワーダー Dll は、ここでは正常には ucrtbase.dll を解決することはできません。 一部の推奨される代替ソリューションは次のとおりです。

  - ユニバーサル CRT に静的にリンクします。
  - ユニバーサル CRT、一元的に展開または
  - アプリと同じディレクトリ内には、ユニバーサル CRT ファイルを配置します。

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP での展開

Visual Studio 2015 と Visual Studio 2017 は、Microsoft Windows XP で使用するソフトウェアの開発をサポートするために続行します。 これをサポートするには、ユニバーサル CRT のバージョンの Microsoft Windows XP で機能します。 Microsoft Windows XP オペレーティング システムはありません主流または拡張のサポートのため、Microsoft Windows XP にはユニバーサル CRT の一元的な展開が他のオペレーティング システムによって異なります。

Windows XP には、Visual C 再頒布可能パッケージをインストールするときに、直接ユニバーサル CRT とその依存関係のすべてにインストール システム ディレクトリをインストールせず、または任意の Windows Update によってです。 再頒布可能マージ モジュールを Microsoft_VC*バージョン*_CRT_\*同じ .msm ファイル操作を実行します。

同様に、その他のサポートされるオペレーティング システムは Windows XP でユニバーサル CRT をローカルに配置されます。

## <a name="see-also"></a>関連項目

- [Visual C++ での配置](deployment-in-visual-cpp.md)
