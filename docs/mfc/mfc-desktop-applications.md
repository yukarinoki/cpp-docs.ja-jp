---
title: MFC デスクトップ アプリケーション
ms.date: 11/04/2016
f1_keywords:
- MFC
- mfc
helpviewer_keywords:
- libraries, MFC
- class libraries, MFC
- MFC, about MFC
ms.assetid: 7101cb18-a681-495c-8f2b-069ad20c72f7
ms.openlocfilehash: 042412000ba59c8400c5a3a64edae5d60756116a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58766496"
---
# <a name="mfc-desktop-applications"></a>MFC デスクトップ アプリケーション

Microsoft Foundation Class (MFC) ライブラリは、Win32 お呼びCOM API の多くにオブジェクト指向のラッパーを提供します。 かなりシンプルなデスクトップ アプリケーションの作成にも使用できますが、複数のコントロールを使用する複雑なユーザー インターフェイスを開発する必要がある場合に最も役立ちます。 MFC を使用すると、Office スタイルのユーザー インターフェイスを持つアプリケーションを作成できます。

『MFC リファレンス』では、Microsoft Foundation Class ライブラリ を構成するクラス、グローバル関数、グローバル変数、マクロについて説明しています。

各クラスの説明に含まれる階層図の一部は、基底クラスの位置を知るのに便利です。 『MFC リファレンス』では、継承されたメンバー関数、継承された演算子の説明はしていません。 これらの関数については、階層図の基底クラスの説明を参照してください。

各クラスのトピックは、クラス概要、カテゴリ別のメンバー要約、メンバー関数、オーバーロードされた演算子、およびデータ メンバーについて説明しています。

パブリック クラス メンバーおよびプロテクト クラス メンバーは、アプリケーション プログラムや派生クラスでよく使われるものだけを取り上げています。 全クラス メンバーの一覧は、クラスのヘッダー ファイルを参照してください。

> [!IMPORTANT]
>  MFC クラスとそのメンバーは、Windows ランタイム環境で実行するアプリケーションでは使用できません。
>
>  マルチバイト文字エンコード (MBCS) の MFC ライブラリ (DLL) は、Visual Studio に含まれなくなりましたが、Visual Studio アドオンとして使用できます。 詳細については、[MFC MBCS DLL アドオン](mfc-mbcs-dll-add-on.md)を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[概念](mfc-concepts.md)<br/>
MFC のトピックの概念に関する記事です。

[階層図](hierarchy-chart.md)<br/>
クラス ライブラリのクラスの関係がわかりやすく図で示されています。

[クラスの概要](class-library-overview.md)<br/>
MFC ライブラリのクラスをカテゴリ別に一覧表示します。

[チュートリアル](walkthroughs-mfc.md)<br/>
MFC ライブラリ機能に関連するさまざまなタスクを解説している記事を紹介します。

[テクニカル ノート](mfc-technical-notes.md)<br/>
MFC 開発チームの執筆によるクラス ライブラリに関する技術情報へのリンクを提供します。

[MFC のカスタマイズ](customization-for-mfc.md)<br/>
MFC アプリケーションをカスタマイズするためのヒントを示します。

[クラス](reference/mfc-classes.md)<br/>
MFC クラスへのリンクおよび MFC クラスのヘッダー ファイル情報が用意されています。

[内部クラス](reference/internal-classes.md)<br/>
MFC での内部使用。 完全を期すために、このセクションではこれらの内部クラスについて説明しますが、コードで直接使用するためのものではありません。

[マクロとグローバル](reference/mfc-macros-and-globals.md)<br/>
MFC ライブラリのマクロおよびグローバル関数へのリンクを提供します。

[構造体、スタイル、コールバック関数とメッセージ マップ](reference/structures-styles-callbacks-and-message-maps.md)<br/>
MFC ライブラリで使用する構造体、スタイル、コールバック関数、およびメッセージ マップへのリンクを提供します。

[MFC ウィザードとダイアログ ボックス](reference/mfc-wizards-and-dialog-boxes.md)<br/>
Visual Studio の MFC アプリケーションを作成するための機能のガイドです。

[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
リソース ファイルを使用して、UI の文字列やダイアログ ボックスのレイアウトなどの静的ユーザー インターフェイスのデータを管理する方法。

## <a name="related-sections"></a>関連項目

[階層図カテゴリ](hierarchy-chart-categories.md)<br/>
カテゴリ別の MFC 階層図を示します。

[ATL/MFC 共有クラス](../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
MFC と ATL で共有されるクラスへのリンクを提供します。

[MFC のサンプル](../overview/visual-cpp-samples.md)<br/>
MFC の使い方を示すサンプルへのリンクを提供します。

[Visual C++ ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
Visual C++ に用意されているさまざまなライブラリへのリンクがあります。ATL、MFC、OLE DB の各テンプレート、C ランタイム ライブラリ、および C++ 標準ライブラリが含まれます。

[Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)<br/>
Visual Studio デバッガーを使用してアプリケーションやストアド プロシージャの論理エラーを修正する方法を説明するトピックへのリンクがあります。

## <a name="see-also"></a>関連項目

[MFC と ATL](mfc-and-atl.md)
