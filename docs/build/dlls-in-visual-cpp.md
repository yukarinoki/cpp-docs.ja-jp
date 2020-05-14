---
title: Visual Studio で C/C++ DLL を作成する
description: Visual Studio で C++ を使用して DLL を作成および使用する理由と方法についての概要です。
ms.date: 01/27/2020
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 7083924f137fa9283da40404c7d15183e59c0b1c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422830"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Visual Studio で C/C++ DLL を作成する

Windows において、ダイナミックリンク ライブラリ (DLL) とは、関数とリソースの共有ライブラリとして機能する実行可能ファイルの一種です。 動的リンクは、オペレーティング システムの機能です。 これにより、実行可能ファイルから別のファイルに格納された関数を呼び出したり、リソースを使用したりすることができます。 これらの関数とリソースはコンパイルできるだけでなく、これらを使用する実行可能ファイルとは別に配置することができます。

DLL はスタンドアロンの実行可能ファイルではありません。 DLL は、それを呼び出すアプリケーションのコンテキストで実行されます。 オペレーティング システムによって、その DLL がアプリケーションのメモリ領域に読み込まれます。 これは、アプリケーションが読み込まれるとき ("*暗黙的なリンク*")、または必要に応じて実行時に ("*明示的なリンク*") 実行されます。 また、DLL は、実行可能ファイル間で関数とリソースを共有しやすくします。 メモリ内の DLL の内容には、同時に複数のアプリケーションがアクセスできます。

## <a name="differences-between-dynamic-linking-and-static-linking"></a>動的リンクと静的リンクの違い

静的リンクの場合、スタティック ライブラリ内のすべてのオブジェクト コードが、ビルド時にそれを使用する実行可能ファイルにコピーされます。 動的リンクには、データ項目または関数を含む DLL の検索と読み込みのために、実行時に Windows によって必要となる情報のみが含まれます。 DLL を作成するときは、この情報を含むインポート ライブラリも作成します。 DLL を呼び出す実行可能ファイルをビルドする場合、リンカーでは、インポート ライブラリにエクスポートされたシンボルを使用して、この情報を Windows ローダーに格納します。 ローダーが DLL を読み込むと、DLL はアプリケーションのメモリ領域にマップされます。 存在する場合は、DLL 内の特殊な関数 `DllMain` が呼び出され、DLL に必要なすべての初期化が実行されます。

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>アプリケーションと DLL の違い

DLL とアプリケーションはどちらも実行可能なモジュールですが、いくつかの相違点があります。 最も明白な違いは、DLL は実行できないということです。 システム側から見ると、アプリケーションと DLL には次の 2 つの根本的な違いがあります。

- アプリケーションは、システム内で実行される自分のインスタンスを複数同時に持つことができます。 DLL は 1 つしかインスタンスを持つことができません。

- アプリケーションは、プロセスとして読み込むことができます。 これはスタック、実行スレッド、グローバル メモリ、ファイル ハンドル、メッセージ キューなどを持つことができます。 DLL はそれらを持つことはできません。

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>DLL を使用する利点

コードおよびリソースへの動的リンクには、静的リンクに勝るいくつかの利点があります。

- 動的リンクではメモリが節約され、スワップが減ります。 多数のプロセスで 1 つの DLL を同時に使用し、メモリ内で DLL の読み取り専用部分の 1 つのコピーを共有できます。 これに対し、静的にリンクされたライブラリを使用してビルドされるすべてのアプリケーションには、ライブラリ コードの完全なコピーが含まれ、これを Windows がメモリに読み込む必要があります。

- 動的リンクを使用すると、ディスク領域と帯域幅が節約されます。 複数のアプリケーションが、ディスク上の DLL を共有できます。 これに対し、静的リンク ライブラリを使用してビルドされた各アプリケーションでは、その実行可能イメージにライブラリ コードがリンクされます。 これにより、より多くのディスク領域が使用され、転送により広い帯域幅が必要になります。

- メンテナンス、セキュリティの修正、アップグレードが簡単になります。 複数のアプリケーションで DLL 内の共通の関数が使用されている場合、バグ修正を実装し、DLL に対する更新プログラムを配置できます。 DLL が更新されたときに、それらを使用するアプリケーションを再コンパイルまたは再リンクする必要はありません。 新しい DLL は、配置されるとすぐに使用できるようになります。 これに対して、静的にリンクされたオブジェクト コードの修正を行う場合は、それを使用するすべてのアプリケーションを再リンクして再配置する必要があります。

- DLL を使用して、出荷後のサポートを提供できます。 たとえば、ディスプレイ ドライバー DLL を変更して、アプリケーションの出荷時には利用できなかったディスプレイをサポートすることもできます。

- 明示的なリンクを使用して、実行時に DLL を検出して読み込むことができます。 たとえば、リビルドや再配置なしでアプリに新しい機能を追加する、アプリケーション拡張機能です。

- 動的リンクを使用すると、異なるプログラミング言語で記述されたアプリケーションのサポートが容易になります。 異なるプログラミング言語で書かれたプログラムでも、関数の呼び出し規則に従う限り、同じ DLL 関数を呼び出すことができます。 プログラムと DLL 関数は、次の点で互換性がある必要があります。関数で想定される、その引数がスタック上にプッシュされる順序。 関数またはアプリケーションがスタックのクリーンアップを行うかどうか。 および、レジスタで引数が渡されるかどうか。

- 動的リンクにより、Microsoft Foundation Class ライブラリ (MFC) クラスを拡張するためのメカニズムが提供されます。 既存の MFC クラスの派生クラスを作成し、MFC アプリケーションから使用可能な MFC 拡張 DLL に配置できます。

- 動的リンクを使用すると、アプリケーションの国際対応バージョンの作成が容易になります。 DLL は、ロケール固有のリソースを提供するのに便利な方法です。これにより、アプリケーションの国際対応バージョンの作成がはるかに容易になります。 アプリケーションの多数のローカライズ バージョンを配布する代わりに、各言語用の文字列と画像を別々のリソース DLL に配置することができます。 その後、アプリケーションでは、そのロケールに対する適切なリソースを、実行時に読み込むことができます。

DLL を使用する場合の潜在的な欠点は、アプリケーションが自己完結していないことです。 それは個別の DLL モジュールの存在に依存しています。インストールの一部として、自分でこれを配置したり、検証したりする必要があります。

## <a name="more-information-on-how-to-create-and-use-dlls"></a>DLL を作成および使用する方法の詳細

次の記事では、Visual Studio で C/C++ DLL を作成する方法に関する詳細が説明されています。

[チュートリアル: ダイナミック リンク ライブラリの作成と使用 (C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)\
Visual Studio を使用して DLL を作成および使用する方法について説明します。

[DLL の種類](kinds-of-dlls.md)\
ビルドできる各種 DLL に関する情報を提供します。

[DLL に関してよく寄せられる質問](dll-frequently-asked-questions.md)\
DLL に関してよく寄せられる質問への回答を示します。

[実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md)\
DLL との明示的なリンクと暗黙的なリンクについて説明します。

[DLL の初期化](run-time-library-behavior.md#initializing-a-dll)\
DLL の読み込み時に実行する必要がある DLL 初期化コードについて説明します。

[DLL と Visual C++ ランタイム ライブラリの動作](run-time-library-behavior.md)\
ランタイム ライブラリの DLL 起動シーケンスについて説明します。

[LoadLibrary と AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)\
`LoadLibrary` と `AfxLoadLibrary` を使用して、実行時に DLL と明示的にリンクする方法について説明します。

[GetProcAddress](getprocaddress.md)\
`GetProcAddress` を使用して DLL のエクスポート関数のアドレスを取得する方法について説明します。

[FreeLibrary と AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)\
DLL モジュールが不要になったときの `FreeLibrary` と `AfxFreeLibrary` の使用方法について説明します。

[ダイナミック リンク ライブラリの検索順序](/windows/win32/Dlls/dynamic-link-library-search-order)\
Windows オペレーティング システムがシステム上の DLL を検索するために使用する検索パスについて説明します。

[MFC と動的にリンクされる標準 MFC DLL のモジュール状態](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)\
MFC と動的にリンクされる標準 MFC DLL のモジュール状態について説明します。

[MFC 拡張 DLL](extension-dlls-overview.md)\
通常は既存の MFC クラスから派生した再利用可能なクラスを実装する DLL について説明します。

[リソースのみの DLL の作成](creating-a-resource-only-dll.md)\
アイコン、ビットマップ、文字列、ダイアログ ボックスなどのリソースだけを含む、リソースのみの DLL について説明します。

[MFC アプリケーションのローカライズされたリソース:サテライト DLL](localized-resources-in-mfc-applications-satellite-dlls.md)\
混合言語にローカライズされるアプリケーションの作成に役立つ、サテライト DLL のサポートを強化します。

[インポートとエクスポート](importing-and-exporting.md)\
アプリケーションへのパブリック シンボルのインポート、または DLL からの関数のエクスポートについて説明します。

[Active テクノロジと DLL](active-technology-and-dlls.md)\
オブジェクト サーバーを DLL 内部に実装できます。

[DLL でのオートメーション](automation-in-a-dll.md)\
MFC DLL ウィザードの [オートメーション] オプションについて説明します。

[MFC DLL の名前付け規則](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)\
MFC に含まれる DLL やライブラリに適用される一定の名前付け規則について説明します。

[Visual Basic アプリケーションから DLL 関数を呼び出す](calling-dll-functions-from-visual-basic-applications.md)\
Visual Basic アプリケーションから DLL 関数を呼び出す方法について説明します。

## <a name="related-sections"></a>関連項目

[DLL の構成要素としての MFC](../mfc/tn011-using-mfc-as-part-of-a-dll.md)\
MFC ライブラリを Windows ダイナミック リンク ライブラリの一部として使用できる標準 MFC DLL について説明します。

[MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)\
MFC アプリケーションおよび MFC 拡張 DLL での MFCxx.dll および MFCxxD.dll (x は MFC のバージョン番号) 共有ダイナミック リンク ライブラリを使用する方法について説明します。
