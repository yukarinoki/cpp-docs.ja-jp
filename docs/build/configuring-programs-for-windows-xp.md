---
title: Windows XP 用プログラムの構成
description: Visual Studio で C++ Windows XP ツールセットをインストールして使用する方法について説明します。
ms.date: 03/16/2020
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 09fe1a511c92f999e02646b9e606a3631a175215
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919372"
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP 用プログラムの構成

Visual Studio では、複数のプラットフォーム ツールセットがサポートされています。 つまり、既定のツールセットによってサポートされていないオペレーティング システムとランタイム ライブラリをターゲットにすることができます。 たとえば、プラットフォーム ツールセットを切り替えることで、Visual Studio 2017 C++ コンパイラを使用して、ターゲットが Windows XP と Windows Server 2003 であるアプリを作成できます。 また、以前のプラットフォーム ツールセットを使用して、バイナリ互換性のあるレガシ コードを保守しながら、Visual Studio IDE の最新の機能も利用できます。

::: moniker range="msvc-160"

Visual Studio 2019 で提供される v142 ツールセットには、Windows XP 用のコード作成のサポートは含まれていません。 Visual Studio 2017 の v141_xp ツールセットを使用した Windows XP の開発のサポートは、Visual Studio インストーラーの独立したコンポーネント オプションとして入手できます。

::: moniker-end

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP プラットフォーム ツールセットのインストール

::: moniker range="<=msvc-150"

ターゲットが Windows XP と Windows Server 2003 である Visual Studio 2017 プラットフォーム ツールセットとコンポーネントを取得するには、Visual Studio インストーラーを実行します。 Visual Studio を初めてインストールするとき、または既存のインストールを変更するとき、 **[C++ によるデスクトップ開発]** ワークロードを必ず選択します。 このワークロードのオプション コンポーネントの一覧で、 **[C++ に関する Windows XP サポート]** を選択し、 **[インストール]** または **[変更]** を選択します。

::: moniker-end

::: moniker range="msvc-160"

ターゲットが Windows XP と Windows Server 2003 である v141_xp プラットフォーム ツールセットとコンポーネントを取得するには、Visual Studio インストーラーを実行します。 Visual Studio を初めてインストールするとき、または既存のインストールを変更するとき、 **[C++ によるデスクトップ開発]** ワークロードを必ず選択します。 **[個々のコンポーネント]** タブの **[コンパイラ、ビルド ツール、およびランタイム]** で、 **VS 2017 (v141) ツールの C++ Windows XP サポート \[非推奨]** を選択し、 **[インストール]** または **[変更]** を選択します。

::: moniker-end

## <a name="windows-xp-targeting-experience"></a>Windows XP 対応のエクスペリエンス

Visual Studio に含まれている Windows XP プラットフォーム ツールセットは Windows 7 SDK のバージョンの 1 つですが、Visual Studio 2017 C++ コンパイラが使用されます。 また、これは、プロジェクトのプロパティを適切な既定値に構成します。たとえば、下位レベルへの対応用の、互換性のあるリンカーの仕様などです。 Windows XP と Windows Server 2003 では、Windows XP プラットフォーム ツールセットを使用して作成された Windows デスクトップ アプリだけを実行できます。 これらのアプリは、より新しい Windows オペレーティング システムでも実行できます。

### <a name="to-target-windows-xp"></a>Windows XP に対応するには

1. **ソリューション エクスプローラー** で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** を選択します。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスで、 **[構成プロパティ]**  >  **[全般]** を選択します。 **[プラットフォーム ツールセット]** プロパティを、優先する Windows XP ツールセットに設定します。 たとえば、Visual Studio 2017 の Microsoft C++ コンパイラを使用し、Windows XP および Windows Server 2003 向けのコードを作成するには、 **[Visual Studio 2017 - Windows XP (v141_xp)]** を選択します。

### <a name="c-runtime-support"></a>C++ ランタイムのサポート

Windows XP プラットフォーム ツールセットと共に、いくつかのライブラリには、Windows XP と Windows Server 2003 のランタイムサポートが含まれています。 これらのライブラリは、C ランタイム ライブラリ (CRT)、C++ 標準ライブラリ、Active Template Library (ATL)、同時実行ランタイム ライブラリ (ConCRT)、並列パターン ライブラリ (PPL)、Microsoft Foundation Class ライブラリ (MFC)、および C++ AMP (C++ Accelerated Massive Programming) ライブラリです。 これらのオペレーティング システムでサポートされる最小バージョンは次のとおりです。x86 用 Windows XP Service Pack 3 (SP3)、x64 用 Windows XP Service Pack 2 (SP2)、および x86 と x64 用 Windows Server 2003 Service Pack 2 (SP2) です。

これらのライブラリは Visual Studio によってインストールされているプラットフォーム ツールセットによりサポートされますが、サポート状況はターゲットに応じて異なります。

|ライブラリ|Windows デスクトップ アプリを対象とする既定のプラットフォーム ツールセット|Store アプリを対象とする既定のプラットフォーム ツールセット|Windows XP と Windows Server 2003 を対象とする Windows XP プラットフォーム ツールセット|
|---|---|---|---|
|CRT|x|x|x|
|C++ 標準ライブラリ|x|x|x|
|ATL|x|x|x|
|ConCRT/PPL|x|x|x|
|MFC|x||x|
|C++ AMP|x|x||

> [!NOTE]
> C++/CLI で作成され、.NET Framework 4 を対象とするアプリは、Windows XP と Windows Server 2003 で動作します。

### <a name="differences-between-the-toolsets"></a>ツールセットの間の相違点

プラットフォームとライブラリのサポートの違いにより、Windows XP のプラットフォーム ツールセットを使用するアプリの開発のエクスペリエンスは、既定の Visual Studio プラットフォーム ツールセットを使用するアプリの場合ほど完全ではありません。

- **C++ 言語の機能**

   v110\_xp のプラットフォーム ツールセットを使用するアプリでサポートされているのは、Visual Studio 2012 に実装されている C++ 言語機能だけです。 v120\_xp のプラットフォーム ツールセットを使用するアプリでサポートされているのは、Visual Studio 2013 に実装されている C++ 言語機能だけです。 v140\_xp のプラットフォーム ツールセットを使用するアプリでサポートされているのは、Visual Studio 2015 に実装されている C++ 言語機能だけです。 v141\_xp プラットフォーム ツールセットを使用するアプリでサポートされているのは、Visual Studio 2017 に実装されている C++ 言語機能だけです。 Visual Studio は、以前のプラットフォーム ツールセットを使用してビルドするときに、対応するコンパイラを使用します。 そのバージョンのコンパイラに実装されている C++ 言語の追加機能を利用するには、より新しい Windows XP のプラットフォーム ツールセットを使用します。

- **リモート デバッグ**

   Remote Tools for Visual Studio は、Windows XP または Windows Server 2003 のリモート デバッグに対応していません。 Windows XP または Windows Server 2003 でアプリをローカルにまたはリモートでデバッグするには、古いバージョンの Visual Studio のデバッガーを使用します。 これは Windows Vista でのアプリのデバッグと似ていますが、プラットフォーム ツールセットのランタイム ターゲットであり、リモートのデバッグ ターゲットではありません。

- **静的分析**

   Windows XP のプラットフォーム ツールセットは、Windows 7 SDK の SAL 注釈とランタイム ライブラリに互換性がないため、静的分析をサポートしていません。 Windows XP または Windows Server 2003 をサポートするアプリのスタティック分析は実行できます。 分析用の既定のプラットフォーム ツールセットをターゲットにするようにソリューションを一時的に切り替えた後、アプリをビルドする Windows XP のプラットフォーム ツールセットに切り替え直します。

- **DirectX グラフィックスのデバッグ**

   グラフィックス デバッガーでは Direct3D 9 API はサポートされないため、Windows XP または Windows Server 2003 で Direct3D を使用するアプリのデバッグにこれを利用することはできません。 ただし、Direct3D 10 API または Direct3D 11 API に基づく代替レンダラーがアプリで実装される場合は、グラフィックス デバッガーを使用して問題を診断できます。

- **HLSL の構築**

   Windows XP ツールセットでは、既定では HLSL ソース コード ファイルはコンパイルされません。 HLSL ファイルをコンパイルするには、June 2010 DirectX SDK をダウンロードしてインストールし、プロジェクトの VC ディレクトリに含めるように設定します。 詳細については、[June 2010 DirectX SDK ダウンロード ページ](https://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)の「DirectX SDK はインクルード/ライブラリ パスを Visual Studio 2010 に登録しない」セクションを参照してください。
