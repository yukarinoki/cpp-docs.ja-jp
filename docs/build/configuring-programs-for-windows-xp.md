---
title: Windows XP 用プログラムの構成
description: Visual Studio でC++ Windows XP ツールセットをインストールして使用する方法について説明します。
ms.date: 03/16/2020
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 92364d7fd25ac617baacc125b279fb0ee9c92f62
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440478"
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP 用プログラムの構成

Visual Studio では、複数のプラットフォームツールセットがサポートされています。 つまり、既定のツールセットでサポートされていないオペレーティングシステムとランタイムライブラリを対象にすることができます。 たとえば、プラットフォームツールセットを切り替えることにより、Visual Studio 2017 C++コンパイラを使用して、windows XP と windows Server 2003 を対象とするアプリを作成できます。 また、以前のプラットフォーム ツールセットを使用して、バイナリ互換性のあるレガシ コードを保守しながら、Visual Studio IDE の最新の機能も利用できます。

::: moniker range="vs-2019"

Visual Studio 2019 で提供される v142 ツールセットには、Windows XP 用のコードを作成するためのサポートは含まれていません。 Visual Studio 2017 v141_xp ツールセットを使用した Windows XP 開発のサポートは、Visual Studio インストーラーで個別のコンポーネントオプションとして使用できます。

::: moniker-end

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP プラットフォーム ツールセットのインストール

::: moniker range="<=vs-2017"

Windows XP と Windows Server 2003 を対象とする Visual Studio 2017 プラットフォームのツールセットとコンポーネントを入手するには、Visual Studio インストーラーを実行します。 最初に Visual Studio をインストールするとき、または既存のインストールを変更するときに、[ワークロード**を含むC++デスクトップ開発**] が選択されていることを確認します。 このワークロードのオプション コンポーネントの一覧で、 **[C++ に関する Windows XP サポート]** を選択し、 **[インストール]** または **[変更]** を選択します。

::: moniker-end

::: moniker range="vs-2019"

Windows XP と Windows Server 2003 を対象とする v141_xp プラットフォームのツールセットとコンポーネントを入手するには、Visual Studio インストーラーを実行します。 最初に Visual Studio をインストールするとき、または既存のインストールを変更するときに、[ワークロード**を含むC++デスクトップ開発**] が選択されていることを確認します。 **[個々のコンポーネント]** タブの **コンパイラ]、[ビルドツール]** 、[ランタイム] の下で、[  **C++ Windows XP Support for VS 2017 (v141) tools \[非推奨])** を選択し、 **[インストール]** または **[変更]** を選択します。

::: moniker-end

## <a name="windows-xp-targeting-experience"></a>Windows XP 対応のエクスペリエンス

Visual Studio に含まれている Windows XP プラットフォームツールセットは、Windows 7 SDK のバージョンですが、Visual Studio 2017 C++コンパイラを使用します。 また、これは、プロジェクトのプロパティを適切な既定値に構成します。たとえば、下位レベルへの対応用の、互換性のあるリンカーの仕様などです。 Windows xp プラットフォームツールセットを使用して作成された Windows デスクトップアプリのみが、Windows XP および Windows Server 2003 で実行できます。 これらのアプリは、より新しい Windows オペレーティングシステムでも実行できます。

### <a name="to-target-windows-xp"></a>Windows XP に対応するには

1. **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** を選択します。

1. プロジェクトの **[プロパティページ]** ダイアログボックスで、 **[構成プロパティ]**  >  **[全般]** を選択します。 **プラットフォームツール**セットのプロパティを、優先する Windows XP ツールセットに設定します。 たとえば、Visual Studio 2017 の Microsoft C++ コンパイラを使用し、Windows XP および Windows Server 2003 向けのコードを作成するには、 **[Visual Studio 2017 - Windows XP (v141_xp)]** を選択します。

### <a name="c-runtime-support"></a>C++ ランタイムのサポート

Windows XP プラットフォームツールセットと共に、いくつかのライブラリには、Windows XP および Windows Server 2003 のランタイムサポートが含まれています。 これらのライブラリは、C ランタイムライブラリ (CRT)、 C++標準ライブラリ、ACTIVE TEMPLATE LIBRARY (ATL)、同時実行ランタイムライブラリ (concrt)、並列パターンライブラリ (PPL)、MICROSOFT FOUNDATION CLASS ライブラリ (MFC)、 C++ AMP (C++高速大規模プログラミング) ライブラリです。 これらのオペレーティングシステムでサポートされている最小バージョンは、x86 用の Windows XP Service Pack 3 (SP3)、x64 用の windows xp Service pack 2 (SP2)、および x86 と x64 の両方の Windows Server 2003 Service pack 2 (SP2) です。

これらのライブラリは Visual Studio によってインストールされているプラットフォーム ツールセットによりサポートされますが、サポート状況はターゲットに応じて異なります。

|ライブラリ|Windows デスクトップ アプリを対象とする既定のプラットフォーム ツールセット|Store アプリを対象とする既定のプラットフォーム ツールセット|Windows XP と Windows Server 2003 を対象とする Windows XP プラットフォーム ツールセット|
|---|---|---|---|
|CRT|X|X|X|
|C++ 標準ライブラリ|X|X|X|
|[ATL]|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> C++/CLI で作成され、.NET Framework 4 を対象とするアプリは、Windows XP と Windows Server 2003 で動作します。

### <a name="differences-between-the-toolsets"></a>ツールセットの間の相違点

プラットフォームとライブラリのサポートの違いにより、Windows XP プラットフォームツールセットを使用するアプリの開発環境は、既定の Visual Studio プラットフォームツールセットを使用するアプリの場合と同様に完了していません。

- **C++ 言語の機能**

   v110\_xp のプラットフォーム ツールセットを使用するアプリでサポートされているのは、Visual Studio 2012 に実装されている C++ 言語機能だけです。 v120\_xp のプラットフォーム ツールセットを使用するアプリでサポートされているのは、Visual Studio 2013 に実装されている C++ 言語機能だけです。 v140\_xp のプラットフォーム ツールセットを使用するアプリでサポートされているのは、Visual Studio 2015 に実装されている C++ 言語機能だけです。 V141 C++\_xp プラットフォームツールセットを使用するアプリでは、Visual Studio 2017 で実装されている言語機能のみがサポートされます。 Visual Studio は、以前のプラットフォーム ツールセットを使用してビルドするときに、対応するコンパイラを使用します。 そのバージョンのコンパイラに実装されている C++ 言語の追加機能を利用するには、より新しい Windows XP のプラットフォーム ツールセットを使用します。

- **リモート デバッグ**

   Remote Tools for Visual Studio は、Windows XP または Windows Server 2003 のリモート デバッグに対応していません。 Windows XP または Windows Server 2003 でローカルまたはリモートでアプリをデバッグするには、古いバージョンの Visual Studio のデバッガーを使用します。 これは、プラットフォームツールセットのランタイムターゲットである Windows Vista でのアプリのデバッグに似ていますが、リモートデバッグターゲットはありません。

- **静的分析**

   Windows XP のプラットフォーム ツールセットは、Windows 7 SDK の SAL 注釈とランタイム ライブラリに互換性がないため、静的分析をサポートしていません。 Windows XP または Windows Server 2003 をサポートするアプリでは、静的な分析を実行できます。 分析の既定のプラットフォームツールセットを対象とするようにソリューションを一時的に切り替えてから、Windows XP プラットフォームツールセットに戻り、アプリをビルドします。

- **DirectX グラフィックスのデバッグ**

   グラフィックスデバッガーは Direct3D 9 API をサポートしていないため、Windows XP または Windows Server 2003 で Direct3D を使用するアプリのデバッグには使用できません。 ただし、アプリが Direct3D 10 または Direct3D 11 Api に基づく別のレンダラーを実装している場合は、グラフィックスデバッガーを使用して問題を診断できます。

- **HLSL の構築**

   既定では、Windows XP ツールセットは HLSL ソースコードファイルをコンパイルしません。 HLSL ファイルをコンパイルするには、June 2010 DirectX SDK をダウンロードしてインストールし、プロジェクトの VC ディレクトリに含めるように設定します。 詳細については、[June 2010 DirectX SDK ダウンロード ページ](https://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)の「DirectX SDK はインクルード/ライブラリ パスを Visual Studio 2010 に登録しない」セクションを参照してください。
