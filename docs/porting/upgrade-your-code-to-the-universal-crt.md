---
title: Universal CRT へのコードのアップグレード | Microsoft Docs
ms.custom: ''
ms.date: 03/31/2017
ms.topic: conceptual
ms.assetid: eaf34c1b-da98-4058-a059-a10db693a5ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1091a28448aa6531aa909117e0284e19bbcc7cd8
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "42578401"
---
# <a name="upgrade-your-code-to-the-universal-crt"></a>Universal CRT へのコードのアップグレード

Visual Studio 2015 では、Microsoft C ランタイム ライブラリ (CRT) がリファクタリングされました。 標準 C ライブラリ、POSIX の拡張機能、および Microsoft 固有の関数、マクロ、グローバル変数は、ユニバーサル C ランタイム ライブラリ (ユニバーサル CRT または UCRT) という新しいライブラリに移動されました。 CRT のコンパイラ固有のコンポーネントは、新しい vcruntime ライブラリに移動されました。  
  
UCRT は Windows コンポーネントであり、Windows 10 の一部として出荷されます。 UCRT は、C の呼び出し規約に基づく安定した ABI をサポートし、わずかな例外がありますが、ISO C99 標準に厳密に準拠しています。 コンパイラの特定のバージョンに関連付けられることはなくなりました。 UCRT は、Visual Studio 2015 または Visual Studio 2017 でサポートされている Windows の任意のバージョンで使用できます。 利点は、Visual Studio のアップグレードのたびに、CRT の新しいバージョンを対象に、ビルドを更新する必要がなくなったことです。  
  
このリファクタリングでは、多くの CRT ヘッダー ファイル、ライブラリ ファイル、および再頒布可能パッケージの名前や場所、およびコードのために必要な展開方法が変更されました。 さらに、UCRT 内の多数の関数とマクロが追加されるか、標準への準拠を向上させるために変更されました。 これらの変更を利用するには、既存のコードとプロジェクトのビルド システムを更新する必要があります。  
  
## <a name="where-to-find-the-universal-crt-files"></a>ユニバーサル CRT ファイルの場所

Windows コンポーネントと同じように、UCRT ライブラリのファイルとヘッダーは現在、Windows ソフトウェア開発キット (SDK) の一部です。 Visual Studio をインストールするときに、UCRT を使用するために必要な Windows SDK の一部もインストールされます。 Visual Studio インストーラーでは、Visual Studio のプロジェクト ビルド システムで使用される既定のパスに、UCRT ヘッダー、ライブラリ、および DLL ファイルの場所が追加されます。 Visual C++ プロジェクトを更新するときに、既定のプロジェクトの設定が使用されている場合、IDE がヘッダー ファイルの新しい場所を自動的に検出し、リンカーが新しい既定の UCRT ライブラリと vcruntime ライブラリを自動的に使用します。 同様に、Developer コマンド プロンプトを使用してコマンド ライン ビルドを実行する場合、ヘッダーとライブラリのパスを含む環境変数が更新され、こちらも自動的に動作します。  
  
標準 C ライブラリ ヘッダー ファイルが、Windows SDK に含まれるようになり、SDK バージョン固有のディレクトリのインクルード フォルダーに置かれます。 ヘッダー ファイルの標準的な場所は、Program Files または Program Files (x86) ディレクトリにある Windows Kits\\10\\Include\\_sdk-version_\\ucrt です。ここで _sdk-version_ は、Windows のバージョンまたは更新プログラムに対応します。たとえば、Windows 10 Anniversary Update の場合は 10.0.14393.0 です。   
  
UCRT スタティック ライブラリとダイナミック リンク スタブ ライブラリは、 Windows Kits\\10\\Lib\\_sdk-version_\\ucrt\\_architecture_ の下にある Program Files または Program Files (x86) ディレクトリにあります。ここで、_architecture_ は、ARM、x86、または X64 です。 製品版およびデバッグのスタティック ライブラリは、libucrt.lib と libucrtd.lib であり、UCRT DLL のライブラリは、ucrt.lib と ucrtd.lib です。  
  
製品版およびデバッグの UCRT DLL は、別々の場所にあります。 製品版 DLL は再頒布可能であり、Program Files または Program Files (x86) ディレクトリの Windows Kits\\10\\Redist\\ucrt\\DLLs\\_architecture_\. の下にあります。 デバッグ DLL は再頒布可能ではありません。プログラム ファイルまたはプログラム ファイル (x86) ディレクトリの Windows Kits\\10\\bin\\_architecture_\\ucrt フォルダーの下にあります。   

C および C++ コンパイラ固有のランタイム サポート ライブラリ **vcruntime** には、プログラムの起動、および例外処理や組み込みなどの機能をサポートするために必要なコードが含まれています。 ライブラリとそのヘッダー ファイルは、Program Files または Program files (x86) ディレクトリのバージョン固有の Microsoft Visual Studio フォルダーに引き続き置かれています。 Visual Studio 2017 では、ヘッダーは、Microsoft Visual Studio\\2017\\_edition_\\VC\\Tools\\MSVC\\_lib-version_\\include にあり、リンク ライブラリは、Microsoft Visual Studio\\2017\\_edition_\\VC\\Tools\\MSVC\\_lib-version_\\lib\\_architecture_ にあります。ここで、_edition_ はインストールされている Visual Studio のエディションであり、_lib-version_ はライブラリのバージョンで、_architecture_ はプロセッサのアーキテクチャです。 OneCore とストアのリンク ライブラリは、libraries フォルダーにもあります。 スタティック ライブラリの製品版とデバッグ バージョンは、libvcruntime.lib と libvcruntimed.lib です。 ダイナミック リンク ライブラリの製品版とデバッグのスタブ ライブラリは、それぞれ vcruntime.lib と vcruntimed.lib です。  
  
Visual C++ プロジェクトを更新するときに、プロジェクトの **[リンカー]** プロパティの **[すべての既定のライブラリの無視]** を **[はい]** に設定するか、コマンドラインで `/NODEFAULTLIB` リンカー オプションを使用する場合、ライブラリのリストを更新して、新しいリファクタリング ライブラリを組み込む必要があります。 古い CRT ライブラリ (libcmt.lib、libcmtd.lib、msvcrt.lib、msvcrtd.lib など) をリファクタリングした同等のライブラリで置き換えます。 使用する特定のライブラリの詳細については、「[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)」を参照してください。  
  
## <a name="deployment-and-redistribution-of-the-universal-crt"></a>ユニバーサル CRT の配置と再配布
  
UCRT は現在、Microsoft Windows オペレーティング システムのコンポーネントなので、Windows 10 では、オペレーティング システムの一部として含まれており、Windows Vista から Windows 8.1 までの旧バージョンのオペレーティング システムでは、Windows Update を通して入手できます。 再頒布可能パッケージのバージョンは Windows XP で使用できます。 オペレーティング システムのコンポーネントであるため、UCRT の更新プログラムとサービスは、Visual Studio および Microsoft C++ コンパイラのバージョンとは無関係に、Windows Update によって管理されます。 UCRT は、Windows コンポーネントであり、セキュリティおよび更新の容易さ、小さいイメージ サイズなどの理由から、アプリ用の UCRT を集中配置することをお勧めします。  
  
UCRT は、Visual Studio 2015 または Visual Studio 2017 でサポートされている Windows の任意のバージョンで使用できます。 Windows 10 以外のサポートされているバージョンの Windows では、vcredist パッケージを使用して再配布することができます。 vcredist パッケージは、UCRT コンポーネントを含み、既定で、それらのコンポーネントがインストールされていない Windows オペレーティング システムにそれらを自動的にインストールします。 詳細については、「[Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)」を参照してください。  
  
UCRT のアプリのローカルの展開がサポートされていますが、パフォーマンスとセキュリティの両方の理由から推奨されません。 アプリのローカル展開用の DLL は、Windows SDK の一部として **redist** サブディレクトリに置かれています。 必要な DLL には、ucrtbase.dll および api-ms-win-_subset_.dll という名前の **APISet forwarder** DLL のセットなどがあります。 必要な DLL のセットはオペレーティング システムごとに異なるので、アプリのローカルの展開を使用するときにはすべての DLL を含めることをお勧めします。 アプリのローカルの展開に関するその他の詳細および注意事項については、「[Deployment in Visual C++](../ide/deployment-in-visual-cpp.md)」 (Visual c での展開) を参照してください。  
  
## <a name="changes-to-the-universal-crt-functions-and-macros"></a>ユニバーサル CRT 関数およびマクロの変更  

UCRT では、ISO C99 への準拠を改善し、コードの品質およびセキュリティの問題を解決するために、多くの関数が追加または更新されました。 このために、ライブラリの大幅な変更が必要な場合もありました。 古いバージョンの CRT を使用したときにコードが正常にコンパイルされても、UCRT を使用すると壊れる場合は、これらの更新や機能を活用するために、コードを変更する必要があります。 ユニバーサル CRT での CRT の重大な変更と更新の詳細については、Visual C++ の変更履歴の「[C Runtime Library (CRT)](visual-cpp-change-history-2003-2015.md#BK_CRT)」 (C ランタイム ライブラリ (CRT)) セクションを参照してください。 コードに必要な変更を識別するために使用できる影響を受けるヘッダーと関数の一覧が含まれています。  
  
## <a name="see-also"></a>参照  

[Visual C++ 移植とアップグレードのガイド](visual-cpp-porting-and-upgrading-guide.md)  
[アップグレードに関する潜在的な問題 (Visual C++) の概要](overview-of-potential-upgrade-issues-visual-cpp.md)  
[旧バージョンの Visual C++ からのプロジェクトのアップグレード](upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
[Visual C++ 2003 ～ 2015 の変更履歴](visual-cpp-change-history-2003-2015.md)  
[Visual Studio 2017 の C++ 準拠の強化](../cpp-conformance-improvements-2017.md)  