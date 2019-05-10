---
title: Windows XP 用プログラムの構成
ms.date: 02/02/2018
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: f27921e062fd8abb7bc9b63bfbb9b050f25ee54b
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446365"
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP 用プログラムの構成

Visual Studio では、複数のプラットフォーム ツールセットをサポートするために、オペレーティング システムと、既定のツールセットでサポートされていないランタイム ライブラリを対象ことができます。 たとえば、プラットフォーム ツールセットを切り替えることで c++ 11、c++ 14、および c++ 17 の言語拡張機能が Visual Studio での MSVC コンパイラでサポートされているが Windows XP および Windows Server 2003 を対象とするアプリを作成するのにに使用します。 バイナリ互換性のあるレガシ コードを維持するためにも以前のプラットフォーム ツールセットを使用し、Visual Studio IDE の最新の機能も利用できます。

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP プラットフォーム ツールセットをインストールします。

Visual Studio 2017 で、プラットフォームのツールセットとターゲットの Windows XP および Windows Server 2003 にコンポーネントを取得するには、Visual Studio インストーラーを実行します。 最初に Visual Studio をインストールするとき、または選択した**変更**、既存のインストールを変更することを確認します、 **C++ によるデスクトップ開発**ワークロードを選択します。 このワークロードのオプションのコンポーネントの一覧で選択**C++ に関する Windows XP サポート**を選び、**インストール**または**変更**します。

## <a name="windows-xp-targeting-experience"></a>Windows XP 対応のエクスペリエンス

Visual Studio に含まれている Windows XP プラットフォーム ツールセットは、Windows 7 SDK のバージョンですが、最新の C++ コンパイラを使用します。 プロジェクトのプロパティを適切な既定値、下位レベルの対象とするための互換性のあるリンカーの仕様なども構成します。 Windows デスクトップ アプリのみで、Windows XP および Windows Server 2003 では、実行、Windows XP プラットフォーム ツールセットを使用して作成されるが、それらのアプリは最近の Windows オペレーティング システムも実行できます。

#### <a name="to-target-windows-xp"></a>Windows XP に対応するには

1. **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、**[プロパティ]** を選択します。

1. **プロパティ ページ**ダイアログ ボックスで、プロジェクトの**構成プロパティ** > **全般**、設定、**プラットフォーム ツールセット**プロパティが必要な Windows XP ツールセットにします。 たとえば、選択**Visual Studio 2017 - Windows XP (v141_xp)** Windows XP および Windows Server 2003、Microsoft を使用してコードを作成するC++Visual Studio 2017 でのコンパイラ。

### <a name="c-runtime-support"></a>C++ ランタイムのサポート

Windows XP プラットフォーム ツールセット、C ランタイム ライブラリ (CRT)、C++ 標準ライブラリ、Active Template Library (ATL)、同時実行ランタイム ライブラリ (ConCRT)、並列パターン ライブラリ (PPL)、Microsoft Foundation Class ライブラリ (MFC)、および C++ AMP (C++ と大規模なプログラミングを高速) ライブラリには、Windows XP および Windows Server 2003 のランタイム サポートが含まれます。 これらのオペレーティング システムでは、最小のサポートされているバージョンは Windows XP Service Pack 3 (SP3) x86、Windows XP Service Pack 2 (SP2) x64、および Windows Server 2003 Service Pack 2 (SP2) の x86 と x64 の両方。

これらのライブラリは、ターゲットによって、Visual Studio によってインストールされているプラットフォームのツールセットでサポートされます。

|ライブラリ|Windows デスクトップ アプリを対象とする既定のプラットフォーム ツールセット|既定のプラットフォーム ツールセットの対象とするストア アプリ|Windows XP、Windows Server 2003 を対象とする Windows XP プラットフォーム ツールセット|
|---|---|---|---|
|CRT|X|X|x|
|C++ 標準ライブラリ|x|X|X|
|[ATL]|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|x||

> [!NOTE]
> C++ で記述されたアプリ/cli CLI と、.NET Framework 4 をターゲットが Windows XP および Windows Server 2003 で実行します。

### <a name="differences-between-the-toolsets"></a>ツールセットの間の相違点

プラットフォームとライブラリのサポートの違いにより、Windows XP プラットフォーム ツールセットを使用するアプリの開発のエクスペリエンスの対象は、既定の Visual Studio プラットフォーム ツールセットを使用するアプリの場合に完了しません。

- **C++ 言語の機能**

   Visual Studio 2012 で実装された C++ 言語機能だけが、v110 を使用するアプリでサポートされている\_xp プラットフォーム ツールセットです。 Visual Studio 2013 で実装された C++ 言語機能だけが、v120 を使用するアプリでサポートされている\_xp プラットフォーム ツールセットです。 Visual Studio 2015 で実装された C++ 言語機能だけが、v140 を使用するアプリでサポートされている\_xp プラットフォーム ツールセットです。 Visual Studio は、以前のプラットフォーム ツールセットを使用してビルドするときに、対応するコンパイラを使用します。 そのバージョンのコンパイラで実装される追加の C++ 言語の機能を活用するために、最新の Windows XP プラットフォーム ツールセットを使用します。

- **リモート デバッグ**

   Remote Tools for Visual Studio では、Windows XP または Windows Server 2003 でのリモート デバッグをサポートしていません。 Windows XP または Windows Server 2003 で実行されている場合は、アプリをデバッグするには、ローカルまたはリモートでデバッグを Visual Studio の以前のバージョンからデバッガーを使用できます。 これと似ているのが Windows Vista のアプリのデバッグのエクスペリエンスであり、これはプラットフォーム ツールセットのランタイム ターゲットですが、リモートのデバッグ ターゲットではありません。

- **静的分析**

   Windows XP プラットフォーム ツールセットは、Windows 7 SDK とランタイム ライブラリの SAL 注釈は互換性がないために、静的分析をサポートされていません。 Windows XP または Windows Server 2003 をサポートするアプリの静的分析を実行するときに、分析を実行する既定のプラットフォーム ツールセットを対象とするソリューションを一時的に切り替えるし、ビルドを Windows XP プラットフォーム ツールセットに戻りますアプリ。

- **DirectX グラフィックスのデバッグ**

   グラフィックス デバッガーは direct3d9 API をサポートしていないために、Windows XP または Windows Server 2003 で Direct3D を使用するアプリのデバッグに使用できません。 ただし、アプリが Direct3D 10 または Direct3D 11 の API を使用する代替のレンダラーを実装する場合、これらの API を使用する場合の問題の診断にグラフィックス デバッガーを利用できます。

- **HLSL の構築**

   既定では、Windows XP ツールセットでは HLSL のソース コード ファイルはコンパイルされません。 HLSL ファイルをコンパイルするには、June 2010 DirectX SDK をダウンロードしてインストールし、プロジェクトの VC ディレクトリに含めるように設定します。 詳細については、次を参照してください。、"DirectX SDK は登録されませんインクルード/ライブラリ パスを Visual Studio 2010"のセクション、 [June 2010 DirectX SDK ダウンロード ページ](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)します。
